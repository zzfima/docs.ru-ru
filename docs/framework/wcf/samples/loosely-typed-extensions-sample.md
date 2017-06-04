---
title: "Образец слабо типизированных расширений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Образец слабо типизированных расширений
Объектная модель синдикации обеспечивает широкую поддержку работы с данными расширения — информацией, присутствующей в XML\-представлении канала синдикации, но не предоставляемой в явном виде такими классами, как <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>.Этот образец иллюстрирует основные приемы работы с данными расширения.  
  
 В этом образце используется класс <xref:System.ServiceModel.Syndication.SyndicationFeed>.Однако показанные в образце шаблоны можно использовать со всеми классами Syndication, которые поддерживают данные расширения:  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## Образец XML  
 Для справки: в этом образце используется следующий XML\-документ.  
  
```  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
  
```  
  
 Этот документ содержит следующие части данных расширения:  
  
-   Атрибут `myAttribute` элемента `<feed>`.  
  
-   Элемент `<simpleString>`.  
  
-   Элемент `<DataContractExtension>`.  
  
-   Элемент `<XmlSerializerExtension>`.  
  
-   Элемент `<xElementExtension>`.  
  
## Запись данных расширений  
 Расширения атрибутов создаются путем добавления записей в коллекцию <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>, как показано в следующем образце кода.  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
  
```  
  
 Расширения элементов создаются путем добавления записей в коллекцию <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.Эти расширения могут быть базовыми значениями, такими как строки, XML\-сериализациями объектов платформы .NET Framework или XML\-узлами, код которых написан вручную.  
  
 В следующем примере кода создается элемент расширения с именем `simpleString`.  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
  
```  
  
 Пространство имен XML для этого элемента представляет собой пустое пространство имен \(""\), а его значением является текстовый узел, содержащий строку "hello, world\!".  
  
 Одним из способов создания расширений сложных элементов, содержащий много вложенных элементов, является использование для сериализации интерфейсов API платформы .NET Framework \(поддерживаются как <xref:System.Runtime.Serialization.DataContractSerializer>, так и <xref:System.Xml.Serialization.XmlSerializer>\), как показано в следующих примерах.  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
  
```  
  
 В этом примере `DataContractExtension` и `XmlSerializerExtension` представляют собой пользовательские типы, созданные для использования с сериализатором.  
  
 Класс <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> также может использоваться для создания расширений элементов из экземпляра <xref:System.Xml.XmlReader>.Это обеспечивает простую интеграцию с интерфейсами API, обрабатывающими XML, такими как <xref:System.Xml.Linq.XElement>, как показано в следующем образце кода.  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
  
```  
  
## Чтение данных расширений  
 Значения для расширений атрибутов можно получить, произведя поиск атрибута в коллекции <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> по его имени <xref:System.Xml.XmlQualifiedName>, как показано в следующем образце кода.  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
  
```  
  
 Для доступа к расширениям элементов служит метод `ReadElementExtensions<T>`.  
  
```  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
  
```  
  
 Можно также получить средство чтения `XmlReader` для расширений отдельных элементов с помощью метода <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>.  
  
```  
  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
  
```  
  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## См. также  
 [Строго типизированные расширения](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)   
 [Синдикация WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)