---
title: "Практическое руководство: фильтрация по именам элементов (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 07f7867b0fc5cf79ba5ce06f95b07b5c538e83d3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="d2158-102">Практическое руководство: фильтрация по именам элементов (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2158-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d2158-103">При вызове одного из методов, возвращающих <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>, можно выполнить фильтрацию по имени элемента.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d2158-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2158-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d2158-104">Example</span></span>  
 <span data-ttu-id="d2158-105">В этом примере показано получение отфильтрованной коллекции потомков, в которой содержатся только потомки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="d2158-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="d2158-106">В этом примере используется следующий XML-документ: [пример XML-файла: типичный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d2158-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
<span data-ttu-id="d2158-107"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d2158-107"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="d2158-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="d2158-108">This code produces the following output:</span></span>  
  
<span data-ttu-id="d2158-109"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d2158-109"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="d2158-110">Методы, которые возвращают <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>коллекции следуют тому же шаблону.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d2158-110">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="d2158-111">Их сигнатуры подобны <xref:System.Xml.Linq.XContainer.Elements%2A>и <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-111">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="d2158-112">Ниже следует полный список методов, имеющих аналогичные сигнатурам методов:</span><span class="sxs-lookup"><span data-stu-id="d2158-112">The following is the complete list of methods that have similar method signatures:</span></span>  
  
-   <span data-ttu-id="d2158-113"><xref:System.Xml.Linq.XNode.Ancestors%2A></xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-113"><xref:System.Xml.Linq.XNode.Ancestors%2A></span></span>  
  
-   <span data-ttu-id="d2158-114"><xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-114"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>  
  
-   <span data-ttu-id="d2158-115"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>  
  
-   <span data-ttu-id="d2158-116"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-116"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>  
  
-   <span data-ttu-id="d2158-117"><xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-117"><xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></span></span>  
  
-   <span data-ttu-id="d2158-118"><xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-118"><xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></span></span>  
  
-   <span data-ttu-id="d2158-119"><xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d2158-119"><xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></span></span>  
  
## <a name="example"></a><span data-ttu-id="d2158-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d2158-120">Example</span></span>  
 <span data-ttu-id="d2158-121">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="d2158-121">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d2158-122">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="d2158-122">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="d2158-123">В этом примере используется следующий XML-документ: [пример XML-файла: типичный заказ на покупку в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d2158-123">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d2158-124">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="d2158-124">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2158-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d2158-125">See Also</span></span>  
 [<span data-ttu-id="d2158-126">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2158-126">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
