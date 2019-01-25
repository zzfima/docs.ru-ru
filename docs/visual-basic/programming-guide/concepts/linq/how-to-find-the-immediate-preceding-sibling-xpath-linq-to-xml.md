---
title: Как выполнить Найти ближайший предшествующий одноуровневый элемент (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: 81113c30cae0eb29fe0cf4b783fb031156353130
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572478"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="5da00-102">Как выполнить Найти ближайший предшествующий одноуровневый элемент (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5da00-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5da00-103">Иногда требуется найти ближайший предшествующий одноуровневый элемент узла.</span><span class="sxs-lookup"><span data-stu-id="5da00-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="5da00-104">Из-за разности в семантике позиционных предикатов для осей предшествующих одноуровневых элементов в XPath и в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] это сравнение является одним из наиболее интересных.</span><span class="sxs-lookup"><span data-stu-id="5da00-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5da00-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5da00-105">Example</span></span>  
 <span data-ttu-id="5da00-106">В этом примере в запросе [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] оператор <xref:System.Linq.Enumerable.Last%2A> используется для обнаружения последнего узла в коллекции, возвращенной методом <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="5da00-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="5da00-107">В отличие от этого, в выражении XPath для обнаружения ближайшего предшествующего элемента используется предикат со значением 1.</span><span class="sxs-lookup"><span data-stu-id="5da00-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1/>  
        <Child2/>  
        <Child3/>  
        <Child4/>  
    </Root>  
Dim child4 As XElement = root.Element("Child4")  
  
' LINQ to XML query  
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()  
  
' XPath expression  
Dim el2 As XElement = _  
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _  
    IEnumerable).Cast(Of XElement)().First()  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="5da00-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5da00-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="5da00-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5da00-109">See also</span></span>
- [<span data-ttu-id="5da00-110">LINQ to XML для пользователей XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5da00-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
