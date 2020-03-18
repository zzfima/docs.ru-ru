---
title: Сравнительные характеристики XPath и LINQ to XML
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: e9bf192a2075653802f0c5a8b4e44ff0ceacb975
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "66487540"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Сравнительные характеристики XPath и LINQ to XML
XPath и LINQ to XML имеют некоторые сходные функциональные возможности. И то и другое можно использовать, чтобы запрашивать XML-дерево для возвращения таких результатов, как коллекция элементов, коллекция атрибутов, коллекция узлов или значение элемента или атрибута. Однако между ними также есть некоторые различия.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Различия между XPath и LINQ to XML  
 XPath не поддерживает проекции новых типов. Может возвращать только коллекции узлов из дерева, тогда как LINQ to XML может выполнить запрос и спроецировать граф объектов или XML-дерево в новой форме. Запросы LINQ to XML гораздо более эффективны и обладают большим набором возможностей по сравнению с выражениями XPath.  
  
 Выражение XPath представлено в изолированном виде, внутри строки. Компилятор C# не может выполнить синтаксический анализ выражения XPath во время компиляции. Напротив, компилятор C# проводит синтаксический анализ и компилирует запросы LINQ to XML. Компилятор способен обнаруживать многие ошибки запроса.  
  
 Результаты XPath не являются строго типизированными. В некоторых ситуациях результатом вычисления выражения XPath является объект, а задача определения соответствующего типа и приведения результата в соответствии с необходимостью возлагается на разработчика. В отличие от этого, проекции на основе запроса LINQ to XML являются строго типизированными.  
  
## <a name="result-ordering"></a>Упорядочение результатов  
 В документе XPath 1.0 Recommendation указано, что коллекция, которая является результатом вычисления выражения XPath, не упорядочена.  
  
 Однако при просмотре коллекции, возвращенной методом оси XPath LINQ to XML, можно отметить, что узлы в коллекции возвращены в том же порядке, что и в документе. И они располагаются так даже при доступе к осям XPath, где предикаты выражены в обратном порядке по отношению к документу, например `preceding` и `preceding-sibling`.  
  
 В отличие от этого, большинство осей LINQ to XML возвращают коллекции в порядке, соответствующем документу, однако две из них, <xref:System.Xml.Linq.XNode.Ancestors%2A> и <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, возвращают коллекции в порядке, обратном по отношению к документу. В следующей таблице перечисляются эти оси и указывается порядок коллекций для каждой из них.  
  
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
  
 В отличие от этого все позиционные предикаты в LINQ to XML всегда выражаются в порядке оси. Например, `anElement.ElementsBeforeSelf().ElementAt(0)` возвращает первый дочерний элемент родителя запрашиваемого элемента, а не ближайший предшествующий одноуровневый элемент. Другой пример: `anElement.Ancestors().ElementAt(0)` возвращает родительский элемент.  
  
 Если вам необходимо найти ближайший предшествующий элемент в LINQ to XML, следует использовать выражение:  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a>Различия в производительности  
 Запросы XPath, которые используют функциональность XPath в LINQ to XML, менее производительны по сравнению с запросами LINQ to XML.  
  
## <a name="comparison-of-composition"></a>Сравнение композиций  
 Состав запроса LINQ to XML немного напоминает состав выражения XPath, хотя по синтаксису они совершенно различны.  
  
 Например, если в переменной с именем `customers` имеется элемент и требуется найти внучатый элемент с именем `CompanyName` во всех дочерних элементах с именем `Customer`, то нужно написать следующее выражение XPath:  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 Эквивалентный запрос LINQ to XML:  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
```  

 Существуют похожие аналоги для каждой оси XPath.  
  
|Ось XPath|Ось LINQ to XML|  
|----------------|----------------------|  
|дочерняя (ось по умолчанию)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|родительская (...)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|ось атрибутов (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> or<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|ось ancestor|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|ось ancestor-or-self|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|дочерняя ось (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> or<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> or<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> or<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> or<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|following|Непосредственного эквивалента нет.|  
|preceding|Непосредственного эквивалента нет.|  
  