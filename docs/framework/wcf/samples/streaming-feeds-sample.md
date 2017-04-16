---
title: "Образец потоковой передачи каналов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Образец потоковой передачи каналов
В этом образце показано, как управлять веб\-каналами синдикации, содержащими большое число элементов.На стороне сервера этот образец показывает, как откладывать создание отдельных объектов <xref:System.ServiceModel.Syndication.SyndicationItem> в веб\-канале до момента записи элемента в сетевой поток.  
  
 На стороне клиента этот образец показывает, что для чтения отдельных элементов из сетевого потока можно использовать пользовательский модуль форматирования веб\-канала синдикации, чтобы читаемый веб\-канал никогда не буферизовался в памяти целиком.  
  
 Для лучшей демонстрации возможности потоковой передачи API синдикации в этом образце используется достаточно нереальный сценарий, при котором сервер предоставляет веб\-канал с бесконечным числом элементов.В этом случае сервер продолжает создавать в веб\-канале новые элементы, пока он не определит, что клиент не прочитал из веб\-канала заданное число элементов \(по умолчанию — 10\).Для простоты клиент и служба реализованы в одном процессе и используют общий объект `ItemCounter` для отслеживания числа элементов, созданных клиентом.Тип `ItemCounter` нужен лишь для того, чтобы пример можно было верно завершить, и не является ключевым элементом демонстрируемого сценария.  
  
 В демонстрации используются итераторы [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] \(использующие ключевые слова `yield``return`\).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об итераторах см. в разделе «Использование итераторов» библиотеки MSDN.  
  
## Служба  
 Служба реализует базовый контракт <xref:System.ServiceModel.Web.WebGetAttribute>, состоящий из одной операции, как показано в следующем примере кода.  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
  
```  
  
 Служба реализует этот контракт с помощью класса `ItemGenerator`, создающего потенциально бесконечный поток экземпляров <xref:System.ServiceModel.Syndication.SyndicationItem> с использованием итератора, как показано в следующем примере кода.  
  
```  
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
  
 Когда реализация службы создает веб\-канал, вместо буферизованной коллекции элементов используется вывод метода `ItemGenerator.GenerateItems()`.  
  
```  
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
  
 В результате поток элементов никогда не помещается в буфер памяти целиком.Чтобы наблюдать за этим поведением, можно установить точку останова на операторе `yield``return` внутри метода `ItemGenerator.GenerateItems()`. При этом будет видно, что точка останова будет впервые достигнута после того, как служба возвратит результаты метода `StreamedFeed()`.  
  
## Клиент  
 Клиент в этом образце применяет пользовательскую реализацию <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>, которая задерживает воссоздание отдельных элементов в веб\-канале вместо их записи в буфер в памяти.Пользовательский экземпляр `StreamedAtom10FeedFormatter` используется следующим образом.  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
  
```  
  
 Обычно вызов метода <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> не завершается, пока будет прочитано из сети и записано в буфер в памяти все содержимое веб\-канала.Однако класс `StreamedAtom10FeedFormatter` переопределяет метод <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29>, чтобы вместо буферизованной коллекции он возвращал итератор, как показано в следующем примере кода.  
  
```  
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
  
 В результате элемент не будет прочитан из сети, пока клиентское приложение, через которое проходят результаты вызова метода `ReadItems()`, не будет готово к использованию этого элемента.Чтобы наблюдать за этим поведением, можно установить точку останова на операторе `yield``return` внутри метода `StreamedAtom10FeedFormatter.DelayReadItems()`. При этом будет видно, что точка останова будет впервые достигнута после завершения вызова метода `ReadFrom()`.  
  
 Ниже показано, как выполнить построение и запуск этого образца.Обратите внимание, что хотя сервер прекращает создание элементов после того, как клиент прочтет 10 элементов, результат работы программы показывает, что клиент прочитывает гораздо больше, чем 10 элементов.Это связано с тем, что используемая сетевая привязка передает данные фрагментами по 4 килобайта \(КБ\).Таким образом, клиент получает 4 КБ данных элемента раньше, чем он сможет прочитать хотя бы один элемент.Это нормальное поведение \(разбиение данных на небольшие фрагменты при их потоковой передаче по протоколу HTTP повышает производительность\).  
  
#### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## См. также  
 [Автономный веб\-канал диагностики](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)