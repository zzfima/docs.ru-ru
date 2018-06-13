---
title: Сравнительные характеристики XPath и LINQ to XML1
ms.date: 07/20/2015
ms.assetid: c3fd07c1-6761-4e4b-8eb1-ddd780ed8d44
ms.openlocfilehash: fe6b0b77f82a9fcb5475e31e096a636211faa578
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644151"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Сравнительные характеристики XPath и LINQ to XML
XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] имеют некоторые сходные функциональные возможности. И то и другое можно использовать, чтобы запрашивать XML-дерево для возвращения таких результатов, как коллекция элементов, коллекция атрибутов, коллекция узлов или значение элемента или атрибута. Однако между ними также есть некоторые различия.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Различия между XPath и LINQ to XML  
 XPath не поддерживает проекции новых типов. Может возвращать только коллекции узлов из дерева, тогда как [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] может выполнить запрос, проецировав граф объектов или XML-дерево в новой форме. Запросы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] гораздо более эффективны и обладают большими возможностями, чем выражения XPath.  
  
 Выражение XPath представлено в изолированном виде, внутри строки. Компилятор Visual Basic не может выполнить синтаксический анализ выражения XPath во время компиляции. В отличие от этого [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] анализируются и компилируются компилятором основные theVisual запросов. Компилятор способен обнаруживать многие ошибки запроса.  
  
 Результаты XPath не являются строго типизированными. В некоторых ситуациях результатом вычисления выражения XPath является объект, а задача определения соответствующего типа и приведения результата в соответствии с необходимостью возлагается на разработчика. В отличие от этого, проекции на основе запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] являются строго типизированными.  
  
## <a name="result-ordering"></a>Упорядочение результатов  
 В документе XPath 1.0 Recommendation указано, что коллекция, которая является результатом вычисления выражения XPath, не упорядочена.  
  
 Однако при просмотре коллекции, возвращенной методом оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XPath, можно отметить, что узлы в коллекции возвращены в том же порядке, что и в документе. И они располагаются так даже при доступе к осям XPath, где предикаты выражены в обратном порядке по отношению к документу, например `preceding` и `preceding-sibling`.  
  
 В отличие от этого, большинство осей [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] возвращают коллекции в порядке, соответствующем документу, однако две из них, <xref:System.Xml.Linq.XNode.Ancestors%2A> и <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, возвращают коллекции в порядке, обратном по отношению к документу. В следующей таблице перечисляются эти оси и указывается порядок коллекций для каждой из них.  
  
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
  
 Если бы потребовалось найти ближайший предшествующий элемент в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], то было бы написано следующее выражение:  
  
 `ElementsBeforeSelf().Last()`  
  
## <a name="performance-differences"></a>Различия в производительности  
 Запросы XPath, которые используют функциональность XPath в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], менее производительны, чем запросы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="comparison-of-composition"></a>Сравнение композиций  
 Композиция запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] немного напоминает композицию выражения XPath, хотя по синтаксису они совершенно различны.  
  
 Например, если в переменной с именем `customers` имеется элемент и требуется найти внучатый элемент с именем `CompanyName` во всех дочерних элементах с именем `Customer`, то нужно написать следующее выражение XPath:  
  
```vb  
customers.XPathSelectElements("./Customer/CompanyName")  
```  
  
 Эквивалентное выражение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] таково:  
  
```vb  
customers.Element("Customer").Elements("CompanyName")  
```  
  
 Существуют похожие аналоги для каждой оси XPath.  
  
|Ось XPath|Ось LINQ to XML|  
|----------------|----------------------|  
|дочерняя (ось по умолчанию)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|родительская (...)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|ось атрибутов (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|ось ancestor|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|ось ancestor-or-self|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|дочерняя ось (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> или<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|following|Непосредственного эквивалента нет.|  
|preceding|Непосредственного эквивалента нет.|  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
