---
title: "Сохранение результатов запроса в памяти"
description: "Как сохранять результаты."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 86a9c2d464eac83cabb5faa68987ad580fc31248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="ae92c-104">Сохранение результатов запроса в памяти</span><span class="sxs-lookup"><span data-stu-id="ae92c-104">Store the results of a query in memory</span></span>

<span data-ttu-id="ae92c-105">Запрос, по сути, является набором инструкций, на основании которых осуществляется извлечение и организация данных.</span><span class="sxs-lookup"><span data-stu-id="ae92c-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="ae92c-106">Запросы выполняются медленно по мере выполнения запроса к каждому последующему элементу в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="ae92c-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="ae92c-107">При использовании `foreach` для итерации результатов элементы возвращаются как те, к которым был получен доступ.</span><span class="sxs-lookup"><span data-stu-id="ae92c-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="ae92c-108">Чтобы оценить запрос и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:</span><span class="sxs-lookup"><span data-stu-id="ae92c-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="ae92c-109">Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ae92c-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae92c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ae92c-110">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="ae92c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ae92c-111">See Also</span></span>  
 [<span data-ttu-id="ae92c-112">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="ae92c-112">LINQ Query Expressions</span></span>](index.md)
