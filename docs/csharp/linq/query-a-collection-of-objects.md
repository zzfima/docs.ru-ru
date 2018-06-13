---
title: Запрос коллекции объектов
description: Описывает, как запрашивать коллекции.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: c690da2ae59d2a9b34a5bd403bc54797c4e95fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282396"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="d472a-103">Запрос коллекции объектов</span><span class="sxs-lookup"><span data-stu-id="d472a-103">Query a collection of objects</span></span>
<span data-ttu-id="d472a-104">В этом примере показано, как выполнить простой запрос к списку объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="d472a-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="d472a-105">Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.</span><span class="sxs-lookup"><span data-stu-id="d472a-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="d472a-106">Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.</span><span class="sxs-lookup"><span data-stu-id="d472a-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d472a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d472a-107">Example</span></span>  
 <span data-ttu-id="d472a-108">Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="d472a-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="d472a-109">Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать.</span><span class="sxs-lookup"><span data-stu-id="d472a-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="d472a-110">Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.</span><span class="sxs-lookup"><span data-stu-id="d472a-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="d472a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d472a-111">See also</span></span>  
 [<span data-ttu-id="d472a-112">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="d472a-112">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="d472a-113">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="d472a-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
