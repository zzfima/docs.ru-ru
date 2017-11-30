---
title: "Доступ к атрибутам в модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="42515-102">Доступ к атрибутам в модели DOM</span><span class="sxs-lookup"><span data-stu-id="42515-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="42515-103">Атрибуты - свойства элемента, а не его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="42515-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="42515-104">Это различие очень важно из-за методов, используемых для перемещения по дочерним, родительским и одноуровневым узлам модели XML DOM.</span><span class="sxs-lookup"><span data-stu-id="42515-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="42515-105">Например **PreviousSibling** и **NextSibling** методы не используются для перемещения с элемента на атрибут или между атрибутами.</span><span class="sxs-lookup"><span data-stu-id="42515-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="42515-106">Вместо этого атрибут является свойством элемента и принадлежит элемент, имеет **OwnerElement** свойство и не **parentNode** свойство, и имеет собственные методы навигации.</span><span class="sxs-lookup"><span data-stu-id="42515-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="42515-107">Если текущий узел является элементом, используйте **HasAttribute** метод, если есть какие-либо атрибуты, связанные с элементом.</span><span class="sxs-lookup"><span data-stu-id="42515-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="42515-108">Если у элемента есть атрибуты, к ним можно получить доступ различными методами.</span><span class="sxs-lookup"><span data-stu-id="42515-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="42515-109">Для получения одного атрибута элемента, можно использовать **GetAttribute** и **GetAttributeNode** методы **XmlElement** или получить все атрибуты в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="42515-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="42515-110">Получение коллекции удобно, если предполагается ее обзор.</span><span class="sxs-lookup"><span data-stu-id="42515-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="42515-111">Если требуется, чтобы все атрибуты данного элемента, используйте **атрибуты** свойство элемента для получения всех атрибутов в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="42515-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="42515-112">Получение всех атрибутов в виде коллекции</span><span class="sxs-lookup"><span data-stu-id="42515-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="42515-113">Если требуется поместить все атрибуты узла элемента в коллекцию, вызовите **XmlElement.Attributes** свойство.</span><span class="sxs-lookup"><span data-stu-id="42515-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="42515-114">Это возвращает **XmlAttributeCollection** , содержащий все атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="42515-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="42515-115">**XmlAttributeCollection** класс наследует от **XmlNamedNode** карты.</span><span class="sxs-lookup"><span data-stu-id="42515-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="42515-116">Таким образом, методы и свойства, доступные для данной коллекции включают в себя те, которые доступны для карты именованного узла в дополнение к методам и свойствам, специфичным для **XmlAttributeCollection** класса, такие как **ItemOf**  свойство или **Append** метод.</span><span class="sxs-lookup"><span data-stu-id="42515-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="42515-117">Каждый элемент в коллекции атрибутов представляет **XmlAttribute** узла.</span><span class="sxs-lookup"><span data-stu-id="42515-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="42515-118">Чтобы выяснить число атрибутов данного элемента, получить **XmlAttributeCollection**и использовать **число** свойство, чтобы просмотреть сколько **XmlAttribute** узлы находятся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="42515-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="42515-119">В следующем примере кода показано, как получить атрибут коллекции и, используя **число** для индекса цикла, пройти по ней.</span><span class="sxs-lookup"><span data-stu-id="42515-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="42515-120">Затем в примере демонстрируется получение одного атрибута из коллекции и вывод его значения.</span><span class="sxs-lookup"><span data-stu-id="42515-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
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
  
 <span data-ttu-id="42515-121">Этот пример выводит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="42515-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="42515-122">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="42515-122">**Output**</span></span>  
  
 <span data-ttu-id="42515-123">Отображает все атрибуты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="42515-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="42515-124">Информация из коллекции атрибутов может быть получена по имени или по значению индекса.</span><span class="sxs-lookup"><span data-stu-id="42515-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="42515-125">В примере показано получение данных по имени.</span><span class="sxs-lookup"><span data-stu-id="42515-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="42515-126">В следующем примере показано получение данных по значению индекса.</span><span class="sxs-lookup"><span data-stu-id="42515-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="42515-127">Поскольку **XmlAttributeCollection** является коллекцией и ее можно обходить по имени или индексу, в этом примере показан выбор из коллекции, используя отсчитываемый от нуля индекс и следующий файл первого атрибута **baseuri.xml**качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="42515-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="42515-128">Ввод</span><span class="sxs-lookup"><span data-stu-id="42515-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
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
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
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
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="42515-129">Получение единичного узла атрибута</span><span class="sxs-lookup"><span data-stu-id="42515-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="42515-130">Для получения из элемента одного узла атрибута используется метод <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="42515-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="42515-131">Возвращает объект типа **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="42515-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="42515-132">После получения **XmlAttribute**, все методы и свойства, доступные в <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> класса доступны для этого объекта, например, можно найти **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="42515-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
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
  
 <span data-ttu-id="42515-133">Можно также поступить как в предыдущем примере, где единичный узел атрибута был получен из коллекции атрибутов.</span><span class="sxs-lookup"><span data-stu-id="42515-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="42515-134">В следующем примере кода показано как с одной строки кода можно получить единичный атрибут по номеру индекса из корневого элемента XML-документа дерева, также известного как **DocumentElement** свойство.</span><span class="sxs-lookup"><span data-stu-id="42515-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="42515-135">См. также</span><span class="sxs-lookup"><span data-stu-id="42515-135">See Also</span></span>  
 [<span data-ttu-id="42515-136">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="42515-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
