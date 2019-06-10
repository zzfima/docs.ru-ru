---
title: Сравнение запросов к XML-документам Запросы к XElement (C#)
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 9d1e3b54b9d384280cd58aa3ca063f76758fc6fe
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487271"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a>Сравнение запросов к XML-документам Запросы к XElement (C#)
При загрузке документа через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> обратите внимание на то, что запросы придется составлять не так, как при загрузке через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Сравнение XDocument.Load и XElement.Load  
 При загрузке XML-документа в <xref:System.Xml.Linq.XElement> через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> <xref:System.Xml.Linq.XElement> в корне XML-дерева содержит корневой элемент загруженного документа. Однако при загрузке этого же XML-документа в <xref:System.Xml.Linq.XDocument> через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> корень дерева - это узел <xref:System.Xml.Linq.XDocument>, а элемент корня загруженного документа - это один разрешенный дочерний узел <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument>. Оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] работают в зависимости от корневого узла.  
  
 В этом первом примере выполняется загрузка XML-дерева при помощи <xref:System.Xml.Linq.XElement.Load%2A>. Затем выполняется запрос по дочерним элементам корня дерева.  
  
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
  
 Следующий пример такой же, как и пример выше, за исключением того, что XML-дерево загружается в <xref:System.Xml.Linq.XDocument>, а не в <xref:System.Xml.Linq.XElement>.  
  
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
  
 Теперь на этот запрос выводятся те же результаты, что и при запросе по дереву, корень которого размещен в <xref:System.Xml.Linq.XElement>. Пример выводит следующие результаты:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  