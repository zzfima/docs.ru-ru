---
title: "Сравнительные характеристики XPath и LINQ to XML | Документы Майкрософт"
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
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d60000605a42faa22841cc7b76b878a77bc53b7f
ms.lasthandoff: 03/13/2017


---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Сравнительные характеристики XPath и LINQ to XML
XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] имеют некоторые сходные функциональные возможности. И то и другое можно использовать, чтобы запрашивать XML-дерево для возвращения таких результатов, как коллекция элементов, коллекция атрибутов, коллекция узлов или значение элемента или атрибута. Однако между ними также есть некоторые различия.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Различия между XPath и LINQ to XML  
 XPath не поддерживает проекции новых типов. Может возвращать только коллекции узлов из дерева, тогда как [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] может выполнить запрос, проецировав граф объектов или XML-дерево в новой форме. Запросы [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] гораздо более эффективны и обладают большими возможностями, чем выражения XPath.  
  
 Выражение XPath представлено в изолированном виде, внутри строки. Компилятор C# не может выполнить синтаксический анализ выражения XPath во время компиляции. Напротив, компилятор C# проводит синтаксический анализ и компилирует запросы [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Компилятор способен обнаруживать многие ошибки запроса.  
  
 Результаты XPath не являются строго типизированными. В некоторых ситуациях результатом вычисления выражения XPath является объект, а задача определения соответствующего типа и приведения результата в соответствии с необходимостью возлагается на разработчика. В отличие от этого, проекции на основе запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] являются строго типизированными.  
  
## <a name="result-ordering"></a>Упорядочение результатов  
 В документе XPath 1.0 Recommendation указано, что коллекция, которая является результатом вычисления выражения XPath, не упорядочена.  
  
 Однако при просмотре коллекции, возвращенной методом оси [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] XPath, можно отметить, что узлы в коллекции возвращены в том же порядке, что и в документе. И они располагаются так даже при доступе к осям XPath, где предикаты выражены в обратном порядке по отношению к документу, например `preceding` и `preceding-sibling`.  
  
 Напротив, большинство осей [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] возвращает коллекции в порядке документа, однако две из них, <xref:System.Xml.Linq.XNode.Ancestors%2A> и <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, возвращают коллекции в порядке, обратном порядку документа. В следующей таблице перечисляются эти оси и указывается порядок коллекций для каждой из них.  
  
|Ось LINQ to XML|Упорядочение|  
|----------------------|--------------|  
|XContainer.DescendantNodes|Порядок документа|  
|XContainer.Descendants|Порядок документа|  
|XContainer.Elements|Порядок документа|  
|XContainer.Nodes|Порядок документа|  
|XContainer.NodesAfterSelf|Порядок документа|  
|XContainer.NodesBeforeSelf|Порядок документа|  
|XElement.AncestorsAndSelf|Обратный порядок документа|  
|XElement.Attributes|Порядок документа|  
|XElement.DescendantNodesAndSelf|Порядок документа|  
|XElement.DescendantsAndSelf|Порядок документа|  
|XNode.Ancestors|Обратный порядок документа|  
|XNode.ElementsAfterSelf|Порядок документа|  
|XNode.ElementsBeforeSelf|Порядок документа|  
|XNode.NodesAfterSelf|Порядок документа|  
|XNode.NodesBeforeSelf|Порядок документа|  
  
## <a name="positional-predicates"></a>Позиционные предикаты  
 В выражении XPath позиционные предикаты представляются с учетом порядка расположения в документе для многих осей, однако они располагаются в порядке, обратном по отношению к документу, для обратных осей, а именно `preceding`, `preceding-sibling`, `ancestor` и `ancestor-or-self`. Например, выражение XPath `preceding-sibling::*[1]` возвращает ближайший предшествующий одноуровневый элемент. Так происходит даже несмотря на то, что итоговый результирующий набор представляется в порядке документа.  
  
 В отличие от этого все позиционные предикаты в LINQ to XML всегда выражаются в порядке оси. Например, `anElement.ElementsBeforeSelf().ToList()[0]` возвращает первый дочерний элемент родителя запрашиваемого элемента, а не ближайший предшествующий одноуровневый элемент. Другой пример: `anElement.Ancestors().ToList()[0]` возвращает родительский элемент.  
  
 Отметим, что при описанном выше подходе материализуется вся коллекция. Это не самый эффективный способ написания такого запроса. Запрос был написан так в целях демонстрации поведения позиционных предикатов. Более подходящим способом написания этого же запроса является использование метода <xref:System.Linq.Enumerable.First%2A> следующим образом: `anElement.ElementsBeforeSelf().First()`.  
  
 Если бы потребовалось найти ближайший предшествующий элемент в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], то было бы написано следующее выражение:  
  
 `ElementsBeforeSelf().Last()`  
  
## <a name="performance-differences"></a>Различия в производительности  
 Запросы XPath, которые используют функциональность XPath в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], менее производительны, чем запросы [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="comparison-of-composition"></a>Сравнение композиций  
 Композиция запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] немного напоминает композицию выражения XPath, хотя по синтаксису они совершенно различны.  
  
 Например, если в переменной с именем `customers` имеется элемент и требуется найти внучатый элемент с именем `CompanyName` во всех дочерних элементах с именем `Customer`, то нужно написать следующее выражение XPath:  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName");  
```  
  
 Эквивалентное выражение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] таково:  
  
```csharp  
customers.Element("Customer").Elements("CompanyName");  
```  
  
 Существуют похожие аналоги для каждой оси XPath.  
  
|Ось XPath|Ось LINQ to XML|  
|----------------|----------------------|  
|дочерняя (ось по умолчанию)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|  
|родительская (...)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=fullName>|  
|ось атрибутов (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|  
|ось ancestor|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|  
|ось ancestor-or-self|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|  
|дочерняя ось (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=fullName>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=fullName>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=fullName>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=fullName>|  
|following|Непосредственного эквивалента нет.|  
|preceding|Непосредственного эквивалента нет.|  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
