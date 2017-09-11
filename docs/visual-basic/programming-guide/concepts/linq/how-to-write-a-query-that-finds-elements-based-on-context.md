---
title: "Практическое руководство: написать запрос для поиска элементов на основе контекста (Visual Basic) | Документы Microsoft"
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
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fd497c4d63c59eed1873f77f474bfb76eb0194c4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="c27ad-102">Практическое руководство: написать запрос для поиска элементов на основе контекста (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c27ad-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="c27ad-103">Иногда требуется написать запрос, который выбирает элементы, исходя из их контекста.</span><span class="sxs-lookup"><span data-stu-id="c27ad-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="c27ad-104">Может потребоваться использовать фильтрацию с учетом предыдущих или следующих одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="c27ad-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="c27ad-105">Может потребоваться использовать фильтрацию с учетом дочерних или родительских элементов.</span><span class="sxs-lookup"><span data-stu-id="c27ad-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="c27ad-106">Это можно сделать, написав запрос и используя результаты запроса в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="c27ad-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="c27ad-107">Если требуется сначала провести проверку на наличие значения null, а затем проверить само значение, более удобным будет выполнить запрос в предложении `let`, а затем использовать результаты в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="c27ad-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c27ad-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c27ad-108">Example</span></span>  
 <span data-ttu-id="c27ad-109">В следующем примере выбираются все элементы `p`, сразу за которыми следует элемент `ul`.</span><span class="sxs-lookup"><span data-stu-id="c27ad-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
  
```  
  
 <span data-ttu-id="c27ad-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="c27ad-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="c27ad-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c27ad-111">Example</span></span>  
 <span data-ttu-id="c27ad-112">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="c27ad-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c27ad-113">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c27ad-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c27ad-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="c27ad-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="c27ad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c27ad-115">See Also</span></span>  
 <span data-ttu-id="c27ad-116"><xref:System.Xml.Linq.XElement.Parse%2A></xref:System.Xml.Linq.XElement.Parse%2A></span><span class="sxs-lookup"><span data-stu-id="c27ad-116"><xref:System.Xml.Linq.XElement.Parse%2A></span></span>   
 <span data-ttu-id="c27ad-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="c27ad-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 <span data-ttu-id="c27ad-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="c27ad-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>   
 <span data-ttu-id="c27ad-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="c27ad-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></span></span>   
<span data-ttu-id="c27ad-120"> [Базовые запросы (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="c27ad-120"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span></span>
