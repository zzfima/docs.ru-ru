---
title: Доступ к атрибутам в модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
ms.openlocfilehash: dd3292620cafc4e5d2494b3b5e18e04691910dc4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711198"
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="f53b7-102">Доступ к атрибутам в модели DOM</span><span class="sxs-lookup"><span data-stu-id="f53b7-102">Accessing Attributes in the DOM</span></span>

<span data-ttu-id="f53b7-103">Атрибуты - свойства элемента, а не его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="f53b7-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="f53b7-104">Это различие очень важно из-за методов, используемых для перемещения по дочерним, родительским и одноуровневым узлам модели XML DOM.</span><span class="sxs-lookup"><span data-stu-id="f53b7-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="f53b7-105">Например, методы **PreviousSibling** и **NextSibling** не позволяют перемещаться с элемента на атрибут или с одного атрибута на другой.</span><span class="sxs-lookup"><span data-stu-id="f53b7-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="f53b7-106">Вместо этого атрибут является свойством элемента и принадлежит ему. У атрибута есть специальные методы навигации и свойство **OwnerElement**, но нет свойства **parentNode**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>

<span data-ttu-id="f53b7-107">Если текущий узел является элементом, метод **HasAttribute** позволяет узнать, есть ли у него атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f53b7-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="f53b7-108">Если у элемента есть атрибуты, к ним можно получить доступ различными методами.</span><span class="sxs-lookup"><span data-stu-id="f53b7-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="f53b7-109">Чтобы получить отдельный атрибут элементв, используйте методы **GetAttribute** и **GetAttributeNode** класса **XmlElement**. Также есть возможность получить все атрибуты сразу в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="f53b7-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="f53b7-110">Получение коллекции удобно, если предполагается ее обзор.</span><span class="sxs-lookup"><span data-stu-id="f53b7-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="f53b7-111">Если нужно получить все атрибуты конкретного элемента, воспользуйтесь его свойством **Attributes** для получения всех атрибутов в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="f53b7-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>

## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="f53b7-112">Получение всех атрибутов в виде коллекции</span><span class="sxs-lookup"><span data-stu-id="f53b7-112">Retrieving All Attributes into a Collection</span></span>

<span data-ttu-id="f53b7-113">Если нужно поместить все атрибуты узла элемента в коллекцию, вызовите свойство **XmlElement.Attributes**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="f53b7-114">Оно возвращает коллекцию **XmlAttributeCollection** со всеми атрибутами элемента.</span><span class="sxs-lookup"><span data-stu-id="f53b7-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="f53b7-115">Класс **XmlAttributeCollection** наследует от карты **XmlNamedNode**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="f53b7-116">Таким образом, для этой коллекции доступны все свойства и методы, что и для карты именованного узла, а также все методы и свойства класса **XmlAttributeCollection**, например свойство **ItemOf** и метод **Append**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="f53b7-117">Каждый элемент коллекции атрибутов представляет узел **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="f53b7-118">Чтобы выяснить число атрибутов некоторого элемента, получите коллекцию **XmlAttributeCollection** и вызовите ее свойство **Count**, которое содержит число узлов **XmlAttribute** в коллекции.</span><span class="sxs-lookup"><span data-stu-id="f53b7-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>

<span data-ttu-id="f53b7-119">В следующем примере кода показано, как получить коллекцию атрибутов и последовательно перебрать ее элементы, используя метод **Count** в роли индекса цикла.</span><span class="sxs-lookup"><span data-stu-id="f53b7-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="f53b7-120">Затем в примере демонстрируется получение одного атрибута из коллекции и вывод его значения.</span><span class="sxs-lookup"><span data-stu-id="f53b7-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim myElement As XmlElement = doc.DocumentElement

        ' Create an attribute collection from the element.
        Dim attrColl As XmlAttributeCollection = myElement.Attributes

        ' Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...")
        Dim i As Integer
        For i = 0 To attrColl.Count - 1
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)
            Console.Write("{0}", attrColl.ItemOf(i).Value)
            Console.WriteLine()
        Next

        ' Retrieve a single attribute from the collection; specifically, the
        ' attribute with the name "misc".
        Dim attr As XmlAttribute = attrColl("misc")

        ' Retrieve the value from that attribute.
        Dim miscValue As String = attr.InnerXml

        Console.WriteLine("Display the attribute information.")
        Console.WriteLine(miscValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{

    public static void Main()
    {
        XmlDocument doc = new XmlDocument();
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +
                      "<title>The Handmaid's Tale</title>" +
                      "<price>14.95</price>" +
                      "</book>");

        // Move to an element.
        XmlElement myElement = doc.DocumentElement;

        // Create an attribute collection from the element.
        XmlAttributeCollection attrColl = myElement.Attributes;

        // Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...");
        for (int i = 0; i < attrColl.Count; i++)
        {
            Console.Write("{0} = ", attrColl[i].Name);
            Console.Write("{0}", attrColl[i].Value);
            Console.WriteLine();
        }

        // Retrieve a single attribute from the collection; specifically, the
        // attribute with the name "misc".
        XmlAttribute attr = attrColl["misc"];

        // Retrieve the value from that attribute.
        String miscValue = attr.InnerXml;

        Console.WriteLine("Display the attribute information.");
        Console.WriteLine(miscValue);

    }
}
```

<span data-ttu-id="f53b7-121">Этот пример выводит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f53b7-121">This example displays the following output:</span></span>

<span data-ttu-id="f53b7-122">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="f53b7-122">**Output**</span></span>

<span data-ttu-id="f53b7-123">Отображает все атрибуты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="f53b7-123">Display all the attributes in the collection.</span></span>

```console
genre = novel
ISBN = 1-861001-57-5
misc = sale item
Display the attribute information.
sale item
```

<span data-ttu-id="f53b7-124">Информация из коллекции атрибутов может быть получена по имени или по значению индекса.</span><span class="sxs-lookup"><span data-stu-id="f53b7-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="f53b7-125">В примере показано получение данных по имени.</span><span class="sxs-lookup"><span data-stu-id="f53b7-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="f53b7-126">В следующем примере показано получение данных по значению индекса.</span><span class="sxs-lookup"><span data-stu-id="f53b7-126">The next example shows how to retrieve data by index number.</span></span>

<span data-ttu-id="f53b7-127">**XmlAttributeCollection** является коллекцией, которую можно обходить по имени или индексу. В этом примере мы выбираем из коллекции первый атрибут по индексу (нумерация начинается с нуля) и применяем файл **baseuri.xml** в качестве источника входных данных.</span><span class="sxs-lookup"><span data-stu-id="f53b7-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>

### <a name="input"></a><span data-ttu-id="f53b7-128">Input</span><span class="sxs-lookup"><span data-stu-id="f53b7-128">Input</span></span>

```xml
<!-- XML fragment -->
<book genre="novel">
  <title>Pride And Prejudice</title>
</book>
```

```vb
Option Explicit On
Option Strict On

Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()
        ' Create the XmlDocument.
        Dim doc As New XmlDocument()
        doc.Load("http://localhost/baseuri.xml")

        ' Display information on the attribute node. The value
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)
        Console.WriteLine("The value of the attribute:  {0}", attr.InnerText)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
  public static void Main()
  {
    // Create the XmlDocument.
    XmlDocument doc = new XmlDocument();

    doc.Load("http://localhost/baseuri.xml");

    // Display information on the attribute node. The value
    // returned for BaseURI is 'http://localhost/baseuri.xml'.
    XmlAttribute attr = doc.DocumentElement.Attributes[0];
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);
    Console.WriteLine("The value of the attribute:  {0}", attr.InnerText);
  }
}
```

## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="f53b7-129">Получение единичного узла атрибута</span><span class="sxs-lookup"><span data-stu-id="f53b7-129">Retrieving an Individual Attribute Node</span></span>

<span data-ttu-id="f53b7-130">Для получения из элемента одного узла атрибута используется метод <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f53b7-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="f53b7-131">Он возвращает объект типа **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="f53b7-132">Для полученного объекта **XmlAttribute** доступны все методы и свойства класса <xref:System.Xml.XmlAttribute?displayProperty=nameWithType>, например, значение **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim root As XmlElement
        root = doc.DocumentElement

        ' Get an attribute.
        Dim attr As XmlAttribute
        attr = root.GetAttributeNode("ISBN")

        ' Display the value of the attribute.
        Dim attrValue As String
        attrValue = attr.InnerXml
        Console.WriteLine(attrValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

 public class Sample
 {
      public static void Main()
      {
    XmlDocument doc = new XmlDocument();
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +
                   "<title>The Handmaid's Tale</title>" +
                   "<price>14.95</price>" +
                   "</book>");

    // Move to an element.
     XmlElement root = doc.DocumentElement;

    // Get an attribute.
     XmlAttribute attr = root.GetAttributeNode("ISBN");

    // Display the value of the attribute.
     String attrValue = attr.InnerXml;
     Console.WriteLine(attrValue);

    }
}
```

<span data-ttu-id="f53b7-133">Можно также поступить как в предыдущем примере, где единичный узел атрибута был получен из коллекции атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f53b7-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="f53b7-134">Следующий пример демонстрирует, как с помощью одной строки кода получить по значению индекса один атрибут из корневого элемента дерева XML-документа, существующего в виде свойства **DocumentElement**.</span><span class="sxs-lookup"><span data-stu-id="f53b7-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>

```csharp
XmlAttribute attr = doc.DocumentElement.Attributes[0];
```

## <a name="see-also"></a><span data-ttu-id="f53b7-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="f53b7-135">See also</span></span>

- [<span data-ttu-id="f53b7-136">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="f53b7-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
