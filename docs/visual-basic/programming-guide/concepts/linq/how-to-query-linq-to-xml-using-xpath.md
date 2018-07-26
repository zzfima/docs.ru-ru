---
title: 'Практическое: запрос LINQ to XML с использованием XPath (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: d8f23bd8417c3f59377e5e677b08e403ecc1122d
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244352"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a>Практическое: запрос LINQ to XML с использованием XPath (Visual Basic)
В этом разделе описываются методы расширения, обеспечивающие запрос XML-дерева с помощью XPath. Подробные сведения об использовании данных методов расширения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 Рекомендуется использовать XPath с LINQ to XML, только если есть основательная причина для применения запросов на основе XPath, такая как широкое использование кода прежних версий. Запросы XPath не действуют столь эффективно, как запросы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере создается небольшое XML-дерево и для получения набора элементов используется запрос <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы создания запросов (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
