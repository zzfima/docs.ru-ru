---
title: "Как квалифицировать элемент XML и имена атрибутов XML | Microsoft Docs"
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
  - "указание элементов XML"
  - "указание имен элементов XML"
  - "пространства имен XML, указание элементов и имен элементов в"
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как квалифицировать элемент XML и имена атрибутов XML
[Пример кода](#cpconworkingwithxmlnamespacesanchor1)  
  
 Пространства имен XML, содержащиеся в экземплярах класса [XmlSerializerNamespaces](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic), должны соответствовать требованиям консорциума World Wide Web Consortium \(www.w3.org\) под названием «Пространства имен в XML».  
  
 Пространства имен XML предоставляют метод квалификации имен элементов XML и атрибутов XML в документах XML.Полное имя состоит из префикса и локального имени, разделяемых двоеточием.Функцией префикса является только указание места заполнения, он сопоставлен URI, определяющим пространство имен.Сочетание процедур универсально управляемого пространства имен URI и локального имени позволяет создать имя, гарантированно универсально уникальное.  
  
 Создавая экземпляр **XmlSerializerNamespaces** и добавляя пары пространств имен в объект, можно указать префиксы, используемые в документе XML.  
  
### Создание полных имен в документе XML  
  
1.  Создайте экземпляр класса **XmlSerializerNamespaces**.  
  
2.  Добавьте все пары префиксов и пространств имен в **XmlSerializerNamespaces**.  
  
3.  Примените соответствующий атрибут **System.Xml.Serialization** к каждому члену или классу, который [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) будет сериализовать в документ XML.  
  
     Доступные атрибуты: [XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic), [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic), [XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic), [XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic), [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic), [XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic) и [XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic).  
  
4.  Задайте свойство **Namespace** каждого атрибута как одно из значений пространства имен из **XmlSerializerNamespaces**.  
  
5.  Передайте **XmlSerializerNamespaces** в метод **Serialize**, принадлежащий **XmlSerializer**.  
  
## Пример  
 В следующем примере создается **XmlSerializerNamespaces**, и к нему добавляются две пары префикса и пространства имен.Код создает **XmlSerializer**, который используется для сериализации экземпляра класса `Books`.Код вызывает метод **Serialize** с использованием **XmlSerializerNamespaces**, что позволяет XML содержать пространства имен с префиксами.  
  
```vb  
Option Explicit   
public class Price  
{  
    [XmlAttribute(Namespace = "http://www.cpandl.com")]  
    public string currency;  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public decimal price;  
}  
  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Serialization  
  
Public Class Run  
  
    Public Shared Sub Main()  
        Dim test As New Run()  
        test.SerializeObject("XmlNamespaces.xml")  
    End Sub 'Main  
  
    Public Sub SerializeObject(filename As String)  
        Dim mySerializer As New XmlSerializer(GetType(Books))  
        ' Writing a file requires a TextWriter.  
        Dim myWriter As New StreamWriter(filename)  
  
        ' Creates an XmlSerializerNamespaces and adds two  
        ' prefix-namespace pairs.   
        Dim myNamespaces As New XmlSerializerNamespaces()  
        myNamespaces.Add("books", "http://www.cpandl.com")  
        myNamespaces.Add("money", "http://www.cohowinery.com")  
  
        ' Creates a Book.  
        Dim myBook As New Book()  
        myBook.TITLE = "A Book Title"  
        Dim myPrice As New Price()  
        myPrice.price = CDec(9.95)  
        myPrice.currency = "US Dollar"  
        myBook.PRICE = myPrice  
        Dim myBooks As New Books()  
        myBooks.Book = myBook  
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)  
        myWriter.Close()  
    End Sub  
End Class  
  
Public Class Books  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public Book As Book  
End Class 'Books  
  
<XmlType([Namespace] := "http://www.cpandl.com")> _  
Public Class Book  
  
    <XmlElement([Namespace] := "http://www.cpandl.com")> _  
    Public TITLE As String  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public PRICE As Price  
End Class  
  
Public Class Price  
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _  
    Public currency As String  
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
        price As Decimal  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeObject("XmlNamespaces.xml");  
    }  
    public void SerializeObject(string filename)  
    {  
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));  
        // Writing a file requires a TextWriter.  
        TextWriter myWriter = new StreamWriter(filename);  
  
        // Creates an XmlSerializerNamespaces and adds two  
        // prefix-namespace pairs.  
        XmlSerializerNamespaces myNamespaces =   
        new XmlSerializerNamespaces();  
        myNamespaces.Add("books", "http://www.cpandl.com");  
        myNamespaces.Add("money", "http://www.cohowinery.com");  
  
        // Creates a Book.  
        Book myBook = new Book();  
        myBook.TITLE = "A Book Title";  
        Price myPrice = new Price();  
        myPrice.price = (decimal) 9.95;  
        myPrice.currency = "US Dollar";  
        myBook.PRICE = myPrice;  
        Books myBooks = new Books();  
        myBooks.Book = myBook;  
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);  
        myWriter.Close();  
    }  
}  
  
public class Books  
{  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public Book Book;  
}  
  
[XmlType(Namespace ="http://www.cpandl.com")]  
public class Book  
{  
    [XmlElement(Namespace = "http://www.cpandl.com")]  
    public string TITLE;  
    [XmlElement(Namespace ="http://www.cohowinery.com")]  
    public Price PRICE;  
}  
```  
  
## См. также  
 [Инструмент определения схемы XML и сериализация XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [XmlSerializer Class](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Атрибуты управления XML\-сериализацией](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)   
 [XmlSerializerNamespaces Class](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic)   
 [Как указать имя альтернативного элемента для потока XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)