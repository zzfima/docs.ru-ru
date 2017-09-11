---
title: "Возврат запроса из метода"
description: "Как возвратить запрос."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 747345f0a765bc6cbe947a2b0c7bc025eb599550
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="dde8f-104">Практическое руководство. Возврат запроса из метода (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="dde8f-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="dde8f-105">В этом примере показан способ возврата запроса из метода в качестве возвращаемого значения и параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="dde8f-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="dde8f-106">Объекты запроса являются составляемыми, что означает возможность возврата запроса из метода.</span><span class="sxs-lookup"><span data-stu-id="dde8f-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="dde8f-107">Объекты, представляющие запросы, не сохраняют результирующую коллекцию, а сохраняют действия, необходимые для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="dde8f-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="dde8f-108">Преимущество возвращения объектов запроса заключается в том, что их можно комбинировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="dde8f-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="dde8f-109">Поэтому любое возвращаемое значение или параметр `out` метода, который возвращает запрос, должны также иметь этот тип.</span><span class="sxs-lookup"><span data-stu-id="dde8f-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="dde8f-110">Если метод материализует запрос в конкретный тип <xref:System.Collections.Generic.List%601> или <xref:System.Array>, считается, что он должен возвращать результаты запроса, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="dde8f-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="dde8f-111">Переменную запроса, возвращаемую из метода, можно формировать или изменять.</span><span class="sxs-lookup"><span data-stu-id="dde8f-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dde8f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="dde8f-112">Example</span></span>  
 <span data-ttu-id="dde8f-113">В следующем примере первый метод возвращает запрос в качестве возвращаемого значения, а второй метод возвращает запрос в качестве параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="dde8f-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="dde8f-114">Обратите внимание, что в обоих случаях возвращается запрос, а не его результаты.</span><span class="sxs-lookup"><span data-stu-id="dde8f-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 <span data-ttu-id="dde8f-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dde8f-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dde8f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dde8f-116">See Also</span></span>  
 [<span data-ttu-id="dde8f-117">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="dde8f-117">LINQ Query Expressions</span></span>](index.md)

