---
title: Запрос коллекции объектов
description: Описывает, как запрашивать коллекции.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="27923-104">Запрос коллекции объектов</span><span class="sxs-lookup"><span data-stu-id="27923-104">Query a collection of objects</span></span>
<span data-ttu-id="27923-105">В этом примере показано, как выполнить простой запрос к списку объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="27923-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="27923-106">Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.</span><span class="sxs-lookup"><span data-stu-id="27923-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="27923-107">Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.</span><span class="sxs-lookup"><span data-stu-id="27923-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27923-108">Пример</span><span class="sxs-lookup"><span data-stu-id="27923-108">Example</span></span>  
 <span data-ttu-id="27923-109">Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="27923-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="27923-110">Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать.</span><span class="sxs-lookup"><span data-stu-id="27923-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="27923-111">Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.</span><span class="sxs-lookup"><span data-stu-id="27923-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="27923-112">См. также</span><span class="sxs-lookup"><span data-stu-id="27923-112">See also</span></span>  
 [<span data-ttu-id="27923-113">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="27923-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="27923-114">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="27923-114">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
