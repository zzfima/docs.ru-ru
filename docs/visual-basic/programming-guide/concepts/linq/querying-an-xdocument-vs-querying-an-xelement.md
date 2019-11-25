---
title: Запросы к XDocument и запросы к XElement
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 5cee2c841f391bfb6fc410421108656680880616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346554"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Querying an XDocument vs. Querying an XElement (Visual Basic)
При загрузке документа через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> обратите внимание на то, что запросы придется составлять не так, как при загрузке через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Сравнение XDocument.Load и XElement.Load  
 При загрузке XML-документа в <xref:System.Xml.Linq.XElement> через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> <xref:System.Xml.Linq.XElement> в корне XML-дерева содержит корневой элемент загруженного документа. Однако при загрузке этого же XML-документа в <xref:System.Xml.Linq.XDocument> через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> корень дерева - это узел <xref:System.Xml.Linq.XDocument>, а элемент корня загруженного документа - это один разрешенный дочерний узел <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument>. Оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] работают в зависимости от корневого узла.  
  
 В этом первом примере выполняется загрузка XML-дерева при помощи <xref:System.Xml.Linq.XElement.Load%2A>. Затем выполняется запрос по дочерним элементам корня дерева.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Как и ожидается, выполняется вывод следующих данных:  
  
```console
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 Следующий пример такой же, как и пример выше, за исключением того, что XML-дерево загружается в <xref:System.Xml.Linq.XDocument>, а не в <xref:System.Xml.Linq.XElement>.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```console
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 Обратите внимание, что при таком же запросе выводится только узел `Root`, а не три дочерних узла.  
  
 Одним из подходов при этом может быть использование свойства <xref:System.Xml.Linq.XDocument.Root%2A> перед доступом к методам оси:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Теперь на этот запрос выводятся те же результаты, что и при запросе по дереву, корень которого размещен в <xref:System.Xml.Linq.XElement>. Пример выводит следующие результаты:  
  
```console
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>См. также

- [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
