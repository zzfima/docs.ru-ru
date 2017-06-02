---
title: "Как указать имя альтернативного элемента для потока XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "классы, переопределение"
  - "переопределение классов"
  - "переопределение XML-сериализации"
  - "сериализация, переопределение"
  - "XML-сериализация, переопределение"
  - "XML-поток, указание имени альтернативного элемента для"
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как указать имя альтернативного элемента для потока XML
[Пример кода](#cpconoverridingserializationofclasseswithxmlattributeoverridesclassanchor1)  
  
 Используя [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx), можно создать несколько потоков XML с одним и тем же набором классов.Это может понадобиться, поскольку для двух разных XML\-веб\-служб требуется одинаковая основная информация с незначительными различиями.Допустим, две XML\-веб\-службы обрабатывают заказы на книги, и поэтому для каждой из них требуются номера ISBN.Одна служба использует тег \<ISBN\>, а другая — тег \<BookID\>.Имеется класс с именем `Book`, содержащий поле с именем `ISBN`.При сериализации экземпляра класса `Book` имя члена \(ISBN\) будет по умолчанию использоваться в качестве имени элемента для тега.Первая XML\-веб\-служба работает, как и предполагалось.Но чтобы отправить поток XML во вторую XML\-веб\-службу, необходимо переопределить сериализацию, чтобы именем элемента для тега стало `BookID`.  
  
### Создание потока XML с именем альтернативного элемента  
  
1.  Создайте экземпляр класса [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic).  
  
2.  Задайте <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> атрибута <xref:System.Xml.Serialization.XmlElementAttribute> как "BookID".  
  
3.  Создайте экземпляр класса [XmlAttributes](frlrfSystemXmlSerializationXmlAttributesClassTopic).  
  
4.  Добавьте объект **XmlElementAttribute** в коллекцию, доступ к которой осуществляется через свойство <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> атрибута <xref:System.Xml.Serialization.XmlAttributes>.  
  
5.  Создайте экземпляр класса [XmlAttributeOverrides](frlrfSystemXmlSerializationXmlAttributeOverridesClassTopic).  
  
6.  Добавьте **XmlAttributes** к <xref:System.Xml.Serialization.XmlAttributeOverrides>, передавая тип переопределяемого объекта и имя переопределяемого члена.  
  
7.  Создайте экземпляр класса **XmlSerializer** с **XmlAttributeOverrides**.  
  
8.  Создайте экземпляр класса `Book`, сериализуйте или десериализуйте его.  
  
## Пример  
  
```vb  
Public Class SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
  
```  
  
```csharp  
public class SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 Поток XML может иметь следующий вид.  
  
```  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## См. также  
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic)   
 [XmlAttributes](frlrfSystemXmlSerializationXmlAttributesClassTopic)   
 [XmlAttributeOverrides](frlrfSystemXmlSerializationXmlAttributeOverridesClassTopic)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)