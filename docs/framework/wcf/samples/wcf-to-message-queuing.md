---
title: "Отправка сообщений из приложения Windows Communication Foundation в службу очередей сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Отправка сообщений из приложения Windows Communication Foundation в службу очередей сообщений
Данный образец показывает способ отправки сообщения приложению очереди сообщений \(MSMQ\) при помощи приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Служба представляет собой резидентное консольное приложение, позволяющее наблюдать за получением службой сообщений из очереди.Одновременная работа службы и клиента не требуется.  
  
 Служба получает сообщения от очереди и обрабатывает заказы.Служба создает транзакционную очередь и создает обработчик полученных сообщений, как показано в следующем образце кода.  
  
```  
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
  
```  
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
  
```  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
```  
  
> [!NOTE]
>  В имени очереди для определения локального компьютера используется точка \(.\), а в пути в качестве разделителей используются символы обратной косой черты.  
  
 Клиент создает заказ на покупку и отправляет его в пределах транзакции, как показано в следующем образце кода.  
  
```  
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
  
 При отправке сообщения MSMQ в очередь клиент использует внутренний пользовательский порядок сообщений.Поскольку приложение, получающее и обрабатывающее сообщение, является приложением MSMQ, а не приложением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], между двумя приложениями отсутствует неявный контракт службы.Таким образом, в данном сценарии невозможно создать прокси\-класс при помощи средства Svculti.exe.  
  
 Пользовательский клиент в основном одинаков для всех приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], использующих построение `MsmqIntegration` для отправки сообщений.В отличие от других клиентов, он не включает ряд операций службы.В него входит только операция отправки сообщения.  
  
```  
  
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
  
 При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента.Можно видеть, как служба получает сообщения от клиента.Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно.Например, можно запустить клиент, выключить его, а затем запустить службу и все равно получить сообщения клиента.  
  
> [!NOTE]
>  Данный образец требует установки очереди сообщений.См. инструкции по установке в разделе [Очередь сообщений](http://go.microsoft.com/fwlink/?LinkId=94968).  
  
### Настройка, построение и запуск образца  
  
1.  Убедитесь, что выполнена процедура, описанная в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При первом запуске служба проверит наличие очереди.Если очередь отсутствует, служба ее создаст.Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.Чтобы создать очередь в Windows 2008, выполните следующие шаги.  
  
    1.  Откройте диспетчер сервера в [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Разверните вкладку **Функции**.  
  
    3.  Щелкните правой кнопкой мыши узел **Очереди личных сообщений** и выберите пункты **Создать**, **Частная очередь**.  
  
    4.  Установите флажок **Транзакционная**.  
  
    5.  В качестве имени новой очереди укажите `ServiceModelSamplesTransacted`.  
  
3.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы запустить образец на одном компьютере, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Запуск образца на нескольких компьютерах  
  
1.  Скопируйте на компьютер службы файлы служебной программы из папки \\service\\bin\\ в папку языка.  
  
2.  Скопируйте на клиентские компьютеры файлы из папки \\client\\bin\\ в папку языка.  
  
3.  В файле Client.exe.config измените адрес конечной точки клиента, указав имя компьютера службы вместо «.».  
  
4.  На компьютере службы запустите из командной строки программу Service.exe.  
  
5.  На клиентском компьютере из командной строки запустите программу Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## См. также  
 [Как обмениваться сообщениями с конечными точками WCF и приложениями очереди сообщений](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Очередь сообщений](http://go.microsoft.com/fwlink/?LinkId=94968)