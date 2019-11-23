---
title: Практическое руководство. Запрос LINQ to XML с использованием XPath
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: 563756c019ddd458d46f47c843e32ddc7bbaacd1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347647"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="b1b13-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1b13-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="b1b13-103">В этом разделе описываются методы расширения, обеспечивающие запрос XML-дерева с помощью XPath.</span><span class="sxs-lookup"><span data-stu-id="b1b13-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="b1b13-104">Подробные сведения об использовании данных методов расширения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1b13-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b1b13-105">Рекомендуется использовать XPath с LINQ to XML, только если есть основательная причина для применения запросов на основе XPath, такая как широкое использование кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="b1b13-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="b1b13-106">Запросы XPath не действуют столь эффективно, как запросы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1b13-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1b13-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b1b13-107">Example</span></span>  
 <span data-ttu-id="b1b13-108">В следующем примере создается небольшое XML-дерево и для получения набора элементов используется запрос <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1b13-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
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
  
 <span data-ttu-id="b1b13-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b1b13-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1b13-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b13-110">See also</span></span>

- [<span data-ttu-id="b1b13-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1b13-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
