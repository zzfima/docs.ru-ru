---
title: Как квалифицировать XML-элемент и имена атрибутов XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: db0795dd83cc96aba49dd435c875e98a9a6c18cb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159875"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a>Как квалифицировать XML-элемент и имена атрибутов XML

Пространства имен XML, содержащиеся в экземплярах класса <xref:System.Xml.Serialization.XmlSerializerNamespaces>, должны соответствовать спецификации консорциум W3C (W3C), именуемой [пространствами имен в XML](https://www.w3.org/TR/REC-xml-names/).

Пространства имен XML предоставляют метод квалификации имен элементов XML и атрибутов XML в документах XML. Полное имя состоит из префикса и локального имени, разделяемых двоеточием. Функцией префикса является только указание места заполнения, он сопоставлен URI, определяющим пространство имен. Сочетание процедур универсально управляемого пространства имен URI и локального имени позволяет создать имя, гарантированно универсально уникальное.

Создавая экземпляр `XmlSerializerNamespaces` и добавляя пары пространств имен в объект, можно указать префиксы, используемые в документе XML.

## <a name="to-create-qualified-names-in-an-xml-document"></a>Создание полных имен в документе XML

1. Создайте экземпляр класса `XmlSerializerNamespaces`.

2. Добавьте все пары префиксов и пространств имен в `XmlSerializerNamespaces`.

3. Примените соответствующий атрибут `System.Xml.Serialization` к каждому члену или классу, который <xref:System.Xml.Serialization.XmlSerializer> будет сериализовать в документ XML.

    Доступные атрибуты: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.

4. Задайте свойство `Namespace` каждого атрибута как одно из значений пространства имен из `XmlSerializerNamespaces`.

5. Передайте `XmlSerializerNamespaces` в метод `Serialize`, принадлежащий `XmlSerializer`.

## <a name="example"></a>Пример

В следующем примере создается `XmlSerializerNamespaces`, и к нему добавляются две пары префикса и пространства имен. Код создает `XmlSerializer`, который используется для сериализации экземпляра класса `Books`. Код вызывает метод `Serialize` с использованием `XmlSerializerNamespaces`, что позволяет XML содержать пространства имен с префиксами.

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

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
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

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
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }

    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
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

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Serialization.XmlSerializer>
- [Инструмент определения схемы XML и сериализация XML](the-xml-schema-definition-tool-and-xml-serialization.md)
- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Класс XmlSerializer](xref:System.Xml.Serialization.XmlSerializer)
- [Атрибуты управления сериализацией XML](attributes-that-control-xml-serialization.md)
- [Практическое руководство. Указание имени альтернативного элемента для потока XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
