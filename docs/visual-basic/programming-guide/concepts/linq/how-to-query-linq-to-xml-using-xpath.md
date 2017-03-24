---
title: "Практическое руководство: запрос LINQ to XML с помощью XPath (Visual Basic) | Документы Microsoft"
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
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0356a7210fbc1b1e0c15adc9d37b6099877fa655
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a>Практическое руководство: запрос LINQ to XML с помощью XPath (Visual Basic)
В этом разделе описываются методы расширения, обеспечивающие запрос XML-дерева с помощью XPath. Подробные сведения об использовании этих методов расширения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName>  
  
 Рекомендуется использовать XPath с LINQ to XML, только если есть основательная причина для применения запросов на основе XPath, такая как широкое использование кода прежних версий. Запросы XPath не действуют так же как [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] запросов.  
  
## <a name="example"></a>Пример  
 В следующем примере создается небольшое XML-дерево и использует <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>для выбора набора элементов.</xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>  
  
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
  
```  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы создания запросов (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
