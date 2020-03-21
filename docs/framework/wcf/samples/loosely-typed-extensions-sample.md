---
title: Пример слабо типизированных расширений
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: b8d1d42864b8764551cc44a26d820090eb28971e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183548"
---
# <a name="loosely-typed-extensions-sample"></a>Пример слабо типизированных расширений
Объектная модель синдикации обеспечивает широкую поддержку работы с данными расширения - информацией, присутствующей в XML-представлении канала синдикации, но не предоставляемой в явном виде такими классами, как <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>. Этот пример иллюстрирует основные приемы работы с данными расширения.  
  
 В этом примере используется класс <xref:System.ServiceModel.Syndication.SyndicationFeed>. Однако показанные в примере шаблоны можно использовать со всеми классами Syndication, которые поддерживают данные расширения:  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a>Образец XML  
 Для справки: в этом примере используется следующий XML-документ.  
  
```xml  
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
  
- Атрибут `myAttribute` элемента `<feed>`.  
  
- Элемент `<simpleString>`.  
  
- Элемент `<DataContractExtension>`.  
  
- Элемент `<XmlSerializerExtension>`.  
  
- Элемент `<xElementExtension>`.  
  
## <a name="writing-extension-data"></a>Запись данных расширений  
 Расширения атрибутов создаются путем добавления записей в коллекцию <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>, как показано в следующем образце кода.  
  
```csharp  
//Attribute extensions are stored in a dictionary indexed by
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 Расширения элементов создаются путем добавления записей в коллекцию <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. Эти расширения могут быть базовыми значениями, такими как строки, XML-сериализациями объектов платформы .NET Framework или XML-узлами, код которых написан вручную.  
  
 В следующем примере кода создается элемент расширения с именем `simpleString`.  
  
```csharp  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 Пространством имен XML для этого элемента является пустое пространство имен («» ), а его значение — текстовым узлам, содержащим строку «привет, мир!».  
  
 Одним из способов создания расширений сложных элементов, содержащий много вложенных элементов, является использование для сериализации интерфейсов API платформы .NET Framework (поддерживаются как <xref:System.Runtime.Serialization.DataContractSerializer>, так и <xref:System.Xml.Serialization.XmlSerializer>), как показано в следующих примерах.  
  
```csharp  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 В этом примере `DataContractExtension` и `XmlSerializerExtension` представляют собой пользовательские типы, созданные для использования с сериализатором.  
  
 Класс <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> также может использоваться для создания расширений элементов из экземпляра <xref:System.Xml.XmlReader>. Это обеспечивает простую интеграцию с интерфейсами API, обрабатывающими XML, такими как <xref:System.Xml.Linq.XElement>, как показано в следующем образце кода.  
  
```csharp  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a>Чтение данных расширений  
 Значения для расширений атрибутов можно получить, произведя поиск атрибута в коллекции <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> по его имени <xref:System.Xml.XmlQualifiedName>, как показано в следующем образце кода.  
  
```csharp  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 Для доступа к расширениям элементов служит метод `ReadElementExtensions<T>`.  
  
```csharp  
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
  
```csharp  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a>См. также раздел

- [Строго типизированные расширения](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)
- [Синдикация WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
