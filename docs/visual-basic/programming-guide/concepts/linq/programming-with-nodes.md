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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 52fb60b95b869a79900f84c2a1a7a6151bb5b58f
ms.lasthandoff: 03/13/2017

---
# <a name="programming-with-nodes-visual-basic"></a>Программирование с узлами (Visual Basic)
Разработчикам [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], которым требуется написать такие программы, как XML-редактор, система преобразования или модуль формирования отчетов, часто приходится писать программы, которые работают на более высоком уровне гранулярности по сравнению с элементами и атрибутами. Им часто приходится работать на уровне узлов, обрабатывая текстовые узлы, инструкции по обработке и комментарии. В этом разделе приводятся некоторые сведения о программировании на уровне узлов.  
  
## <a name="node-details"></a>Сведения об узле  
 Программист, работающий на уровне узлов, должен учитывать целый ряд нюансов программирования.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Родительскому свойству дочерних узлов XDocument задано значение Null  
 <xref:System.Xml.Linq.XObject.Parent%2A>Свойство содержит родительский объект <xref:System.Xml.Linq.XElement>, не родительский узел.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XObject.Parent%2A> Дочерние узлы <xref:System.Xml.Linq.XDocument>не имеют родительского объекта <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> Их родителем является документ, поэтому <xref:System.Xml.Linq.XObject.Parent%2A>для этих узлов задано значение null.</xref:System.Xml.Linq.XObject.Parent%2A>  
  
 Следующий пример демонстрирует это:  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Соседние текстовые узлы возможны  
 В нескольких моделях программирования XML соседние текстовые узлы всегда объединяются. Иногда такую операцию называют нормализацией текстовых узлов. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] не нормализует текстовые узлы. Если добавить два текстовых узла в один элемент, то они будут соседними. Тем не менее если добавить содержимое, определенное как строка, а не как <xref:System.Xml.Linq.XText>узел, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] может объединить строку с соседним текстовым узлом.</xref:System.Xml.Linq.XText>  
  
 Следующий пример демонстрирует это:  
  
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
  
 В этом примере выводятся следующие данные:  
  
```  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Пустые текстовые узлы возможны  
 В некоторых моделях программирования XML гарантируется, что текстовые узлы не будут содержать пустые строки. Обоснованием является то, что такой текстовый узел не будет влиять на сериализацию XML. Однако по этой же причине, по которой возможны соседние текстовые узлы, удаление текста из текстового узла путем присваивания ему в качестве значения пустой строки не приводит к удалению самого текстового узла.  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Пустые текстовые узлы влияют на сериализацию  
 Если элемент содержит только дочерний текстовый узел, который является пустым, то он сериализуется с использованием синтаксиса длинных тегов: `<Child></Child>`. Если элемент не содержит ни одного дочернего узла, то он сериализуется c использованием синтаксиса коротких тегов: `<Child />`.  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Пространства имен являются атрибутами в дереве LINQ to XML  
 Несмотря на то что синтаксис деклараций пространств имен похож на синтаксис атрибутов, в некоторых программных интерфейсах, например XSLT и XPath, декларации пространств имен не считаются атрибутами. Однако в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], пространства имен хранятся в виде <xref:System.Xml.Linq.XAttribute>объекты в дереве XML.</xref:System.Xml.Linq.XAttribute> Если просмотреть атрибуты элемента, который содержит декларацию пространства имен, то можно увидеть, что декларация пространства имен является одним из элементов возвращенной коллекции.  
  
 <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>Свойство указывает, является ли атрибут объявления пространства имен.</xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>  
  
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
  
 В этом примере выводятся следующие данные:  
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>Методы оси XPath не возвращают дочерние пробелы XDocument  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]допускает дочерние текстовые узлы объекта <xref:System.Xml.Linq.XDocument>, при условии, что текстовые узлы содержат только пробелы.</xref:System.Xml.Linq.XDocument> Тем не менее, модель объектов XPath не включает пробелы как дочерние узлы документа, поэтому при прохождении по дочерним узлам из <xref:System.Xml.Linq.XDocument>с помощью <xref:System.Xml.Linq.XContainer.Nodes%2A>оси, будет возвращено текстовых узлов пробелов.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XDocument> Однако при прохождении по дочерним узлам из <xref:System.Xml.Linq.XDocument>помощи методов оси XPath текстовые узлы пробелов не возвращаются.</xref:System.Xml.Linq.XDocument>  
  
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
  
 В этом примере выводятся следующие данные:  
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>Объекты XDeclaration не являются узлами  
 При прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument>, вы не увидите объект XML-декларации.</xref:System.Xml.Linq.XDocument> Это свойство документа, а не его дочерний узел.  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>См. также  
 [Дополнительно программированию LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
