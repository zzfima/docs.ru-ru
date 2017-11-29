---
title: "Как: поиск элементов-потомков (XPath-LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32a8debaab957e2739a7b489554acc6f9affddfe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="8d12c-102">Как: поиск элементов-потомков (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d12c-102">How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8d12c-103">В этом разделе рассказывается, как возвращать элементы-потомки с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="8d12c-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="8d12c-104">Выражение XPath - `//Name`.</span><span class="sxs-lookup"><span data-stu-id="8d12c-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d12c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8d12c-105">Example</span></span>  
 <span data-ttu-id="8d12c-106">В этом примере обнаруживаются все потомки с именем `Name`.</span><span class="sxs-lookup"><span data-stu-id="8d12c-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="8d12c-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8d12c-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="8d12c-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8d12c-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d12c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8d12c-109">See Also</span></span>  
 [<span data-ttu-id="8d12c-110">LINQ to XML для пользователей XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d12c-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
