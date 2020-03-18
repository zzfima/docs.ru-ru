---
title: Возврат запроса из метода
description: Как возвратить запрос.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1df533770f76301432b104d6f8398f1687750cce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972515"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="f9f8c-103">Практическое руководство. Возврат запроса из метода (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f9f8c-103">How to return a query from a method (C# Programming Guide)</span></span>
<span data-ttu-id="f9f8c-104">В этом примере показан способ возврата запроса из метода в качестве возвращаемого значения и параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="f9f8c-105">Объекты запроса являются составляемыми, что означает возможность возврата запроса из метода.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="f9f8c-106">Объекты, представляющие запросы, не сохраняют результирующую коллекцию, а сохраняют действия, необходимые для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="f9f8c-107">Преимущество возвращения объектов запроса заключается в том, что их можно комбинировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="f9f8c-108">Поэтому любое возвращаемое значение или параметр `out` метода, который возвращает запрос, должны также иметь этот тип.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="f9f8c-109">Если метод материализует запрос в конкретный тип <xref:System.Collections.Generic.List%601> или <xref:System.Array>, считается, что он должен возвращать результаты запроса, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="f9f8c-110">Переменную запроса, возвращаемую из метода, можно формировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9f8c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f9f8c-111">Example</span></span>  
 <span data-ttu-id="f9f8c-112">В следующем примере первый метод возвращает запрос в качестве возвращаемого значения, а второй метод возвращает запрос в качестве параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="f9f8c-113">Обратите внимание, что в обоих случаях возвращается запрос, а не его результаты.</span><span class="sxs-lookup"><span data-stu-id="f9f8c-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="f9f8c-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9f8c-114">See also</span></span>

- [<span data-ttu-id="f9f8c-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="f9f8c-115">Language Integrated Query (LINQ)</span></span>](index.md)
