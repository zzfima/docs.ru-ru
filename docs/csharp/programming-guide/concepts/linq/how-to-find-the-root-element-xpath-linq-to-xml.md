---
title: Практическое руководство. Поиск корневого элемента (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 59696e6f3487bbb09135ba413a173c32dffa0c9b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485413"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="62042-102">Практическое руководство. Поиск корневого элемента (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="62042-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="62042-103">В этом разделе показан поиск корневого элемента с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62042-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="62042-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="62042-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="62042-105">Пример</span><span class="sxs-lookup"><span data-stu-id="62042-105">Example</span></span>  
 <span data-ttu-id="62042-106">В этом примере осуществляется поиск корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="62042-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="62042-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="62042-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="62042-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="62042-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
