---
title: Пользовательское демультиплексирование
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45184c2d884347baef4090ed496e22e77aab5423
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="custom-demux"></a>Пользовательское демультиплексирование
В этом примере показано, как можно сопоставлять заголовки сообщений MSMQ с различными операциями служб, чтобы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] служб, использующих <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> не ограничены использованием одной операции службы, как показано в [служба очереди сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) и [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образцов.  
  
 В данном образце служба представляет собой резидентное консольное приложение, позволяющее наблюдать службу, получающую сообщения из очереди.  
  
 Контракт службы `IOrderProcessor` определяет одностороннюю службу, которую можно использовать с очередями.  

```csharp
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

 У сообщения MSMQ нет заголовка Action. Из-за этого автоматически соотнести различные сообщения MSMQ с контрактами операций невозможно. Поэтому может существовать только один контракт операции. Чтобы преодолеть это ограничение, служба реализует метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>. Метод <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> позволяет службе сопоставить данный заголовок сообщения определенной операции службы. В этом образце метка заголовка сообщения сопоставляется операциям службы. Параметр `Name` контракта операции определяет, какую операцию службы следует выполнить для данной метки сообщения. Например, если метка заголовка сообщения содержит "SubmitPurchaseOrder", вызывается операция службы "SubmitPurchaseOrder".  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 Служба должна реализовывать метод <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> интерфейса <xref:System.ServiceModel.Description.IContractBehavior>, как показано в следующем образце кода. Это применяет пользовательский `OperationSelector` к среде выполнения инфраструктуры службы.  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 Перед тем как попасть к OperationSelector, сообщение должно пройти через свойство <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> диспетчера. По умолчанию сообщение отклоняется, если его действие не обнаружено ни в одном контракте, реализованном службой. Чтобы избежать этого, реализуем поведение <xref:System.ServiceModel.Description.IEndpointBehavior> с именем `MatchAllFilterBehavior`, позволяющее любым сообщениям проходить через фильтр `ContractFilter`, применяя <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> следующим образом.  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 При получении сообщения службой используются сведения, содержащиеся в метке заголовка, и выполняется соответствующая операция службы. Тело сообщения десериализуется в объект `PurchaseOrder`, как показано в следующем образце кода.  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 Служба является резидентной. При работе с MSMQ используемую очередь следует создавать заранее. Это можно сделать вручную или с помощью кода. В данном образце служба содержит код для проверки наличия очереди и ее создания, если очереди нет. Имя очереди считывается из файла конфигурации.  

```csharp
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
>  В имени очереди для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты. В адресе конечной точки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] задается схема msmq.formatname, для обозначения локального компьютера используется имя localhost. Схеме следует адрес очереди в правильном формате в соответствии с рекомендациям о создании адресов имен в формате MSMQ.  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  В этом примере требуется установка [очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=95143).  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1.  Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Разверните **функции** вкладки.  
  
    3.  Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.  
  
    4.  Проверьте **транзакций** поле.  
  
    5.  Введите `ServiceModelSamplesTransacted` качестве имени новой очереди.  
  
3.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1.  Скопируйте на компьютер службы файлы служебной программы из папки \service\bin\ в папку языка.  
  
2.  Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
3.  В файле Client.exe.config измените orderQueueName, указав имя компьютера службы вместо «.».  
  
4.  На компьютере службы запустите из командной строки программу Service.exe.  
  
5.  На клиентском компьютере из командной строки запустите программу Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a>См. также  
 [Очереди в WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=95143)
