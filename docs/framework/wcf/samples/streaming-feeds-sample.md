---
title: Пример потоковой передачи каналов
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 7a887fa1eceac4d8ee323f03fd5bc536bb1dc579
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143971"
---
# <a name="streaming-feeds-sample"></a>Пример потоковой передачи каналов
В этом образце показано, как управлять веб-каналами синдикации, содержащими большое число элементов. На стороне сервера этот пример показывает, как откладывать создание отдельных объектов <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канале до момента записи элемента в сетевой поток.  
  
 На стороне клиента этот пример показывает, что для чтения отдельных элементов из сетевого потока можно использовать пользовательский модуль форматирования веб-канала синдикации, чтобы читаемый веб-канал никогда не буферизовался в памяти целиком.  
  
 Для лучшей демонстрации возможности потоковой передачи API синдикации в этом образце используется достаточно нереальный сценарий, при котором сервер предоставляет веб-канал с бесконечным числом элементов. В этом случае сервер продолжает создавать в веб-канале новые элементы, пока он не определит, что клиент не прочитал из веб-канала заданное число элементов (по умолчанию - 10). Для простоты клиент и служба реализованы в одном процессе и используют общий объект `ItemCounter` для отслеживания числа элементов, созданных клиентом. Тип `ItemCounter` нужен лишь для того, чтобы пример можно было верно завершить, и не является ключевым элементом демонстрируемого сценария.  
  
 Демонстрация использует итераторы Visual C '( используя конструкцию ключевого `yield return` слова). Для получения дополнительной информации о итераторах, см.  
  
## <a name="service"></a>Служба  
 Служба реализует базовый контракт <xref:System.ServiceModel.Web.WebGetAttribute>, состоящий из одной операции, как показано в следующем примере кода.  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 Служба реализует этот контракт с помощью класса `ItemGenerator`, создающего потенциально бесконечный поток экземпляров <xref:System.ServiceModel.Syndication.SyndicationItem> с использованием итератора, как показано в следующем примере кода.  
  
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
  
 Когда реализация службы создает веб-канал, вместо буферизованной коллекции элементов используется вывод метода `ItemGenerator.GenerateItems()`.  
  
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
  
 В результате поток элементов никогда не помещается в буфер памяти целиком. Вы можете наблюдать это поведение, установив `yield return` точку `ItemGenerator.GenerateItems()` разрыва на выписке внутри метода и отметив, что эта точка `StreamedFeed()` разрыва возникает впервые после того, как служба вернула результат метода.  
  
## <a name="client"></a>клиент  
 Клиент в этом образце применяет пользовательскую реализацию <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>, которая задерживает воссоздание отдельных элементов в веб-канале вместо их записи в буфер в памяти. Пользовательский экземпляр `StreamedAtom10FeedFormatter` используется следующим образом.  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 Обычно вызов метода <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> не завершается, пока будет прочитано из сети и записано в буфер в памяти все содержимое веб-канала. Однако класс `StreamedAtom10FeedFormatter` переопределяет метод <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29>, чтобы вместо буферизованной коллекции он возвращал итератор, как показано в следующем примере кода.  
  
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
  
 В результате элемент не будет прочитан из сети, пока клиентское приложение, через которое проходят результаты вызова метода `ReadItems()`, не будет готово к использованию этого элемента. Вы можете наблюдать это поведение, установив `yield return` точку `StreamedAtom10FeedFormatter.DelayReadItems()` разрыва на выписке внутри и заметив, что `ReadFrom()` эта точка разрыва встречается впервые после вызова для завершения.  
  
 Ниже показано, как выполнить построение и запуск этого образца. Обратите внимание, что хотя сервер прекращает создание элементов после того, как клиент прочтет 10 элементов, результат работы программы показывает, что клиент прочитывает гораздо больше, чем 10 элементов. Это связано с тем, что используемая сетевая привязка передает данные фрагментами по 4 килобайта (КБ). Таким образом, клиент получает 4 КБ данных элемента раньше, чем он сможет прочитать хотя бы один элемент. Это нормальное поведение (разбиение данных на небольшие фрагменты при их потоковой передаче по протоколу HTTP повышает производительность).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a>См. также раздел

- [Автономный веб-канал диагностики](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
