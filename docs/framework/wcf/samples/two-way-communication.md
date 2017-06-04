---
title: "Двусторонний обмен данными | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Двусторонний обмен данными
В этом образце показано, как осуществлять транзакционное двустороннее взаимодействие с использованием очередей с помощью MSMQ.  В этом примере используется привязка `netMsmqBinding`.  В данном случае служба представляет собой резидентное консольное приложение, позволяющее наблюдать за тем, как служба получает сообщения из очереди.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец основан на примере [Привязка MSMQ с поддержкой транзакций](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
 При использовании очередей клиент взаимодействует со службой посредством очереди.  Клиент отправляет сообщения в очередь, а служба получает сообщения из очереди.  Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.  
  
 В этом образце показано двустороннее взаимодействие с использованием очередей.  Клиент отправляет заказы на покупку в очередь из области транзакции.  Служба получает заказы, обрабатывает заказ и вызывает клиент с состоянием заказа из очереди из области транзакции.  Для двустороннего взаимодействия и клиент, и служба используют очереди для заказов на покупку и состояний заказов.  
  
 Контракт службы `IOrderProcessor` определяет односторонние операции службы, которые можно использовать с очередями.  Операция службы включает конечную точку ответа, на которую нужно отправлять состояния заказов.  Конечная точка ответа \- это универсальный код ресурса \(URI\) очереди, служащей для отправки клиенту состояний заказов.  Приложение, обрабатывающее заказы, реализует этот контракт.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}  
  
```  
  
 Контракт ответа для отправки состояния заказа задается клиентом.  Клиент реализует контракт состояния заказа.  Служба использует созданный прокси этого контракта для отправки состояния заказа клиенту.  
  
```  
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```  
  
 Операция службы обрабатывает отправленный заказ на покупку.  Объект <xref:System.ServiceModel.OperationBehaviorAttribute> применяется к операции службы, чтобы задать автоматическое зачисление в транзакции, использующейся для получения сообщения из очереди, и автоматическое завершение транзакций после завершения операции службы.  Класс `Orders` инкапсулирует функцию обработки заказа.  В данном случае он добавляет заказ на покупку в словарь.  Транзакция, в которую зачислена операция службы, доступна операциям в классе `Orders`.  
  
 Операция службы, помимо обработки отправленного заказа на закупку, отвечает клиенту о состоянии заказа.  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```  
  
 Имя очереди MSMQ задается в разделе appSettings файла конфигурации.  Конечная точка службы определяется в разделе System.ServiceModel файла конфигурации.  
  
> [!NOTE]
>  Правила адресации несколько различаются для имени очереди MSMQ и адреса конечной точки.  В имени очереди MSMQ для определения локального компьютера используется точка \(.\), а в пути в качестве разделителей используются символы обратной косой черты.  В адресе конечной точки [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] задается схема net.msmq:, для обозначения локального компьютера используется имя "localhost", а в пути в качестве разделителей используются символы косой черты.  Для чтения очереди, размещенной на удаленном компьютере, "." и "localhost" следует заменить именем удаленного компьютера.  
  
 Служба является резидентной.  При работе с транспортом MSMQ используемую очередь следует создавать заранее.  Это можно сделать вручную или с помощью кода.  В данном образце служба проверяет наличие очереди и создает ее, если это необходимо.  Имя очереди считывается из файла конфигурации.  Средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с помощью базового адреса создает для службы прокси.  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderProcessorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 Клиент создает транзакцию.  Связь с очередью происходит в области транзакции, поэтому она обрабатывается как единый модуль, в котором либо все сообщения отправляются успешно, либо не отправляется ни одного.  
  
```  
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
  
```  
  
 Код клиента реализует контракт `IOrderStatus` для получения от службы состояния заказа.  В данном случае он выводит состояние заказа.  
  
```  
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,   
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,   
                                                           status);  
    }  
}  
  
```  
  
 Очередь состояний заказов создается в методе `Main`.  Конфигурация клиента включает конфигурацию службы состояния заказов, размещающую службу состояния заказов, как показано в следующем образце конфигурации.  
  
```  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service   
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
              binding="netMsmqBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
  
```  
  
 При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.  Можно видеть, как служба получает сообщения от клиента.  Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
 Служба отображает сведения заказа на покупку и указывает, что отправляет состояние заказа в очередь состояний заказов.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 Клиент отображает сведения о состоянии заказа, отправленные службой.  
  
```  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
  
```  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имена конечных точек в конфигурации клиента для соответствия клиентскому коду.  
  
 По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена.  Имеется два соответствующих свойства для обеспечения безопасности транспорта MSMQ: <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` По умолчанию установлен режим проверки подлинности `Windows` и уровень защиты `Sign`.  Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена функция интеграции MSMQ со службой каталогов Active Directory.  Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.  
  
### Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory  
  
1.  Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.  
  
    ```  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"   
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
2.  Отключение безопасности для конфигурации клиента дает следующий результат:  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service   
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
                    binding="netMsmqBinding"   
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3.  Служба в образце создает привязку в службе `OrderProcessorService`.  Добавьте строку кода после создания экземпляра привязки, чтобы задать режим безопасности `None`.  
  
    ```  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4.  Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.  
  
    > [!NOTE]
    >  Установка для `security mode` значения `None` равнозначна установке для безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> или `Message` значения `None`.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
  
## См. также