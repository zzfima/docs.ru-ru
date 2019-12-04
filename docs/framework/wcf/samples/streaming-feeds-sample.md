---
title: Пример потоковой передачи каналов
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 9d40a07b81474a283a8edbeb7aca1aa7ab3993b2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716638"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="1c3ce-102">Пример потоковой передачи каналов</span><span class="sxs-lookup"><span data-stu-id="1c3ce-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="1c3ce-103">В этом образце показано, как управлять веб-каналами синдикации, содержащими большое число элементов.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="1c3ce-104">На стороне сервера этот пример показывает, как откладывать создание отдельных объектов <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канале до момента записи элемента в сетевой поток.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="1c3ce-105">На стороне клиента этот пример показывает, что для чтения отдельных элементов из сетевого потока можно использовать пользовательский модуль форматирования веб-канала синдикации, чтобы читаемый веб-канал никогда не буферизовался в памяти целиком.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="1c3ce-106">Для лучшей демонстрации возможности потоковой передачи API синдикации в этом образце используется достаточно нереальный сценарий, при котором сервер предоставляет веб-канал с бесконечным числом элементов.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="1c3ce-107">В этом случае сервер продолжает создавать в веб-канале новые элементы, пока он не определит, что клиент не прочитал из веб-канала заданное число элементов (по умолчанию - 10).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="1c3ce-108">Для простоты клиент и служба реализованы в одном процессе и используют общий объект `ItemCounter` для отслеживания числа элементов, созданных клиентом.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="1c3ce-109">Тип `ItemCounter` нужен лишь для того, чтобы пример можно было верно завершить, и не является ключевым элементом демонстрируемого сценария.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="1c3ce-110">В демонстрации используются визуальные C# итераторы (с использованием `yield return` конструкции ключевого слова).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-110">The demonstration makes use of Visual C# iterators (using the `yield return` keyword construct).</span></span> <span data-ttu-id="1c3ce-111">Дополнительные сведения о итераторах см. в разделе "использование итераторов" на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-111">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="1c3ce-112">Service</span><span class="sxs-lookup"><span data-stu-id="1c3ce-112">Service</span></span>  
 <span data-ttu-id="1c3ce-113">Служба реализует базовый контракт <xref:System.ServiceModel.Web.WebGetAttribute>, состоящий из одной операции, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="1c3ce-114">Служба реализует этот контракт с помощью класса `ItemGenerator`, создающего потенциально бесконечный поток экземпляров <xref:System.ServiceModel.Syndication.SyndicationItem> с использованием итератора, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```csharp
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="1c3ce-115">Когда реализация службы создает веб-канал, вместо буферизованной коллекции элементов используется вывод метода `ItemGenerator.GenerateItems()`.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```csharp
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="1c3ce-116">В результате поток элементов никогда не помещается в буфер памяти целиком.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="1c3ce-117">Это поведение можно проследить, установив точку останова в операторе `yield return` в методе `ItemGenerator.GenerateItems()` и отметив, что эта точка останова встречается в первый раз после того, как служба возвращала результат метода `StreamedFeed()`.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-117">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="1c3ce-118">Клиент</span><span class="sxs-lookup"><span data-stu-id="1c3ce-118">Client</span></span>  
 <span data-ttu-id="1c3ce-119">Клиент в этом образце применяет пользовательскую реализацию <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>, которая задерживает воссоздание отдельных элементов в веб-канале вместо их записи в буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="1c3ce-120">Пользовательский экземпляр `StreamedAtom10FeedFormatter` используется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="1c3ce-121">Обычно вызов метода <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> не завершается, пока будет прочитано из сети и записано в буфер в памяти все содержимое веб-канала.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="1c3ce-122">Однако класс `StreamedAtom10FeedFormatter` переопределяет метод <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29>, чтобы вместо буферизованной коллекции он возвращал итератор, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```csharp  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="1c3ce-123">В результате элемент не будет прочитан из сети, пока клиентское приложение, через которое проходят результаты вызова метода `ReadItems()`, не будет готово к использованию этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="1c3ce-124">Это поведение можно проследить, установив точку останова в операторе `yield return` в `StreamedAtom10FeedFormatter.DelayReadItems()` и убедившись в том, что эта точка останова встречается в первый раз после завершения вызова `ReadFrom()`.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-124">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="1c3ce-125">Ниже показано, как выполнить построение и запуск этого образца.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="1c3ce-126">Обратите внимание, что хотя сервер прекращает создание элементов после того, как клиент прочтет 10 элементов, результат работы программы показывает, что клиент прочитывает гораздо больше, чем 10 элементов.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="1c3ce-127">Это связано с тем, что используемая сетевая привязка передает данные фрагментами по 4 килобайта (КБ).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="1c3ce-128">Таким образом, клиент получает 4 КБ данных элемента раньше, чем он сможет прочитать хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="1c3ce-129">Это нормальное поведение (разбиение данных на небольшие фрагменты при их потоковой передаче по протоколу HTTP повышает производительность).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1c3ce-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="1c3ce-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1c3ce-131">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1c3ce-132">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1c3ce-133">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1c3ce-134">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1c3ce-135">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1c3ce-135">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="1c3ce-136">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1c3ce-137">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1c3ce-137">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="1c3ce-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c3ce-138">See also</span></span>

- [<span data-ttu-id="1c3ce-139">Автономный веб-канал диагностики</span><span class="sxs-lookup"><span data-stu-id="1c3ce-139">Stand-Alone Diagnostics Feed</span></span>](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
