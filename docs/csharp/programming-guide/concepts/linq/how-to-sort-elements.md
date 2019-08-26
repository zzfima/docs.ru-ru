---
title: Практическое руководство. Сортировка элементов (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 074428413fa57d8f0e5ae94970c2aeeeb9e4cc7c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592454"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="8278e-102">Практическое руководство. Сортировка элементов (C#)</span><span class="sxs-lookup"><span data-stu-id="8278e-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="8278e-103">В этом примере показано, как создавать запросы с сортировкой результатов.</span><span class="sxs-lookup"><span data-stu-id="8278e-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8278e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8278e-104">Example</span></span>  
 <span data-ttu-id="8278e-105">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8278e-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="8278e-106">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="8278e-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="8278e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8278e-107">Example</span></span>  
 <span data-ttu-id="8278e-108">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8278e-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="8278e-109">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8278e-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="8278e-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные в пространстве имен](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="8278e-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="8278e-111">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="8278e-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="8278e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8278e-112">See also</span></span>

- [<span data-ttu-id="8278e-113">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="8278e-113">Sorting Data (C#)</span></span>](./sorting-data.md)
