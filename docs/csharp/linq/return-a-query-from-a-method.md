---
title: Возврат запроса из метода
description: Как возвратить запрос.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1df533770f76301432b104d6f8398f1687750cce
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972515"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="c53c2-103">Практическое руководство. Возврат запроса из метода (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c53c2-103">How to return a query from a method (C# Programming Guide)</span></span>
<span data-ttu-id="c53c2-104">В этом примере показан способ возврата запроса из метода в качестве возвращаемого значения и параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="c53c2-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="c53c2-105">Объекты запроса являются составляемыми, что означает возможность возврата запроса из метода.</span><span class="sxs-lookup"><span data-stu-id="c53c2-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="c53c2-106">Объекты, представляющие запросы, не сохраняют результирующую коллекцию, а сохраняют действия, необходимые для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="c53c2-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="c53c2-107">Преимущество возвращения объектов запроса заключается в том, что их можно комбинировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="c53c2-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="c53c2-108">Поэтому любое возвращаемое значение или параметр `out` метода, который возвращает запрос, должны также иметь этот тип.</span><span class="sxs-lookup"><span data-stu-id="c53c2-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="c53c2-109">Если метод материализует запрос в конкретный тип <xref:System.Collections.Generic.List%601> или <xref:System.Array>, считается, что он должен возвращать результаты запроса, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="c53c2-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="c53c2-110">Переменную запроса, возвращаемую из метода, можно формировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="c53c2-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c53c2-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c53c2-111">Example</span></span>  
 <span data-ttu-id="c53c2-112">В следующем примере первый метод возвращает запрос в качестве возвращаемого значения, а второй метод возвращает запрос в качестве параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="c53c2-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="c53c2-113">Обратите внимание, что в обоих случаях возвращается запрос, а не его результаты.</span><span class="sxs-lookup"><span data-stu-id="c53c2-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="c53c2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c53c2-114">See also</span></span>

- [<span data-ttu-id="c53c2-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="c53c2-115">Language Integrated Query (LINQ)</span></span>](index.md)
