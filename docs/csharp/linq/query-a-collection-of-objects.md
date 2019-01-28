---
title: Запрос коллекции объектов (LINQ в C#)
description: Узнайте, как выполнять запросы к коллекциям с помощью LINQ в C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734507"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="b842b-103">Запрос коллекции объектов</span><span class="sxs-lookup"><span data-stu-id="b842b-103">Query a collection of objects</span></span>

<span data-ttu-id="b842b-104">В этом примере показано, как выполнить простой запрос к списку объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="b842b-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="b842b-105">Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.</span><span class="sxs-lookup"><span data-stu-id="b842b-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="b842b-106">Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.</span><span class="sxs-lookup"><span data-stu-id="b842b-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b842b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b842b-107">Example</span></span>

<span data-ttu-id="b842b-108">Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="b842b-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="b842b-109">Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать.</span><span class="sxs-lookup"><span data-stu-id="b842b-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="b842b-110">Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.</span><span class="sxs-lookup"><span data-stu-id="b842b-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b842b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b842b-111">See also</span></span>

- [<span data-ttu-id="b842b-112">LINQ</span><span class="sxs-lookup"><span data-stu-id="b842b-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="b842b-113">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="b842b-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
