---
title: "Возврат запроса из метода"
description: "Как возвратить запрос."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="b87d9-104">Практическое руководство. Возврат запроса из метода (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b87d9-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="b87d9-105">В этом примере показан способ возврата запроса из метода в качестве возвращаемого значения и параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="b87d9-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="b87d9-106">Объекты запроса являются составляемыми, что означает возможность возврата запроса из метода.</span><span class="sxs-lookup"><span data-stu-id="b87d9-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="b87d9-107">Объекты, представляющие запросы, не сохраняют результирующую коллекцию, а сохраняют действия, необходимые для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="b87d9-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="b87d9-108">Преимущество возвращения объектов запроса заключается в том, что их можно комбинировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="b87d9-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="b87d9-109">Поэтому любое возвращаемое значение или параметр `out` метода, который возвращает запрос, должны также иметь этот тип.</span><span class="sxs-lookup"><span data-stu-id="b87d9-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="b87d9-110">Если метод материализует запрос в конкретный тип <xref:System.Collections.Generic.List%601> или <xref:System.Array>, считается, что он должен возвращать результаты запроса, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="b87d9-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="b87d9-111">Переменную запроса, возвращаемую из метода, можно формировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="b87d9-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b87d9-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b87d9-112">Example</span></span>  
 <span data-ttu-id="b87d9-113">В следующем примере первый метод возвращает запрос в качестве возвращаемого значения, а второй метод возвращает запрос в качестве параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="b87d9-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="b87d9-114">Обратите внимание, что в обоих случаях возвращается запрос, а не его результаты.</span><span class="sxs-lookup"><span data-stu-id="b87d9-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="b87d9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b87d9-115">See Also</span></span>  
 [<span data-ttu-id="b87d9-116">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="b87d9-116">LINQ Query Expressions</span></span>](index.md)
