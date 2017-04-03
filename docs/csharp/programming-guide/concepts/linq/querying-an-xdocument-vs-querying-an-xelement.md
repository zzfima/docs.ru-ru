---
title: "Сравнение запросов к XML-документам Запросы к XElement (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a3da563618ad3dbc9797f252ab51588a43ce8e6
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a>Сравнение запросов к XML-документам Запросы к XElement (C#)
При загрузке документа посредством <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> вы можете заметить, что запросы составляются немного не так, как при загрузке посредством <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Сравнение XDocument.Load и XElement.Load  
 При загрузке XML-документа в <xref:System.Xml.Linq.XElement> посредством <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> элемент <xref:System.Xml.Linq.XElement> в корне дерева XML содержит корневой элемент загруженного документа. Однако при загрузке этого же XML-документа в <xref:System.Xml.Linq.XDocument> посредством <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> корень дерева — это узел <xref:System.Xml.Linq.XDocument>, а корневой элемент загруженного документа — это один разрешенный дочерний узел <xref:System.Xml.Linq.XElement> документа <xref:System.Xml.Linq.XDocument>. Оси [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] работают в зависимости от корневого узла.  
  
 В первом примере выполняется загрузка дерева XML с помощью <xref:System.Xml.Linq.XElement.Load%2A>. Затем выполняется запрос по дочерним элементам корня дерева.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 Как и ожидается, выполняется вывод следующих данных:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 Следующий пример такой же, как и пример выше, за исключением того, что дерево XML загружается в <xref:System.Xml.Linq.XDocument>, а не в <xref:System.Xml.Linq.XElement>.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
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
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 Теперь этот запрос выдает те же результаты, что и запрос к дереву, корень которого размещен в <xref:System.Xml.Linq.XElement>. Пример выводит следующие результаты:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>См. также  
 [Базовые запросы (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
