---
title: "Практическое руководство. Сортировка элементов (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a5c17b13f6f637559e2f99426b71947e795e0516
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="0ba2d-102">Практическое руководство. Сортировка элементов (C#)</span><span class="sxs-lookup"><span data-stu-id="0ba2d-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="0ba2d-103">В этом примере показано, как создавать запросы с сортировкой результатов.</span><span class="sxs-lookup"><span data-stu-id="0ba2d-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ba2d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0ba2d-104">Example</span></span>  
 <span data-ttu-id="0ba2d-105">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0ba2d-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="0ba2d-106">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="0ba2d-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="0ba2d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0ba2d-107">Example</span></span>  
 <span data-ttu-id="0ba2d-108">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0ba2d-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0ba2d-109">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="0ba2d-109">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="0ba2d-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные пространства имен](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="0ba2d-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="0ba2d-111">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="0ba2d-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ba2d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0ba2d-112">See Also</span></span>  
 <span data-ttu-id="0ba2d-113">[Сортировка данных (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) </span><span class="sxs-lookup"><span data-stu-id="0ba2d-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) </span></span>  
 [<span data-ttu-id="0ba2d-114">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0ba2d-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

