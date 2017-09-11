---
title: "Сохранение результатов запроса в памяти"
description: "Как сохранять результаты."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 35d908bde06ef55ba2dc93a73211f7be33b9332c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="01dfb-104">Сохранение результатов запроса в памяти</span><span class="sxs-lookup"><span data-stu-id="01dfb-104">Store the results of a query in memory</span></span>

<span data-ttu-id="01dfb-105">Запрос, по сути, является набором инструкций, на основании которых осуществляется извлечение и организация данных.</span><span class="sxs-lookup"><span data-stu-id="01dfb-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="01dfb-106">Запросы выполняются медленно по мере выполнения запроса к каждому последующему элементу в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="01dfb-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="01dfb-107">При использовании `foreach` для итерации результатов элементы возвращаются как те, к которым был получен доступ.</span><span class="sxs-lookup"><span data-stu-id="01dfb-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="01dfb-108">Чтобы оценить запрос и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:</span><span class="sxs-lookup"><span data-stu-id="01dfb-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="01dfb-109">Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="01dfb-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="01dfb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="01dfb-110">Example</span></span>  
 <span data-ttu-id="01dfb-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="01dfb-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="01dfb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="01dfb-112">See Also</span></span>  
 [<span data-ttu-id="01dfb-113">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="01dfb-113">LINQ Query Expressions</span></span>](index.md)

