---
title: "Пользовательское демультиплексирование | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: 41
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 41
---
# Пользовательское демультиплексирование
В этом образце показано, как сопоставлять заголовки сообщений MSMQ с различными операциями служб, чтобы службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], использующие привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>, не были ограничены использованием одной операции службы, как показано в примерах [Передача сообщений из службы очередей сообщений в приложение Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) и [Отправка сообщений из приложения Windows Communication Foundation в службу очередей сообщений](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md).  
  
 В данном образце служба представляет собой резидентное консольное приложение, позволяющее наблюдать службу, получающую сообщения из очереди.  
  
 Контракт службы `IOrderProcessor` определяет одностороннюю службу, которую можно использовать с очередями.  
  
```  
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```  
  
 У сообщения MSMQ нет заголовка Action.  Из\-за этого автоматически соотнести различные сообщения MSMQ с контрактами операций невозможно.  Поэтому может существовать только один контракт операции.  Чтобы преодолеть это ограничение, служба реализует метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.  Метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> позволяет службе сопоставить данный заголовок сообщения определенной операции службы.  В этом образце метка заголовка сообщения сопоставляется операциям службы.  Параметр `Name` контракта операции определяет, какую операцию службы следует выполнить для данной метки сообщения.  Например, если метка заголовка сообщения содержит "SubmitPurchaseOrder", вызывается операция службы "SubmitPurchaseOrder".  
  
```  
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```  
  
 Служба должна реализовывать метод <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> интерфейса <xref:System.ServiceModel.Description.IContractBehavior>, как показано в следующем образце кода.  Это применяет пользовательский `OperationSelector` к среде выполнения инфраструктуры службы.  
  
```  
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```  
  
 Перед тем как попасть к OperationSelector, сообщение должно пройти через свойство <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> диспетчера.  По умолчанию сообщение отклоняется, если его действие не обнаружено ни в одном контракте, реализованном службой.  Чтобы избежать этого, реализуем поведение <xref:System.ServiceModel.Description.IEndpointBehavior> с именем `MatchAllFilterBehavior`, позволяющее любым сообщениям проходить через фильтр `ContractFilter`, применяя <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> следующим образом.  
  
```  
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```  
  
 При получении сообщения службой используются сведения, содержащиеся в метке заголовка, и выполняется соответствующая операция службы.  Тело сообщения десериализуется в объект `PurchaseOrder`, как показано в следующем образце кода.  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```  
  
 Служба является резидентной.  При работе с MSMQ используемую очередь следует создавать заранее.  Это можно сделать вручную или с помощью кода.  В данном образце служба содержит код для проверки наличия очереди и ее создания, если очереди нет.  Имя очереди считывается из файла конфигурации.  
  
```  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
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
  
 Имя очереди MSMQ задается в разделе appSettings файла конфигурации.  
  
> [!NOTE]
>  В имени очереди для определения локального компьютера используется точка \(.\), а в пути в качестве разделителей используются символы обратной косой черты.  В адресе конечной точки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] задается схема msmq.formatname, для обозначения локального компьютера используется имя localhost.  Схеме следует адрес очереди в правильном формате в соответствии с рекомендациям о создании адресов имен в формате MSMQ.  
  
```  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
  
```  
  
> [!NOTE]
>  Данный образец требует установки [очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=95143).  
  
 Запустите службу и выполните клиент.  
  
 Клиент получает следующий результат.  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 Служба должна предоставить следующие результаты.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При первом запуске служба проверит наличие очереди.  Если очередь отсутствует, служба ее создаст.  Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.  Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1.  Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Разверните вкладку **Функции**.  
  
    3.  Щелкните правой кнопкой мыши узел **Очереди личных сообщений** и выберите пункты **Создать**, **Частная очередь**.  
  
    4.  Установите флажок **Транзакционная**.  
  
    5.  В качестве имени новой очереди укажите `ServiceModelSamplesTransacted`.  
  
3.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Запуск образца на нескольких компьютерах  
  
1.  Скопируйте на компьютер службы файлы служебной программы из папки \\service\\bin\\ в папку языка.  
  
2.  Скопируйте на клиентские компьютеры файлы из папки \\client\\bin\\ в папку языка.  
  
3.  В файле Client.exe.config измените orderQueueName, указав имя компьютера службы вместо «.».  
  
4.  На компьютере службы запустите из командной строки программу Service.exe.  
  
5.  На клиентском компьютере из командной строки запустите программу Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## См. также  
 [Очереди в WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)   
 [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143)