---
title: Пример строго типизированных расширений
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: 4ad0a8e10ecbcb5e3ddf9106dbbaa55356314020
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716622"
---
# <a name="strongly-typed-extensions-sample"></a>Пример строго типизированных расширений
В этом примере используется класс <xref:System.ServiceModel.Syndication.SyndicationFeed>. Однако показанные в примере шаблоны можно использовать со всеми классами Syndication, которые поддерживают данные расширения.  
  
 Объектная модель синдикации (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> и связанные классы) поддерживает слабо типизированный доступ к данным расширений с использованием свойств <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> и <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. В этом образце показано, как обеспечить строго типизированный доступ к данным расширений, реализовав пользовательские производные классы для классов <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>, чтобы сделать доступными в виде строго типизированных свойств некоторые относящиеся к конкретным приложениям расширения.  
  
 Например, здесь показано, как реализовать элемент расширения, определенный в документе RFC "Atom Threading Extensions". Этот образец приводится исключительно с целью демонстрации и не является полной реализацией предлагаемой спецификации.  
  
## <a name="sample-xml"></a>Образец XML  
 В следующем примере XML показана запись Atom 1.0 с дополнительным элементом расширения `<in-reply-to>`.  
  
```xml  
<entry>  
    <id>tag:example.org,2005:1,2</id>  
    <title type="text">Another response to the original</title>  
    <summary type="text">  
         This is a response to the original entry</summary>  
    <updated>2006-03-01T12:12:13Z</updated>  
    <link href="http://www.example.org/entries/1/2" />  
    <in-reply-to p3:ref="tag:example.org,2005:1"   
                 p3:href="http://www.example.org/entries/1"   
                 p3:type="application/xhtml+xml"   
                 xmlns:p3="http://contoso.org/syndication/thread/1.0"   
                 xmlns="http://contoso.org/syndication/thread/1.0">  
      <anotherElement xmlns="http://www.w3.org/2005/Atom">  
                     Some more data</anotherElement>  
      <aDifferentElement xmlns="http://www.w3.org/2005/Atom">  
                     Even more data</aDifferentElement>  
    </in-reply-to>  
</entry>  
```  
  
 Элемент `<in-reply-to>` задает три обязательных атрибута (`ref`, `type` и `href`), а также разрешение на присутствие дополнительных атрибутов расширения и элементов расширения.  
  
## <a name="modeling-the-in-reply-to-element"></a>Моделирование элемента In-Reply-To  
 В этом образце элемент `<in-reply-to>` моделируется в среде CLR, которая реализует интерфейс <xref:System.Xml.Serialization.IXmlSerializable>, позволяющий использовать его с <xref:System.Runtime.Serialization.DataContractSerializer>. Кроме того, в образце реализованы методы и свойства для доступа к данным элемента, как показано в следующем образце кода.  
  
```csharp  
[XmlRoot(ElementName = "in-reply-to", Namespace = "http://contoso.org/syndication/thread/1.0")]  
public class InReplyToElement : IXmlSerializable  
{  
    internal const string ElementName = "in-reply-to";  
    internal const string NsUri =   
                  "http://contoso.org/syndication/thread/1.0";  
    private Dictionary<XmlQualifiedName, string> extensionAttributes;  
    private Collection<XElement> extensionElements;  
  
    public InReplyToElement()  
    {  
        this.extensionElements = new Collection<XElement>();  
        this.extensionAttributes = new Dictionary<XmlQualifiedName,   
                                                          string>();  
    }  
  
    public Dictionary<XmlQualifiedName, string> AttributeExtensions  
    {  
        get { return this.extensionAttributes; }  
    }  
  
    public Collection<XElement> ElementExtensions  
    {  
        get { return this.extensionElements; }  
    }  
  
    public Uri Href  
    { get; set; }  
  
    public string MediaType  
    { get; set; }  
  
    public string Ref  
    { get; set; }  
  
    public Uri Source  
    { get; set; }  
}  
```  
  
 Класс `InReplyToElement` реализует свойства для обязательного атрибута (`HRef`, `MediaType` и `Source`), а также коллекцию для хранения расширений <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> и <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.  
  
 Класс `InReplyToElement` реализует интерфейс <xref:System.Xml.Serialization.IXmlSerializable>, который позволяет напрямую управлять тем, как экземпляры объектов считываются из XML и записываются в XML. Метод `ReadXml` сначала считывает значения свойств `Ref`, `HRef`, `Source` и `MediaType` из переданного ему объекта <xref:System.Xml.XmlReader>. Все неизвестные атрибуты хранятся в коллекции <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>. После чтения всех атрибутов вызывается метод <xref:System.Xml.XmlReader.ReadStartElement>, чтобы перевести средство чтения к следующему элементу. Поскольку у моделируемого этим классом элемента нет обязательных дочерних элементов, дочерние элементы буферизуются в экземплярах `XElement` и хранятся в коллекции <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, как показано в следующем примере кода.  
  
```csharp
public void ReadXml(System.Xml.XmlReader reader)  
{  
    bool isEmpty = reader.IsEmptyElement;  
  
    if (reader.HasAttributes)  
    {  
        for (int i = 0; i < reader.AttributeCount; i++)  
        {  
            reader.MoveToNextAttribute();  
  
            if (reader.NamespaceURI == "")  
            {  
                if (reader.LocalName == "ref")  
                {  
                    this.Ref = reader.Value;  
                }  
                else if (reader.LocalName == "href")  
                {  
                    this.Href = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "source")  
                {  
                    this.Source = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "type")  
                {  
                    this.MediaType = reader.Value;  
                }  
                else  
                {  
                    this.AttributeExtensions.Add(new   
                                 XmlQualifiedName(reader.LocalName,   
                                 reader.NamespaceURI),   
                                 reader.Value);  
                }  
            }  
        }  
    }  
  
    reader.ReadStartElement();  
  
    if (!isEmpty)  
    {  
        while (reader.IsStartElement())  
        {  
            ElementExtensions.Add(  
                  (XElement) XElement.ReadFrom(reader));  
        }  
        reader.ReadEndElement();  
    }  
}  
```  
  
 В `WriteXml` в методе `InReplyToElement` сначала записывает значения из свойств `Ref`, `HRef`, `Source` и `MediaType` в виде атрибутов XML (`WriteXml` не отвечает за запись самого внешнего элемента, поскольку это делает сторона, вызывающая `WriteXml`). Кроме того, он записывает содержимое свойств <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> и <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> в средство записи, как показано в следующем примере кода.  
  
```csharp
public void WriteXml(System.Xml.XmlWriter writer)  
{  
    if (this.Ref != null)  
    {  
        writer.WriteAttributeString("ref", InReplyToElement.NsUri,   
                                            this.Ref);  
    }  
    if (this.Href != null)  
    {  
        writer.WriteAttributeString("href", InReplyToElement.NsUri,   
                                                this.Href.ToString());  
    }  
    if (this.Source != null)  
    {  
        writer.WriteAttributeString("source", InReplyToElement.NsUri,   
                                              this.Source.ToString());  
    }  
    if (this.MediaType != null)  
    {  
        writer.WriteAttributeString("type", InReplyToElement.NsUri,   
                                                    this.MediaType);  
    }  
  
    foreach (KeyValuePair<XmlQualifiedName, string> kvp in   
                                             this.AttributeExtensions)  
    {  
        writer.WriteAttributeString(kvp.Key.Name, kvp.Key.Namespace,   
                                                   kvp.Value);  
    }  
  
    foreach (XElement element in this.ElementExtensions)  
    {  
        element.WriteTo(writer);  
    }  
}  
```  
  
## <a name="threadedfeed-and-threadeditem"></a>ThreadedFeed и ThreadedItem  
 В этом образце элементы `SyndicationItems` с расширениями `InReplyTo` моделируются с помощью класса `ThreadedItem`. Аналогично класс `ThreadedFeed` является каналом `SyndicationFeed`, элементы которого являются экземплярами `ThreadedItem`.  
  
 Класс `ThreadedFeed` наследует классу `SyndicationFeed` и переопределяет метод `OnCreateItem`, чтобы он возвращал элементы `ThreadedItem`. Кроме того, он реализует метод для доступа к коллекции `Items` в виде `ThreadedItems`, как показано в следующем примере кода.  
  
```csharp
public class ThreadedFeed : SyndicationFeed  
{  
    public ThreadedFeed()  
    {  
    }  
  
    public IEnumerable<ThreadedItem> ThreadedItems  
    {  
        get  
        {  
            return this.Items.Cast<ThreadedItem>();  
        }  
    }  
  
    protected override SyndicationItem CreateItem()  
    {  
        return new ThreadedItem();  
    }  
}  
```  
  
 Класс `ThreadedItem` наследует классу `SyndicationItem` и делает элемент `InReplyToElement` строго типизированным свойством. Это делает возможным удобный программный доступ к данным расширений `InReplyTo`. Кроме того, он реализует методы `TryParseElement` и `WriteElementExtensions` для чтения и записи данных расширений, как показано в следующем примере кода.  
  
```csharp
public class ThreadedItem : SyndicationItem  
{  
    private InReplyToElement inReplyTo;  
    // Constructors  
        public ThreadedItem()  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
        public ThreadedItem(string title, string content, Uri itemAlternateLink, string id, DateTimeOffset lastUpdatedTime) : base(title, content, itemAlternateLink, id, lastUpdatedTime)  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
    public InReplyToElement InReplyTo  
    {  
        get { return this.inReplyTo; }  
    }  
  
    protected override bool TryParseElement(  
                        System.Xml.XmlReader reader,   
                        string version)  
    {  
        if (version == SyndicationVersions.Atom10 &&  
            reader.NamespaceURI == InReplyToElement.NsUri &&  
            reader.LocalName == InReplyToElement.ElementName)  
        {  
            this.inReplyTo = new InReplyToElement();  
  
            this.InReplyTo.ReadXml(reader);  
  
            return true;  
        }  
        else  
        {  
            return base.TryParseElement(reader, version);  
        }  
    }  
  
    protected override void WriteElementExtensions(XmlWriter writer,   
                                                 string version)  
    {  
        if (this.InReplyTo != null &&   
                     version == SyndicationVersions.Atom10)  
        {  
            writer.WriteStartElement(InReplyToElement.ElementName,   
                                           InReplyToElement.NsUri);  
            this.InReplyTo.WriteXml(writer);  
            writer.WriteEndElement();  
        }  
  
        base.WriteElementExtensions(writer, version);  
    }  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
