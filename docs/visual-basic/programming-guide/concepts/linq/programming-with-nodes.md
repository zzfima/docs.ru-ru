---
title: "Программирование с узлами (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 967e207aa4d1a4afb21f82b7b1767a5c6dc088c6
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="programming-with-nodes-visual-basic"></a><span data-ttu-id="48fdc-102">Программирование с узлами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48fdc-102">Programming with Nodes (Visual Basic)</span></span>
<span data-ttu-id="48fdc-103">Разработчикам [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], которым требуется написать такие программы, как XML-редактор, система преобразования или модуль формирования отчетов, часто приходится писать программы, которые работают на более высоком уровне гранулярности по сравнению с элементами и атрибутами.</span><span class="sxs-lookup"><span data-stu-id="48fdc-103">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="48fdc-104">Им часто приходится работать на уровне узлов, обрабатывая текстовые узлы, инструкции по обработке и комментарии.</span><span class="sxs-lookup"><span data-stu-id="48fdc-104">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="48fdc-105">В этом разделе приводятся некоторые сведения о программировании на уровне узлов.</span><span class="sxs-lookup"><span data-stu-id="48fdc-105">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="48fdc-106">Сведения об узле</span><span class="sxs-lookup"><span data-stu-id="48fdc-106">Node Details</span></span>  
 <span data-ttu-id="48fdc-107">Программист, работающий на уровне узлов, должен учитывать целый ряд нюансов программирования.</span><span class="sxs-lookup"><span data-stu-id="48fdc-107">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="48fdc-108">Родительскому свойству дочерних узлов XDocument задано значение Null</span><span class="sxs-lookup"><span data-stu-id="48fdc-108">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="48fdc-109"><xref:System.Xml.Linq.XObject.Parent%2A>Свойство содержит родительский объект <xref:System.Xml.Linq.XElement>, не родительский узел.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="48fdc-109">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="48fdc-110">Дочерние узлы <xref:System.Xml.Linq.XDocument>не имеют родительского объекта <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="48fdc-110">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="48fdc-111">Их родителем является документ, поэтому <xref:System.Xml.Linq.XObject.Parent%2A>для этих узлов задано значение null.</xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="48fdc-111">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="48fdc-112">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="48fdc-112">The following example demonstrates this:</span></span>  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 <span data-ttu-id="48fdc-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-113">This example produces the following output:</span></span>  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="48fdc-114">Соседние текстовые узлы возможны</span><span class="sxs-lookup"><span data-stu-id="48fdc-114">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="48fdc-115">В нескольких моделях программирования XML соседние текстовые узлы всегда объединяются.</span><span class="sxs-lookup"><span data-stu-id="48fdc-115">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="48fdc-116">Иногда такую операцию называют нормализацией текстовых узлов.</span><span class="sxs-lookup"><span data-stu-id="48fdc-116">This is sometimes called normalization of text nodes.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="48fdc-117"> не нормализует текстовые узлы.</span><span class="sxs-lookup"><span data-stu-id="48fdc-117"> does not normalize text nodes.</span></span> <span data-ttu-id="48fdc-118">Если добавить два текстовых узла в один элемент, то они будут соседними.</span><span class="sxs-lookup"><span data-stu-id="48fdc-118">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="48fdc-119">Тем не менее если добавить содержимое, определенное как строка, а не как <xref:System.Xml.Linq.XText>узел, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] может объединить строку с соседним текстовым узлом.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="48fdc-119">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="48fdc-120">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="48fdc-120">The following example demonstrates this:</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
' This does not add a new text node.  
xmlTree.Add("new content")  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
'// This does add a new, adjacent text node.  
xmlTree.Add(New XText("more text"))  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="48fdc-121">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-121">This example produces the following output:</span></span>  
  
```  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="48fdc-122">Пустые текстовые узлы возможны</span><span class="sxs-lookup"><span data-stu-id="48fdc-122">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="48fdc-123">В некоторых моделях программирования XML гарантируется, что текстовые узлы не будут содержать пустые строки.</span><span class="sxs-lookup"><span data-stu-id="48fdc-123">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="48fdc-124">Обоснованием является то, что такой текстовый узел не будет влиять на сериализацию XML.</span><span class="sxs-lookup"><span data-stu-id="48fdc-124">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="48fdc-125">Однако по этой же причине, по которой возможны соседние текстовые узлы, удаление текста из текстового узла путем присваивания ему в качестве значения пустой строки не приводит к удалению самого текстового узла.</span><span class="sxs-lookup"><span data-stu-id="48fdc-125">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 <span data-ttu-id="48fdc-126">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-126">This example produces the following output:</span></span>  
  
```  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="48fdc-127">Пустые текстовые узлы влияют на сериализацию</span><span class="sxs-lookup"><span data-stu-id="48fdc-127">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="48fdc-128">Если элемент содержит только дочерний текстовый узел, который является пустым, то он сериализуется с использованием синтаксиса длинных тегов: `<Child></Child>`.</span><span class="sxs-lookup"><span data-stu-id="48fdc-128">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="48fdc-129">Если элемент не содержит ни одного дочернего узла, то он сериализуется c использованием синтаксиса коротких тегов: `<Child />`.</span><span class="sxs-lookup"><span data-stu-id="48fdc-129">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 <span data-ttu-id="48fdc-130">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-130">This example produces the following output:</span></span>  
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="48fdc-131">Пространства имен являются атрибутами в дереве LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="48fdc-131">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="48fdc-132">Несмотря на то что синтаксис деклараций пространств имен похож на синтаксис атрибутов, в некоторых программных интерфейсах, например XSLT и XPath, декларации пространств имен не считаются атрибутами.</span><span class="sxs-lookup"><span data-stu-id="48fdc-132">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="48fdc-133">Однако в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], пространства имен хранятся в виде <xref:System.Xml.Linq.XAttribute>объекты в дереве XML.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="48fdc-133">However, in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="48fdc-134">Если просмотреть атрибуты элемента, который содержит декларацию пространства имен, то можно увидеть, что декларация пространства имен является одним из элементов возвращенной коллекции.</span><span class="sxs-lookup"><span data-stu-id="48fdc-134">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="48fdc-135"><xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>Свойство указывает, является ли атрибут объявления пространства имен.</xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A></span><span class="sxs-lookup"><span data-stu-id="48fdc-135">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```vb  
Dim root As XElement = _   
<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>  
For Each att As XAttribute In root.Attributes()  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _  
                      att.IsNamespaceDeclaration)  
Next  
```  
  
 <span data-ttu-id="48fdc-136">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-136">This example produces the following output:</span></span>  
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="48fdc-137">Методы оси XPath не возвращают дочерние пробелы XDocument</span><span class="sxs-lookup"><span data-stu-id="48fdc-137">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="48fdc-138">допускает дочерние текстовые узлы объекта <xref:System.Xml.Linq.XDocument>, при условии, что текстовые узлы содержат только пробелы.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="48fdc-138"> allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="48fdc-139">Тем не менее, модель объектов XPath не включает пробелы как дочерние узлы документа, поэтому при прохождении по дочерним узлам из <xref:System.Xml.Linq.XDocument>с помощью <xref:System.Xml.Linq.XContainer.Nodes%2A>оси, будет возвращено текстовых узлов пробелов.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="48fdc-139">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white space text nodes will be returned.</span></span> <span data-ttu-id="48fdc-140">Однако при прохождении по дочерним узлам из <xref:System.Xml.Linq.XDocument>помощи методов оси XPath текстовые узлы пробелов не возвращаются.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="48fdc-140">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white space text nodes will not be returned.</span></span>  
  
```vb  
' Create a document with some white space child nodes of the document.  
Dim root As XDocument = XDocument.Parse( _  
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _  
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _  
LoadOptions.PreserveWhitespace)  
  
' Count the white space child nodes using LINQ to XML.  
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())  
  
' Count the white space child nodes using XPathEvaluate.  
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)  
Console.WriteLine(nodes.OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="48fdc-141">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-141">This example produces the following output:</span></span>  
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="48fdc-142">Объекты XDeclaration не являются узлами</span><span class="sxs-lookup"><span data-stu-id="48fdc-142">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="48fdc-143">При прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument>, вы не увидите объект XML-декларации.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="48fdc-143">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="48fdc-144">Это свойство документа, а не его дочерний узел.</span><span class="sxs-lookup"><span data-stu-id="48fdc-144">It is a property of the document, not a child node of it.</span></span>  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 <span data-ttu-id="48fdc-145">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="48fdc-145">This example produces the following output:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a><span data-ttu-id="48fdc-146">См. также</span><span class="sxs-lookup"><span data-stu-id="48fdc-146">See Also</span></span>  
 [<span data-ttu-id="48fdc-147">Дополнительно программированию LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48fdc-147">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

