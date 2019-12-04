---
title: Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: 1cbc1251a8e4eaaaf4b47357851dd681ae326f25
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715063"
---
# <a name="windows-communication-foundation-to-message-queuing"></a>Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ
В этом примере показано, как приложение Windows Communication Foundation (WCF) может отправить сообщение в приложение очереди сообщений (MSMQ). Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди. Одновременная работа службы и клиента не требуется.

 Служба получает сообщения от очереди и обрабатывает заказы. Служба создает транзакционную очередь и создает обработчик полученных сообщений, как показано в следующем образце кода.

```csharp
static void Main(string[] args)
{
    if (!MessageQueue.Exists(
              ConfigurationManager.AppSettings["queueName"]))
       MessageQueue.Create(
           ConfigurationManager.AppSettings["queueName"], true);
        //Connect to the queue
        MessageQueue Queue = new
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);
    Queue.ReceiveCompleted +=
                 new ReceiveCompletedEventHandler(ProcessOrder);
    Queue.BeginReceive();
    Console.WriteLine("Order Service is running");
    Console.ReadLine();
}
```

 При получении сообщения в очереди вызывается обработчик сообщений `ProcessOrder`.

```csharp
public static void ProcessOrder(Object source,
    ReceiveCompletedEventArgs asyncResult)
{
    try
    {
        // Connect to the queue.
        MessageQueue Queue = (MessageQueue)source;
        // End the asynchronous receive operation.
        System.Messaging.Message msg =
                     Queue.EndReceive(asyncResult.AsyncResult);
        msg.Formatter = new System.Messaging.XmlMessageFormatter(
                                new Type[] { typeof(PurchaseOrder) });
        PurchaseOrder po = (PurchaseOrder) msg.Body;
        Random statusIndexer = new Random();
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
        Console.WriteLine("Processing {0} ", po);
        Queue.BeginReceive();
    }
    catch (System.Exception ex)
    {
        Console.WriteLine(ex.Message);
    }

}
```

 Служба извлекает `ProcessOrder` из тела сообщения MSMQ и обрабатывает заказ.

 Имя очереди MSMQ задается в разделе appSettings файла конфигурации, как показано в следующем образце конфигурации.

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

> [!NOTE]
> В имени очереди для определения локального компьютера используется точка (.), а в пути в качестве разделителей используются символы обратной косой черты.

 Клиент создает заказ на покупку и отправляет его в пределах транзакции, как показано в следующем образце кода.

```csharp
// Create the purchase order
PurchaseOrder po = new PurchaseOrder();
// Fill in the details
...

OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");

MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    client.SubmitPurchaseOrder(ordermsg);
    scope.Complete();
}
Console.WriteLine("Order has been submitted:{0}", po);

//Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

 При отправке сообщения MSMQ в очередь клиент использует внутренний пользовательский порядок сообщений. Так как приложение, получающее и обрабатывающее сообщение, является приложением MSMQ, а не приложением WCF, неявный контракт службы между двумя приложениями отсутствует. Таким образом, в данном сценарии невозможно создать прокси-класс при помощи средства Svculti.exe.

 По сути, Пользовательский клиент одинаков для всех приложений WCF, использующих привязку `MsmqIntegration` для отправки сообщений. В отличие от других клиентов, он не включает ряд операций службы. В него входит только операция отправки сообщения.

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor
{
    public OrderProcessorClient(){}

    public OrderProcessorClient(string configurationName)
        : base(configurationName)
    { }

    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SubmitPurchaseOrder(msg);
    }
}
```

 При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента. Можно видеть, как служба получает сообщения от клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент. Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно. Например, можно запустить клиент, выключить его, а затем запустить службу и все равно получить сообщения клиента.

> [!NOTE]
> Данный образец требует установки очереди сообщений. См. инструкции по установке в [очереди сообщений](https://go.microsoft.com/fwlink/?LinkId=94968).  
  
### <a name="to-setup-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1. Откройте диспетчер сервера в Visual Studio 2012.  
  
    2. Разверните вкладку **функции** .  
  
    3. Щелкните правой кнопкой мыши **частные очереди сообщений**и выберите **создать**, **Частная очередь**.  
  
    4. Установите флажок **транзакционная** .  
  
    5. Введите `ServiceModelSamplesTransacted` в качестве имени новой очереди.  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить пример в конфигурации с одним компьютером, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Скопируйте на компьютер службы файлы служебной программы из папки \service\bin\ в папку языка.  
  
2. Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
3. В файле Client.exe.config измените адрес конечной точки клиента, указав имя компьютера службы вместо «.».  
  
4. На компьютере службы запустите из командной строки программу Service.exe.  
  
5. На клиентском компьютере из командной строки запустите программу Client.exe.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Очередь сообщений](https://go.microsoft.com/fwlink/?LinkId=94968)
