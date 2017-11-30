---
title: "Создание новых атрибутов для элементов в модели DOM"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="4bd18-102">Создание новых атрибутов для элементов в модели DOM</span><span class="sxs-lookup"><span data-stu-id="4bd18-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="4bd18-103">Создание новых атрибутов отличается от создания других типов узлов, поскольку атрибуты являются не узлами, но свойства узла элемента и содержатся в **XmlAttributeCollection** связанных с элементом.</span><span class="sxs-lookup"><span data-stu-id="4bd18-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="4bd18-104">Есть несколько способов создания атрибута и присоединения его к элементу:</span><span class="sxs-lookup"><span data-stu-id="4bd18-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="4bd18-105">Вернуть узел элемента и использовать **SetAttribute** Чтобы добавить атрибут в коллекцию атрибутов этого элемента.</span><span class="sxs-lookup"><span data-stu-id="4bd18-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="4bd18-106">Создание **XmlAttribute** узла с помощью **CreateAttribute** , вернуть узел элемента и использовать **SetAttributeNode** для добавления в коллекцию атрибутов этого узла элемент.</span><span class="sxs-lookup"><span data-stu-id="4bd18-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="4bd18-107">Следующий пример демонстрирует добавление атрибута к элементу с помощью **SetAttribute** метод.</span><span class="sxs-lookup"><span data-stu-id="4bd18-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
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
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="4bd18-108">В следующем примере показано новый атрибут с помощью **CreateAttribute** метод.</span><span class="sxs-lookup"><span data-stu-id="4bd18-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="4bd18-109">Затем показано, как атрибут добавляется в коллекцию атрибутов этого **книги** элемента с помощью **SetAttributeNode** метод.</span><span class="sxs-lookup"><span data-stu-id="4bd18-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="4bd18-110">Заданы следующие XML-данные:</span><span class="sxs-lookup"><span data-stu-id="4bd18-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="4bd18-111">Создается новый атрибут, и ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="4bd18-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="4bd18-112">Атрибут присоединяется к его элементу:</span><span class="sxs-lookup"><span data-stu-id="4bd18-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="4bd18-113">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="4bd18-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="4bd18-114">Полный образец кода можно найти на <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bd18-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="4bd18-115">Можно также создать **XmlAttribute** узел и использование **InsertBefore** или **InsertAfter** чтобы поместить его в соответствующее место в коллекции.</span><span class="sxs-lookup"><span data-stu-id="4bd18-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="4bd18-116">Если атрибут с таким именем уже существует в коллекции атрибутов существующих **XmlAttribute** узел удаляется из коллекции, а новый **XmlAttribute** вставки узла.</span><span class="sxs-lookup"><span data-stu-id="4bd18-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="4bd18-117">В этом случае выполняется так же, как **SetAttribute** метод.</span><span class="sxs-lookup"><span data-stu-id="4bd18-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="4bd18-118">Эти методы принимают в качестве параметра существующий узел как отправную точку для выполнения **InsertBefore** и **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="4bd18-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="4bd18-119">Если эталонный узел, куда необходимо добавить новый узел, по умолчанию не имеют **InsertAfter** вставляет новый узел в начало коллекции.</span><span class="sxs-lookup"><span data-stu-id="4bd18-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="4bd18-120">Значение по умолчанию положения **InsertBefore**, если ни один узел ссылки, в конец коллекции.</span><span class="sxs-lookup"><span data-stu-id="4bd18-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="4bd18-121">Если вы создали **XmlNamedNodeMap** атрибутов, можно добавить атрибут по имени с помощью <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bd18-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="4bd18-122">Дополнительные сведения см. в разделе [коллекции узлов в NamedNodeMap и nodelist](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="4bd18-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="4bd18-123">Атрибуты по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4bd18-123">Default Attributes</span></span>  
 <span data-ttu-id="4bd18-124">При создании элемента, для которого декларирован атрибут по умолчанию, модель XML DOM создаст новый атрибут по умолчанию со значением по умолчанию и присоединит его к элементу.</span><span class="sxs-lookup"><span data-stu-id="4bd18-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="4bd18-125">Одновременно будут созданы дочерние узлы атрибута по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4bd18-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="4bd18-126">Дочерние узлы атрибута</span><span class="sxs-lookup"><span data-stu-id="4bd18-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="4bd18-127">Значение узла атрибута становится его дочерними узлами.</span><span class="sxs-lookup"><span data-stu-id="4bd18-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="4bd18-128">Существует только два типа допустимым дочерних узлов: **XmlText** узлов, и **XmlEntityReference** узлов.</span><span class="sxs-lookup"><span data-stu-id="4bd18-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="4bd18-129">Они являются дочерними узлами в том смысле, что методы, такие как **FirstChild** и **LastChild** обрабатывают их как дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="4bd18-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="4bd18-130">Это отличие атрибута, имеющего дочерние узлы, становится важным во время удаления атрибута или его дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="4bd18-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="4bd18-131">Дополнительные сведения см. в разделе [удаление атрибутов из узла элемента в DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="4bd18-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd18-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4bd18-132">See Also</span></span>  
 [<span data-ttu-id="4bd18-133">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="4bd18-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
