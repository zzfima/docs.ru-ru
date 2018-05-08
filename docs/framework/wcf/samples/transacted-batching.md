---
title: Пакетирование с поддержкой транзакций
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: 7df65b8f3f149deac841010e392f3919b24506b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transacted-batching"></a>Пакетирование с поддержкой транзакций
В этом образце показано, как пакетировать операции чтения с поддержкой транзакций с помощью очереди сообщений (MSMQ). Пакетирование с поддержкой транзакций - это функция оптимизации производительности для чтения с поддержкой транзакций при взаимодействии с использованием очередей.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 При использовании очередей клиент взаимодействует со службой посредством очереди. Конкретно, клиент отправляет сообщения в очередь. Служба получает сообщения из очереди. Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.  
  
 В этом образце демонстрируется пакетирование с поддержкой транзакций. Пакетирование с поддержкой транзакций - это поведение, которое позволяет считывать несколько сообщений в очереди и обрабатывать их в рамках одной транзакции.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1.  Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Разверните **функции** вкладки.  
  
    3.  Щелкните правой кнопкой мыши **очереди личных сообщений**и выберите **New**, **частную очередь**.  
  
    4.  Проверьте **транзакций** поле.  
  
    5.  Введите `ServiceModelSamplesTransacted` качестве имени новой очереди.  
  
    > [!NOTE]
    >  В этом образце клиент отправляет в составе пакета сотни сообщений. Естественно, что обработка в служебном приложении этих сообщений займет определенное время.  
  
3.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory  
  
1.  По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена. Имеется два соответствующих свойства для обеспечения безопасности транспорта MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` по умолчанию имеет значение режима проверки подлинности `Windows` и устанавливается уровень защиты `Sign`. Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory. Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.  
  
2.  Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значение `None`, как показано в следующем образце конфигурации.  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.  
  
    > [!NOTE]
    >  Задание для `security``mode` значения `None` эквивалентно заданию для параметров безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и `Message` значения `None`.  
  
4.  Чтобы выполнить базу данных на удаленном компьютере, необходимо изменить строку подключения так, чтобы она указывала на компьютер, на котором находится база данных.  
  
## <a name="requirements"></a>Требования  
 Для выполнения этого образца должна быть установлена MSMQ, необходимо также использовать SQL или SQL Express.  
  
## <a name="demonstrates"></a>Демонстрации  
 В этом образце демонстрируется поведение пакетирования с поддержкой транзакций. Пакетирование с поддержкой транзакций - это функция оптимизации производительности, предоставляемая с транспортом очередей MSMQ.  
  
 При использовании транзакций для отправки и получения сообщений это фактически две отдельные транзакции. При отправке клиентом сообщений в области транзакции эта транзакция локальна для клиента и диспетчера очереди клиента. При получении службой сообщений в области транзакции эта транзакция локальна для службы и диспетчера принимающей очереди. Очень важно помнить, что клиент и служба не участвуют в одной транзакции, а используют разные транзакции при выполнении операций с очередью (например, отправки и получения).  
  
 В этом образце одна транзакция используется для выполнения нескольких операций службы. Этот подход используется исключительно в качестве возможности оптимизации производительности и не влияет на семантику приложения. Пример построен на [транзакции привязки MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
## <a name="comments"></a>Комментарии  
 В этом образце клиент отправляет службе пакет сообщений из области транзакции. Чтобы продемонстрировать оптимизацию производительности, отправляется большое число сообщений (до 2 500 в данном случае).  
  
 Сообщения, отправленные в очередь, принимаются после этого службой в области транзакции, определенной службой. Если не используется пакетирование, каждый вызов операции службы приводит к выполнению 2 500 транзакций. Это влияет на производительность системы. Так как участвуют два диспетчера ресурсов (очередь MSMQ и база данных `Orders`), каждая транзакция является транзакцией DTC. Оптимизация обеспечивается выполнением гораздо меньшего числа транзакций, что возможно благодаря вызову пакета сообщений и операции службы в одной транзакции.  
  
 Ниже перечислены способы использования функции пакетирования.  
  
-   При задании поведения пакетирования с поддержкой транзакций в конфигурации.  
  
-   При задании размера пакета в терминах числа сообщений, считываемых в одной транзакции.  
  
-   При задании максимального числа одновременно выполняемых пакетов.  
  
 В этом примере демонстрируется повышение производительности благодаря уменьшению числа транзакций вследствие того, что в одной транзакции вызывается 100 операций службы до фиксации транзакции.  
  
 Поведение службы определяет поведение операции со значением `TransactionScopeRequired`, равным `true`. Это обеспечивает использование любыми диспетчерами ресурсов, к которым обращается метод, той же области транзакции, что и для получения сообщения из очереди. В этом примере основная база данных используется для хранения сведений о заказе на покупку, содержащихся в сообщении. Область транзакции также гарантирует возврат сообщения в очередь, если метод создаст исключение. Если не установить такое поведение операции, канал в очереди создает транзакцию для чтения сообщения из очереди и автоматически фиксирует ее перед передачей, поэтому при ошибке операции сообщение теряется. Наиболее стандартная схема для операций служб заключается в зачислении в транзакцию, которая используется для чтения сообщения из очереди, как показано в следующем примере кода.  
  
 Обратите внимание, что `ReleaseServiceInstanceOnTransactionComplete` присвоено значение `false`. Это важное требование при пакетировании. Свойство `ReleaseServiceInstanceOnTransactionComplete` в `ServiceBehaviorAttribute` показывает, что делать с экземпляром службы после завершения транзакции. По умолчанию после завершения транзакции экземпляр службы освобождается. Смысл пакетирования заключается в том, что одна транзакция используется для чтения и диспетчеризации большого числа сообщений в очереди. Следовательно, освобождение экземпляра службы приводит к преждевременному завершению транзакции, что противоречит смыслу пакетирования. Если этому свойству присвоено значение `true`, а поведение пакетирования с поддержкой транзакций добавляется в конечную точку, поведение проверки пакетирования создает исключение.  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 Класс `Orders` инкапсулирует обработку заказа. В этом образце он обновляет базу данных, внося сведения о заказе на покупку.  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 Поведение пакетирования и его конфигурация заданы в конфигурации приложения службы.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Размер пакета - это подсказка системе. Например, если задать размер пакета равным 20, именно столько сообщений считает и диспетчеризует одна транзакция, после чего произойдет фиксация транзакции. Однако в некоторых случаях транзакция может зафиксировать пакет раньше, чем будет достигнут размер пакета.  
>   
>  С каждой транзакцией связан период ожидания, который отсчитывается после создания транзакции. По истечении этого времени ожидания транзакция прерывается. Этот период ожидания может истечь раньше, чем будет достигнут размер пакета. Чтобы избежать переработки пакета из-за прерывания, `TransactedBatchingBehavior` проверяет, сколько времени осталось до истечения периода ожидания для данной транзакции. Транзакция фиксируется по истечении 80 % времени ожидания транзакции.  
>   
>  Если в очереди больше нет сообщений, вместо того, чтобы ждать достижения размера пакета, поведение <xref:System.ServiceModel.Description.TransactedBatchingBehavior> фиксирует транзакцию.  
>   
>  Выбор размера пакета зависит от используемого приложения. Если размер пакета слишком маленький, производительность может быть ниже требуемого уровня. С другой стороны, слишком большой размер пакета также может снизить производительность. Например, время существования транзакции может увеличиться, и она может хранить блокировки используемой базы данных, либо возможна взаимоблокировка транзакции, в результате чего может произойти откат пакета и повторение всей процедуры.  
  
 Клиент создает область транзакции. Связь с очередью происходит в области транзакции, поэтому она обрабатывается как единый модуль, в котором либо все сообщения отправляются в очередь, либо в очередь не отправляется ни одного сообщения. Транзакция фиксируется вызовом метода <xref:System.Transactions.TransactionScope.Complete%2A> для области транзакции.  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента. Можно видеть, как служба получает сообщения от клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент. Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно. Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента. При считывании и обработке пакета сообщений можно видеть чередующийся вывод.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a>См. также
