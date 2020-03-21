---
title: Программирование с узлами
ms.date: 07/20/2015
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
ms.openlocfilehash: b2c9022cb57cf122af47bbe6d1a7fe2b4d41327c
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266967"
---
# <a name="programming-with-nodes-visual-basic"></a>Программирование с узлами (Visual Basic)
Разработчикам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], которым требуется написать такие программы, как XML-редактор, система преобразования или модуль формирования отчетов, часто приходится писать программы, которые работают на более высоком уровне гранулярности по сравнению с элементами и атрибутами. Им часто приходится работать на уровне узлов, обрабатывая текстовые узлы, инструкции по обработке и комментарии. В этом разделе приводятся некоторые сведения о программировании на уровне узлов.  
  
## <a name="node-details"></a>Сведения об узле  
 Программист, работающий на уровне узлов, должен учитывать целый ряд нюансов программирования.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Родительскому свойству дочерних узлов XDocument задано значение Null  
 Свойство <xref:System.Xml.Linq.XObject.Parent%2A> содержит родительский объект <xref:System.Xml.Linq.XElement>, а не родительский узел. Дочерние узлы объекта <xref:System.Xml.Linq.XDocument> не имеют родительского объекта <xref:System.Xml.Linq.XElement>. Их родителем является документ, поэтому свойству <xref:System.Xml.Linq.XObject.Parent%2A> этих узлов задается значение NULL.  
  
 Следующий пример демонстрирует это:  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Соседние текстовые узлы возможны  
 В нескольких моделях программирования XML соседние текстовые узлы всегда объединяются. Иногда такую операцию называют нормализацией текстовых узлов. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] не нормализует текстовые узлы. Если добавить два текстовых узла в один элемент, то они будут соседними. Однако если добавить содержимое, определенное как строка, а не как узел <xref:System.Xml.Linq.XText>, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] может объединить строку с соседним текстовым узлом.  
  
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
  
```console  
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
  
```console  
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
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Пространства имен являются атрибутами в дереве LINQ to XML  
 Несмотря на то что синтаксис деклараций пространств имен похож на синтаксис атрибутов, в некоторых программных интерфейсах, например XSLT и XPath, декларации пространств имен не считаются атрибутами. Однако в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] пространства имен хранятся в XML-дереве как объекты <xref:System.Xml.Linq.XAttribute>. Если просмотреть атрибуты элемента, который содержит декларацию пространства имен, то можно увидеть, что декларация пространства имен является одним из элементов возвращенной коллекции.  
  
 Свойство <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> указывает, является ли атрибут декларацией пространства имен.  
  
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
  
```console  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>Методы оси XPath не возвращают дочерние пробелы XDocument  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] допускает дочерние текстовые узлы объекта <xref:System.Xml.Linq.XDocument>, если эти текстовые узлы содержат только пробелы. Однако модель объектов XPath не включает пробелы как дочерние узлы документа, поэтому при прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> при помощи оси <xref:System.Xml.Linq.XContainer.Nodes%2A> возвращаются текстовые узлы с пробелами. Однако при прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> при помощи методов оси XPath текстовые узлы с пробелами возвращены не будут.  
  
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
  
```console  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>Объекты XDeclaration не являются узлами  
 При прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> нельзя увидеть объект XML-декларации. Это свойство документа, а не его дочерний узел.  
  
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
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>См. также раздел

- [Расширенный LIN' к XML программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
