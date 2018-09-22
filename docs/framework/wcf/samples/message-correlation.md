---
title: Корреляция сообщений
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: fd97f12f536da85619f300d36d02a10306f32aa5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577468"
---
# <a name="message-correlation"></a>Корреляция сообщений
Этот образец демонстрирует, как приложение очереди сообщений (MSMQ) может отправлять сообщения MSMQ к службе Windows Communication Foundation (WCF) и как можно коррелировать сообщения между приложениями отправителя и получателя в сценарии запроса/ответа. В этом образце используется привязка msmqIntegrationBinding. В данном случае служба представляет собой резидентное консольное приложение, позволяющее наблюдать за тем, как служба получает сообщения из очереди. k  
  
 Служба обрабатывает полученное от отправителя сообщение и отправляет отправителю ответное сообщение. Отправитель согласует полученный ответ с изначально отправленным запросом. Свойства `MessageID` и `CorrelationID` сообщения служат для согласования сообщений запроса и ответа.  
  
 Контракт службы `IOrderProcessor` определяет одностороннюю операцию службы, которую можно использовать с очередями. Сообщение MSMQ не содержит заголовка Action, поэтому автоматически соотнести различные сообщения MSMQ с контрактами операций невозможно. Поэтому в данном случае может существовать только один контракт операции. Если нужно определить для службы несколько контрактов операций, приложение должно сообщать, какой заголовок сообщения MSMQ (например, метку или correlationID) можно использовать для выбора контракта операции. Это показано в [демультиплексирование Custom](../../../../docs/framework/wcf/samples/custom-demux.md).  
  
 Кроме того, сообщение MSMQ не содержит сведений о том, какие заголовки соответствуют различным параметрам контракта операции. Поэтому в данном случае в контракте операции может существовать только один параметр. Параметр имеет тип <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, который содержит сообщение MSMQ. Тип "T" в классе `MsmqMessage<T>` представляет данные, сериализованные в тело сообщения MSMQ. В этом образце тип `PurchaseOrder` сериализован в основную часть сообщения MSMQ.  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
```

 Операция службы обрабатывает заказ на закупку и отображает содержимое заказа и его статус в окне консоли службы. Атрибут <xref:System.ServiceModel.OperationBehaviorAttribute> настраивает операцию для включения в список в транзакции с очередью и для пометки транзакции как завершенной после завершения операции. `PurchaseOrder` содержит сведения о заказе, которые необходимо обработать службе.  

```csharp
// Service class that implements the service contract.  
public class OrderProcessorService : IOrderProcessor  
{  
   [OperationBehavior(TransactionScopeRequired = true,   
          TransactionAutoComplete = true)]  
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)  
   {  
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;  
       Random statusIndexer = new Random();  
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
       Console.WriteLine("Processing {0} ", po);  
       //Send a response to the client that the order has been received   
         and is pending fullfillment.   
       SendResponse(ordermsg);  
    }  
  
    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)  
    {  
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");  
  
        //Set the correlation ID such that the client can correlate the response to the order.  
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);  
        orderResponsemsg.CorrelationId = ordermsg.Id;  
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
        {  
            client.SendOrderResponse(orderResponsemsg);  
            scope.Complete();  
        }  
  
        client.Close();  
    }  
}  
```

 Служба использует пользовательский клиентский метод `OrderResponseClient` для отправки сообщения MSMQ в очередь. Поскольку приложение, которое получает и обрабатывает сообщение является приложением MSMQ, а не приложения WCF, является между двумя приложениями отсутствует неявный контракт службы. То есть в данном сценарии нельзя создать прокси-класс с помощью средства Svcutil.exe.  
  
 Пользовательский прокси-сервер в основном одинаков для всех приложений WCF, использующих `msmqIntegrationBinding` привязки для отправки сообщений. В отличии от других прокси, он не включает ряда операций службы. В него входит только операция отправки сообщения.  

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderResponse  
{  
  
    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]  
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse  
{  
  
    public OrderResponseClient()  
    { }  
  
    public OrderResponseClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SendOrderResponse(msg);  
    }  
}  
```

 Служба является резидентной. При работе с транспортом интеграции MSMQ используемую очередь следует создавать заранее. Это можно сделать вручную или с помощью кода. В данном образце служба содержит код <xref:System.Messaging> для проверки наличия очереди и ее создания, если требуется. Имя очереди считывается из файла конфигурации.  

```csharp
public static void Main()  
{  
       // Get the MSMQ queue name from application settings in configuration.  
      string queueName =   
                ConfigurationManager.AppSettings["orderQueueName"];  
      // Create the transacted MSMQ queue if necessary.  
      if (!MessageQueue.Exists(queueName))  
                MessageQueue.Create(queueName, true);  
     // Create a ServiceHost for the OrderProcessorService type.  
     using (ServiceHost serviceHost = new   
                   ServiceHost(typeof(OrderProcessorService)))  
     {  
            serviceHost.Open();  
            // The service can now be accessed.  
            Console.WriteLine("The service is ready.");  
            Console.WriteLine("Press <ENTER> to terminate service.");  
            Console.ReadLine();  
            // Close the ServiceHost to shutdown the service.  
            serviceHost.Close();  
      }  
}  
```
  
 Очередь MSMQ, в которую отправляются запросы заказов, задается в разделе appSettings файла конфигурации. Конечные точки клиента и службы задаются в разделе system.serviceModel файла конфигурации. Обе конечные точки задают привязку `msmqIntegrationbinding`.  
  
```xml  
<appSettings>  
  <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
<system.serviceModel>  
  <client>  
    <endpoint    name="OrderResponseEndpoint"   
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"  
              binding="msmqIntegrationBinding"  
              bindingConfiguration="OrderProcessorBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">  
    </endpoint>  
  </client>  
  
  <services>  
    <service   
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"  
                            binding="msmqIntegrationBinding"  
                bindingConfiguration="OrderProcessorBinding"   
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">  
      </endpoint>  
    </service>  
  </services>  
  
  <bindings>  
    <msmqIntegrationBinding>  
      <binding name="OrderProcessorBinding" >  
        <security mode="None" />  
      </binding>  
    </msmqIntegrationBinding>  
  </bindings>  
  
</system.serviceModel>  
```  
  
 Клиентское приложение использует для отправки в очередь устойчивых и транзакционных сообщений пространство имен <xref:System.Messaging>. Заказ на закупку содержится в теле сообщения.  

```csharp
static void PlaceOrder()  
{  
    //Connect to the queue  
    MessageQueue orderQueue =   
            new MessageQueue(  
                    ConfigurationManager.AppSettings["orderQueueName"])   
    // Create the purchase order.  
    PurchaseOrder po = new PurchaseOrder();  
    po.CustomerId = "somecustomer.com";  
    po.PONumber = Guid.NewGuid().ToString();  
    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
    lineItem1.ProductId = "Blue Widget";  
    lineItem1.Quantity = 54;  
    lineItem1.UnitCost = 29.99F;  
  
    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
    lineItem2.ProductId = "Red Widget";  
    lineItem2.Quantity = 890;  
    lineItem2.UnitCost = 45.89F;  
  
    po.orderLineItems = new PurchaseOrderLineItem[2];  
    po.orderLineItems[0] = lineItem1;  
    po.orderLineItems[1] = lineItem2;  
  
    Message msg = new Message();  
    msg.UseDeadLetterQueue = true;  
    msg.Body = po;  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new      
     TransactionScope(TransactionScopeOption.Required))  
    {  
        // Submit the purchase order.  
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);  
        // Complete the transaction.  
        scope.Complete();  
    }  
    //Save the messageID for order response correlation.  
    orderMessageID = msg.Id;  
    Console.WriteLine("Placed the order, waiting for response...");  
}  
```

 Очередь MSMQ, из которой получаются ответы о заказах, задается в разделе appSettings файла конфигурации, как показано в следующем образце конфигурации.  
  
> [!NOTE]
>  В имени очереди для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты. Адрес конечной точки WCF задается схема msmq.formatname и используется имя «localhost» на локальном компьютере. Правильно составленное имя формата соответствует шаблону msmq.имя_формата к коде URI в соответствии с указаниями MSMQ.  
  
```xml  
<appSettings>  
    <add key=" orderResponseQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
 Клиентское приложение сохраняет `messageID` сообщения запроса заказа, которое было отправлено службе, и ждет от службы ответа. После получения ответа в очереди клиент согласовывает его с отправленным сообщением заказа с помощью свойства `correlationID` сообщения, которое содержит значение `messageID` сообщения заказа, которое клиент изначально отправил службе.  

```csharp
static void DisplayOrderStatus()  
{  
    MessageQueue orderResponseQueue = new   
     MessageQueue(ConfigurationManager.AppSettings              
                  ["orderResponseQueueName"]);  
    //Create a transaction scope.  
    bool responseReceived = false;  
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;  
    while (!responseReceived)  
    {  
       Message responseMsg;  
       using (TransactionScope scope2 = new    
         TransactionScope(TransactionScopeOption.Required))  
       {  
          //Receive the Order Response message.  
          responseMsg =   
              orderResponseQueue.Receive  
                   (MessageQueueTransactionType.Automatic);  
          scope2.Complete();  
     }  
     responseMsg.Formatter = new   
     System.Messaging.XmlMessageFormatter(new Type[] {   
         typeof(PurchaseOrder) });  
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;  
    //Check if the response is for the order placed.  
    if (orderMessageID == responseMsg.CorrelationId)  
    {  
       responseReceived = true;  
       Console.WriteLine("Status of current Order: OrderID-{0},Order   
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
    else  
    {  
       Console.WriteLine("Status of previous Order: OrderID-{0},Order    
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
  }  
}  
```

 При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента. Можно видеть, как служба получает сообщения от клиента и отправляет ему ответные сообщения. Клиент отображает запросы, получаемые от службы. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
> [!NOTE]
>  Данный образец требует установки очереди сообщений (MSMQ). Инструкции по установке MSMQ см. в разделе "См. также".  
  
### <a name="to-setup-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1.  Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Разверните **функции** вкладки.  
  
    3.  Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.  
  
    4.  Проверьте **транзакционная** поле.  
  
    5.  Введите `ServiceModelSamplesTransacted` как имя новой очереди.  
  
3.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы запустить образец в конфигурации с одним компьютером, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1.  Скопируйте на компьютер службы файлы служебной программы из папки \service\bin\ в папку языка.  
  
2.  Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
3.  В файле Client.exe.config измените orderQueueName, указав имя компьютера службы вместо «.».  
  
4.  В файле Service.exe.config измените адрес конечной точки клиента, указав имя клиентского компьютера вместо «.».  
  
5.  На компьютере службы запустите из командной строки программу Service.exe.  
  
6.  На клиентском компьютере из командной строки запустите программу Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`  
  
## <a name="see-also"></a>См. также  
 [Очереди в WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Очереди сообщений](https://go.microsoft.com/fwlink/?LinkId=94968)
