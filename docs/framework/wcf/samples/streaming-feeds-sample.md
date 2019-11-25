---
title: Пример потоковой передачи каналов
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: ede1dbb4f5c682b8182dda4888a9cbd373b95dd8
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976374"
---
# <a name="streaming-feeds-sample"></a>Пример потоковой передачи каналов
В этом образце показано, как управлять веб-каналами синдикации, содержащими большое число элементов. На стороне сервера этот пример показывает, как откладывать создание отдельных объектов <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канале до момента записи элемента в сетевой поток.  
  
 На стороне клиента этот пример показывает, что для чтения отдельных элементов из сетевого потока можно использовать пользовательский модуль форматирования веб-канала синдикации, чтобы читаемый веб-канал никогда не буферизовался в памяти целиком.  
  
 Для лучшей демонстрации возможности потоковой передачи API синдикации в этом образце используется достаточно нереальный сценарий, при котором сервер предоставляет веб-канал с бесконечным числом элементов. В этом случае сервер продолжает создавать в веб-канале новые элементы, пока он не определит, что клиент не прочитал из веб-канала заданное число элементов (по умолчанию - 10). Для простоты клиент и служба реализованы в одном процессе и используют общий объект `ItemCounter` для отслеживания числа элементов, созданных клиентом. Тип `ItemCounter` нужен лишь для того, чтобы пример можно было верно завершить, и не является ключевым элементом демонстрируемого сценария.  
  
 В демонстрации используются визуальные C# итераторы (с использованием `yield return` конструкции ключевого слова). Дополнительные сведения о итераторах см. в разделе "использование итераторов" на сайте MSDN.  
  
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
  
 В результате поток элементов никогда не помещается в буфер памяти целиком. Это поведение можно проследить, установив точку останова в операторе `yield return` в методе `ItemGenerator.GenerateItems()` и отметив, что эта точка останова встречается в первый раз после того, как служба возвращала результат метода `StreamedFeed()`.  
  
## <a name="client"></a>"Клиент";  
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
  
 В результате элемент не будет прочитан из сети, пока клиентское приложение, через которое проходят результаты вызова метода `ReadItems()`, не будет готово к использованию этого элемента. Это поведение можно проследить, установив точку останова в операторе `yield return` в `StreamedAtom10FeedFormatter.DelayReadItems()` и убедившись в том, что эта точка останова встречается в первый раз после завершения вызова `ReadFrom()`.  
  
 Ниже показано, как выполнить построение и запуск этого образца. Обратите внимание, что хотя сервер прекращает создание элементов после того, как клиент прочтет 10 элементов, результат работы программы показывает, что клиент прочитывает гораздо больше, чем 10 элементов. Это связано с тем, что используемая сетевая привязка передает данные фрагментами по 4 килобайта (КБ). Таким образом, клиент получает 4 КБ данных элемента раньше, чем он сможет прочитать хотя бы один элемент. Это нормальное поведение (разбиение данных на небольшие фрагменты при их потоковой передаче по протоколу HTTP повышает производительность).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a>См. также

- [Автономный веб-канал диагностики](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
