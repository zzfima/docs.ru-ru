---
title: Создание новых атрибутов для элементов в модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9445f16b6470b1d2066fcae749b1623ec5e11ac
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138948"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="b15c3-102">Создание новых атрибутов для элементов в модели DOM</span><span class="sxs-lookup"><span data-stu-id="b15c3-102">Creating New Attributes for Elements in the DOM</span></span>

<span data-ttu-id="b15c3-103">Создание новых атрибутов отличается от создания других типов узлов, поскольку атрибуты являются не узлами, а свойствами узла элемента, и содержатся в связанной с этим элементом коллекции **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="b15c3-104">Есть несколько способов создания атрибута и присоединения его к элементу:</span><span class="sxs-lookup"><span data-stu-id="b15c3-104">There are multiple ways to create an attribute and attach it to an element:</span></span>

- <span data-ttu-id="b15c3-105">Получите узел элемента и примените метод **SetAttribute**, чтобы добавить атрибут в коллекцию атрибутов этого элемента.</span><span class="sxs-lookup"><span data-stu-id="b15c3-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>

- <span data-ttu-id="b15c3-106">Создайте узел **XmlAttribute** с помощью метода **CreateAttribute**, получите узел элемента и примените метод **SetAttributeNode**, чтобы добавить узел в коллекцию атрибутов этого элемента.</span><span class="sxs-lookup"><span data-stu-id="b15c3-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>

<span data-ttu-id="b15c3-107">В следующем примере показано, как добавить атрибут к элементу с помощью метода **setAttribute** :</span><span class="sxs-lookup"><span data-stu-id="b15c3-107">The following example shows how to add an attribute to an element using the **SetAttribute** method:</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As New XmlDocument()
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _
                    "<title>Pride And Prejudice</title>" & _
                    "</book>")
        Dim root As XmlElement = doc.DocumentElement

        ' Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel")

        Console.WriteLine("Display the modified XML...")
        Console.WriteLine(doc.InnerXml)
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
        var doc = new XmlDocument();
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +
                    "<title>Pride And Prejudice</title>" +
                    "</book>");
        XmlElement root = doc.DocumentElement;

        // Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel");

        Console.WriteLine("Display the modified XML...");
        Console.WriteLine(doc.InnerXml);
    }
}
```

<span data-ttu-id="b15c3-108">Следующий пример демонстрирует, как создать новый атрибут с помощью метода **CreateAttribute**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="b15c3-109">Созданный атрибут он добавляет в коллекцию атрибутов элемента **book** с помощью метода **SetAttributeNode**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>

<span data-ttu-id="b15c3-110">Заданы следующие XML-данные:</span><span class="sxs-lookup"><span data-stu-id="b15c3-110">Given the following XML:</span></span>
  
```xml
<book genre='novel' ISBN='1-861001-57-5'>
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="b15c3-111">Создается новый атрибут, и ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="b15c3-111">create a new attribute and give it a value:</span></span>

```vb
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")
attr.Value = "WorldWide Publishing"
```

```csharp
XmlAttribute attr = doc.CreateAttribute("publisher");
attr.Value = "WorldWide Publishing";
```

<span data-ttu-id="b15c3-112">Атрибут присоединяется к его элементу:</span><span class="sxs-lookup"><span data-stu-id="b15c3-112">and attach it to the element:</span></span>

```vb
doc.DocumentElement.SetAttributeNode(attr)
```

```csharp
doc.DocumentElement.SetAttributeNode(attr);
```

<span data-ttu-id="b15c3-113">**Выходные данные:**</span><span class="sxs-lookup"><span data-stu-id="b15c3-113">**Output**</span></span>

```xml
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="b15c3-114">Полный код для этого примера вы найдете на странице <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b15c3-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>

<span data-ttu-id="b15c3-115">Также можно создать узел **XmlAttribute** и вызвать метод **InsertBefore** или **InsertAfter**, чтобы поместить его в подходящее место коллекции.</span><span class="sxs-lookup"><span data-stu-id="b15c3-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="b15c3-116">Если в коллекции атрибутов уже существует атрибут с таким именем, эти методы удаляют существующий узел **XmlAttribute** и добавляют вместо него новый узел **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="b15c3-117">Алгоритм выполнения здесь такой же, как у метода **SetAttribute**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="b15c3-118">Эти методы принимают в качестве параметра существующий узел, который будет считаться базовой точкой для методов **InsertBefore** и **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="b15c3-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="b15c3-119">Если не задан базовый узел, рядом с которым нужно вставить новый узел, метод **InsertAfter** по умолчанию вставляет новый узел в начало коллекции,</span><span class="sxs-lookup"><span data-stu-id="b15c3-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="b15c3-120">а метод **InsertBefore** — в конец коллекции.</span><span class="sxs-lookup"><span data-stu-id="b15c3-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>

<span data-ttu-id="b15c3-121">Если вы создали **XmlNamedNodeMap** атрибутов, можно добавить атрибут по имени с помощью метода <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="b15c3-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A> method.</span></span> <span data-ttu-id="b15c3-122">Дополнительные сведения см. в статье [Коллекции узлов в NamedNodeMap и NodeList](node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="b15c3-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](node-collections-in-namednodemaps-and-nodelists.md).</span></span>

## <a name="default-attributes"></a><span data-ttu-id="b15c3-123">Атрибуты по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b15c3-123">Default attributes</span></span>

<span data-ttu-id="b15c3-124">При создании элемента, для которого декларирован атрибут по умолчанию, модель XML DOM создаст новый атрибут по умолчанию со значением по умолчанию и присоединит его к элементу.</span><span class="sxs-lookup"><span data-stu-id="b15c3-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="b15c3-125">Одновременно будут созданы дочерние узлы атрибута по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b15c3-125">The child nodes of the default attribute are also created at this time.</span></span>

## <a name="attribute-child-nodes"></a><span data-ttu-id="b15c3-126">Дочерние узлы атрибута</span><span class="sxs-lookup"><span data-stu-id="b15c3-126">Attribute child nodes</span></span>

<span data-ttu-id="b15c3-127">Значение узла атрибута становится его дочерними узлами.</span><span class="sxs-lookup"><span data-stu-id="b15c3-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="b15c3-128">Существует только два типа допустимых дочерних узлов: узлы **xmltext** и узел **XmlEntityReference** .</span><span class="sxs-lookup"><span data-stu-id="b15c3-128">There are only two types of valid child nodes: **XmlText** nodes and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="b15c3-129">Они являются дочерними узлами в том смысле, что такие методы, как **FirstChild** и **LastChild**, обрабатывают их как дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="b15c3-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="b15c3-130">Это отличие атрибута, имеющего дочерние узлы, становится важным во время удаления атрибута или его дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="b15c3-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="b15c3-131">Дополнительные сведения см. в статье [Удаление атрибутов из узла элемента в модели DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="b15c3-131">For more information, see [Removing Attributes from an Element Node in the DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b15c3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b15c3-132">See also</span></span>

- [<span data-ttu-id="b15c3-133">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="b15c3-133">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
