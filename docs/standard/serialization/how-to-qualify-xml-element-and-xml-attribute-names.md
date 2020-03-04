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
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="9d197-102">Как квалифицировать XML-элемент и имена атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="9d197-102">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="9d197-103">Пространства имен XML, содержащиеся в экземплярах класса <xref:System.Xml.Serialization.XmlSerializerNamespaces>, должны соответствовать спецификации консорциум W3C (W3C), именуемой [пространствами имен в XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="9d197-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="9d197-104">Пространства имен XML предоставляют метод квалификации имен элементов XML и атрибутов XML в документах XML.</span><span class="sxs-lookup"><span data-stu-id="9d197-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="9d197-105">Полное имя состоит из префикса и локального имени, разделяемых двоеточием.</span><span class="sxs-lookup"><span data-stu-id="9d197-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="9d197-106">Функцией префикса является только указание места заполнения, он сопоставлен URI, определяющим пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9d197-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="9d197-107">Сочетание процедур универсально управляемого пространства имен URI и локального имени позволяет создать имя, гарантированно универсально уникальное.</span><span class="sxs-lookup"><span data-stu-id="9d197-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="9d197-108">Создавая экземпляр `XmlSerializerNamespaces` и добавляя пары пространств имен в объект, можно указать префиксы, используемые в документе XML.</span><span class="sxs-lookup"><span data-stu-id="9d197-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="9d197-109">Создание полных имен в документе XML</span><span class="sxs-lookup"><span data-stu-id="9d197-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="9d197-110">Создайте экземпляр класса `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="9d197-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="9d197-111">Добавьте все пары префиксов и пространств имен в `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="9d197-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="9d197-112">Примените соответствующий атрибут `System.Xml.Serialization` к каждому члену или классу, который <xref:System.Xml.Serialization.XmlSerializer> будет сериализовать в документ XML.</span><span class="sxs-lookup"><span data-stu-id="9d197-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="9d197-113">Доступные атрибуты: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9d197-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="9d197-114">Задайте свойство `Namespace` каждого атрибута как одно из значений пространства имен из `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="9d197-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="9d197-115">Передайте `XmlSerializerNamespaces` в метод `Serialize`, принадлежащий `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="9d197-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="9d197-116">Пример</span><span class="sxs-lookup"><span data-stu-id="9d197-116">Example</span></span>

<span data-ttu-id="9d197-117">В следующем примере создается `XmlSerializerNamespaces`, и к нему добавляются две пары префикса и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9d197-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="9d197-118">Код создает `XmlSerializer`, который используется для сериализации экземпляра класса `Books`.</span><span class="sxs-lookup"><span data-stu-id="9d197-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="9d197-119">Код вызывает метод `Serialize` с использованием `XmlSerializerNamespaces`, что позволяет XML содержать пространства имен с префиксами.</span><span class="sxs-lookup"><span data-stu-id="9d197-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9d197-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9d197-120">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="9d197-121">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="9d197-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="9d197-122">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="9d197-122">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="9d197-123">Класс XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="9d197-123">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="9d197-124">Атрибуты управления сериализацией XML</span><span class="sxs-lookup"><span data-stu-id="9d197-124">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="9d197-125">Практическое руководство. Указание имени альтернативного элемента для потока XML</span><span class="sxs-lookup"><span data-stu-id="9d197-125">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="9d197-126">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="9d197-126">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="9d197-127">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="9d197-127">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
