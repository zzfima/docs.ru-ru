---
title: Сохранение результатов запроса в памяти
description: Как сохранять результаты.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 66a7a95c74db4062e76c54d4339ccb7343f44067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "65633569"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="bcf56-103">Сохранение результатов запроса в памяти</span><span class="sxs-lookup"><span data-stu-id="bcf56-103">Store the results of a query in memory</span></span>

<span data-ttu-id="bcf56-104">Запрос, по сути, является набором инструкций, на основании которых осуществляется извлечение и организация данных.</span><span class="sxs-lookup"><span data-stu-id="bcf56-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="bcf56-105">Запросы выполняются медленно по мере выполнения запроса к каждому последующему элементу в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="bcf56-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="bcf56-106">При использовании `foreach` для итерации результатов элементы возвращаются как те, к которым был получен доступ.</span><span class="sxs-lookup"><span data-stu-id="bcf56-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="bcf56-107">Чтобы оценить запрос и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:</span><span class="sxs-lookup"><span data-stu-id="bcf56-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="bcf56-108">Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bcf56-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="bcf56-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bcf56-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="bcf56-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcf56-110">See also</span></span>

- [<span data-ttu-id="bcf56-111">LINQ</span><span class="sxs-lookup"><span data-stu-id="bcf56-111">Language Integrated Query (LINQ)</span></span>](index.md)
