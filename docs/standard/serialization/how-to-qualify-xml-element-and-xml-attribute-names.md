---
title: Практическое руководство. Квалификация элемента XML и имен атрибутов XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 6b4d58f6b5bf23cbce2ace8fb40730d7b73994de
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930886"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="22ee1-102">Практическое руководство. Квалификация элемента XML и имен атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="22ee1-102">How to: Qualify XML Element and XML Attribute Names</span></span>

<span data-ttu-id="22ee1-103">Пространства имен XML, содержащиеся в экземплярах <xref:System.Xml.Serialization.XmlSerializerNamespaces> класса должно соответствовать спецификации World Wide Web Consortium (W3C), который вызывается [пространства имен в XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="22ee1-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="22ee1-104">Пространства имен XML предоставляют метод квалификации имен элементов XML и атрибутов XML в документах XML.</span><span class="sxs-lookup"><span data-stu-id="22ee1-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="22ee1-105">Полное имя состоит из префикса и локального имени, разделяемых двоеточием.</span><span class="sxs-lookup"><span data-stu-id="22ee1-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="22ee1-106">Функцией префикса является только указание места заполнения, он сопоставлен URI, определяющим пространство имен.</span><span class="sxs-lookup"><span data-stu-id="22ee1-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="22ee1-107">Сочетание процедур универсально управляемого пространства имен URI и локального имени позволяет создать имя, гарантированно универсально уникальное.</span><span class="sxs-lookup"><span data-stu-id="22ee1-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="22ee1-108">Создавая экземпляр `XmlSerializerNamespaces` и добавляя пары пространств имен в объект, можно указать префиксы, используемые в документе XML.</span><span class="sxs-lookup"><span data-stu-id="22ee1-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="22ee1-109">Создание полных имен в документе XML</span><span class="sxs-lookup"><span data-stu-id="22ee1-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="22ee1-110">Создайте экземпляр класса `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="22ee1-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="22ee1-111">Добавьте все пары префиксов и пространств имен в `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="22ee1-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="22ee1-112">Примените соответствующий атрибут `System.Xml.Serialization` к каждому члену или классу, который <xref:System.Xml.Serialization.XmlSerializer> будет сериализовать в документ XML.</span><span class="sxs-lookup"><span data-stu-id="22ee1-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

  <span data-ttu-id="22ee1-113">Доступные атрибуты: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="22ee1-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="22ee1-114">Задайте свойство `Namespace` каждого атрибута как одно из значений пространства имен из `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="22ee1-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="22ee1-115">Передайте `XmlSerializerNamespaces` в метод `Serialize`, принадлежащий `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="22ee1-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="22ee1-116">Пример</span><span class="sxs-lookup"><span data-stu-id="22ee1-116">Example</span></span>

<span data-ttu-id="22ee1-117">В следующем примере создается `XmlSerializerNamespaces`, и к нему добавляются две пары префикса и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="22ee1-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="22ee1-118">Код создает `XmlSerializer`, который используется для сериализации экземпляра класса `Books`.</span><span class="sxs-lookup"><span data-stu-id="22ee1-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="22ee1-119">Код вызывает метод `Serialize` с использованием `XmlSerializerNamespaces`, что позволяет XML содержать пространства имен с префиксами.</span><span class="sxs-lookup"><span data-stu-id="22ee1-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="22ee1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="22ee1-120">See Also</span></span>

<span data-ttu-id="22ee1-121"><xref:System.Xml.Serialization.XmlSerializer>
[Инструмент определения схемы XML и сериализация XML](the-xml-schema-definition-tool-and-xml-serialization.md)
[введение в сериализацию XML](introducing-xml-serialization.md)
[класс XmlSerializer](xref:System.Xml.Serialization.XmlSerializer) 
 [Атрибуты управления сериализацией XML](attributes-that-control-xml-serialization.md)
[как: Указание имени альтернативного элемента для XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
[как: сериализация объекта](how-to-serialize-an-object.md) 
 [Как: десериализации объекта](how-to-deserialize-an-object.md)</span><span class="sxs-lookup"><span data-stu-id="22ee1-121"><xref:System.Xml.Serialization.XmlSerializer>
[The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md)
[Introducing XML Serialization](introducing-xml-serialization.md)
[XmlSerializer Class](xref:System.Xml.Serialization.XmlSerializer)
[Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md)
[How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
[How to: Serialize an Object](how-to-serialize-an-object.md)
[How to: Deserialize an Object](how-to-deserialize-an-object.md)</span></span>