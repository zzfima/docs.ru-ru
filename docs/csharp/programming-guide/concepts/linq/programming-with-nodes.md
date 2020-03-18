---
title: Программирование с узлами (C#)
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 05c2e95fe97effda7b537a7ac2d8f5780f4e212b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168318"
---
# <a name="programming-with-nodes-c"></a>Программирование с узлами (C#)
Разработчикам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], которым требуется написать такие программы, как XML-редактор, система преобразования или модуль формирования отчетов, часто приходится писать программы, которые работают на более высоком уровне гранулярности по сравнению с элементами и атрибутами. Им часто приходится работать на уровне узлов, обрабатывая текстовые узлы, инструкции по обработке и комментарии. В этом разделе приводятся некоторые сведения о программировании на уровне узлов.  
  
## <a name="node-details"></a>Сведения об узле  
 Программист, работающий на уровне узлов, должен учитывать целый ряд нюансов программирования.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Родительскому свойству дочерних узлов XDocument задано значение Null  
 Свойство <xref:System.Xml.Linq.XObject.Parent%2A> содержит родительский объект <xref:System.Xml.Linq.XElement>, а не родительский узел. Дочерние узлы объекта <xref:System.Xml.Linq.XDocument> не имеют родительского объекта <xref:System.Xml.Linq.XElement>. Их родителем является документ, поэтому свойству <xref:System.Xml.Linq.XObject.Parent%2A> этих узлов задается значение NULL.  
  
 Следующий пример демонстрирует это:  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Соседние текстовые узлы возможны  
 В нескольких моделях программирования XML соседние текстовые узлы всегда объединяются. Иногда такую операцию называют нормализацией текстовых узлов. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] не нормализует текстовые узлы. Если добавить два текстовых узла в один элемент, то они будут соседними. Однако если добавить содержимое, определенное как строка, а не как узел <xref:System.Xml.Linq.XText>, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] может объединить строку с соседним текстовым узлом.  
  
 Следующий пример демонстрирует это:  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Пустые текстовые узлы возможны  
 В некоторых моделях программирования XML гарантируется, что текстовые узлы не будут содержать пустые строки. Обоснованием является то, что такой текстовый узел не будет влиять на сериализацию XML. Однако по этой же причине, по которой возможны соседние текстовые узлы, удаление текста из текстового узла путем присваивания ему в качестве значения пустой строки не приводит к удалению самого текстового узла.  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Пустые текстовые узлы влияют на сериализацию  
 Если элемент содержит только дочерний текстовый узел, который является пустым, то он сериализуется с использованием синтаксиса длинных тегов: `<Child></Child>`. Если элемент не содержит ни одного дочернего узла, то он сериализуется c использованием синтаксиса коротких тегов: `<Child />`.  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Пространства имен являются атрибутами в дереве LINQ to XML  
 Несмотря на то что синтаксис деклараций пространств имен похож на синтаксис атрибутов, в некоторых программных интерфейсах, например XSLT и XPath, декларации пространств имен не считаются атрибутами. Однако в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] пространства имен хранятся в XML-дереве как объекты <xref:System.Xml.Linq.XAttribute>. Если просмотреть атрибуты элемента, который содержит декларацию пространства имен, то можно увидеть, что декларация пространства имен является одним из элементов возвращенной коллекции.  
  
 Свойство <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> указывает, является ли атрибут декларацией пространства имен.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>Методы оси XPath не возвращают дочерние пробелы XDocument  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] допускает дочерние текстовые узлы объекта <xref:System.Xml.Linq.XDocument>, если эти текстовые узлы содержат только пробелы. Однако модель объектов XPath не включает пробелы как дочерние узлы документа, поэтому при прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> при помощи оси <xref:System.Xml.Linq.XContainer.Nodes%2A> возвращаются текстовые узлы с пробелами. Однако при прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> при помощи методов оси XPath текстовые узлы с пробелами возвращены не будут.  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>Объекты XDeclaration не являются узлами  
 При прохождении по дочерним узлам объекта <xref:System.Xml.Linq.XDocument> нельзя увидеть объект XML-декларации. Это свойство документа, а не его дочерний узел.  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  