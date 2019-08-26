---
title: Практическое руководство. Вычисление промежуточных значений (C#)
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 7b2dfc4e26fc7648cbd93b1e590079e4b105ad43
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594133"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="3a656-102">Практическое руководство. Вычисление промежуточных значений (C#)</span><span class="sxs-lookup"><span data-stu-id="3a656-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="3a656-103">В этом примере показано, как вычислять промежуточные значения, которые используются в сортировке, фильтрации и выборке.</span><span class="sxs-lookup"><span data-stu-id="3a656-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a656-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3a656-104">Example</span></span>  
 <span data-ttu-id="3a656-105">В следующем примере используется предложение `Let`.</span><span class="sxs-lookup"><span data-stu-id="3a656-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="3a656-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3a656-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="3a656-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3a656-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="3a656-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3a656-108">Example</span></span>  
 <span data-ttu-id="3a656-109">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3a656-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="3a656-110">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3a656-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3a656-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные в пространстве имен](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3a656-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="3a656-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3a656-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
