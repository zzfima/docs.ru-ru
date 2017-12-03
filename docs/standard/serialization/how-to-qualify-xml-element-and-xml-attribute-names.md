---
title: "Практическое руководство. Квалификация элемента XML и имен атрибутов XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e94b9022e6da29f0aa8deb5534fec6e89d40152a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="cf0aa-102">Практическое руководство. Квалификация элемента XML и имен атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-102">How to: Qualify XML Element and XML Attribute Names</span></span>
[<span data-ttu-id="cf0aa-103">Пример кода</span><span class="sxs-lookup"><span data-stu-id="cf0aa-103">Code Example</span></span>](#cpconworkingwithxmlnamespacesanchor1)  
  
 <span data-ttu-id="cf0aa-104">Пространства имен XML, содержащиеся в экземплярах класса <xref:System.Xml.Serialization.XmlSerializerNamespaces>, должны соответствовать требованиям консорциума World Wide Web Consortium (www.w3.org) под названием «Пространства имен в XML».</span><span class="sxs-lookup"><span data-stu-id="cf0aa-104">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (www.w3.org) specification called "Namespaces in XML."</span></span>  
  
 <span data-ttu-id="cf0aa-105">Пространства имен XML предоставляют метод квалификации имен элементов XML и атрибутов XML в документах XML.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-105">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="cf0aa-106">Полное имя состоит из префикса и локального имени, разделяемых двоеточием.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-106">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="cf0aa-107">Функцией префикса является только указание места заполнения, он сопоставлен URI, определяющим пространство имен.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-107">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="cf0aa-108">Сочетание процедур универсально управляемого пространства имен URI и локального имени позволяет создать имя, гарантированно универсально уникальное.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-108">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>  
  
 <span data-ttu-id="cf0aa-109">Создавая экземпляр `XmlSerializerNamespaces` и добавляя пары пространств имен в объект, можно указать префиксы, используемые в документе XML.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-109">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>  
  
### <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="cf0aa-110">Создание полных имен в документе XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-110">To create qualified names in an XML document</span></span>  
  
1.  <span data-ttu-id="cf0aa-111">Создайте экземпляр класса `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-111">Create an instance of the `XmlSerializerNamespaces` class.</span></span>  
  
2.  <span data-ttu-id="cf0aa-112">Добавьте все пары префиксов и пространств имен в `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-112">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>  
  
3.  <span data-ttu-id="cf0aa-113">Примените соответствующий атрибут `System.Xml.Serialization` к каждому члену или классу, который <xref:System.Xml.Serialization.XmlSerializer> будет сериализовать в документ XML.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-113">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>  
  
     <span data-ttu-id="cf0aa-114">Доступные атрибуты: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-114">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>  
  
4.  <span data-ttu-id="cf0aa-115">Задайте свойство `Namespace` каждого атрибута как одно из значений пространства имен из `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-115">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>  
  
5.  <span data-ttu-id="cf0aa-116">Передайте `XmlSerializerNamespaces` в метод `Serialize`, принадлежащий `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-116">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf0aa-117">Пример</span><span class="sxs-lookup"><span data-stu-id="cf0aa-117">Example</span></span>  
 <span data-ttu-id="cf0aa-118">В следующем примере создается `XmlSerializerNamespaces`, и к нему добавляются две пары префикса и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-118">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="cf0aa-119">Код создает `XmlSerializer`, который используется для сериализации экземпляра класса `Books`.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-119">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="cf0aa-120">Код вызывает метод `Serialize` с использованием `XmlSerializerNamespaces`, что позволяет XML содержать пространства имен с префиксами.</span><span class="sxs-lookup"><span data-stu-id="cf0aa-120">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf0aa-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cf0aa-121">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="cf0aa-122">Инструмент определения схемы XML и сериализация XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 [<span data-ttu-id="cf0aa-123">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="cf0aa-124">Класс XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="cf0aa-124">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)  
 [<span data-ttu-id="cf0aa-125">Атрибуты управления сериализацией XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 [<span data-ttu-id="cf0aa-126">Практическое руководство. Указание имени альтернативного элемента для потока XML</span><span class="sxs-lookup"><span data-stu-id="cf0aa-126">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 [<span data-ttu-id="cf0aa-127">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="cf0aa-127">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="cf0aa-128">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="cf0aa-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
