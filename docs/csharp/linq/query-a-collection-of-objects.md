---
title: "Запрос коллекции объектов"
description: "Описывает, как запрашивать коллекции."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="1f427-104">Запрос коллекции объектов</span><span class="sxs-lookup"><span data-stu-id="1f427-104">Query a collection of objects</span></span>
<span data-ttu-id="1f427-105">В этом примере показано, как выполнить простой запрос к списку объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="1f427-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="1f427-106">Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.</span><span class="sxs-lookup"><span data-stu-id="1f427-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="1f427-107">Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.</span><span class="sxs-lookup"><span data-stu-id="1f427-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f427-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1f427-108">Example</span></span>  
 <span data-ttu-id="1f427-109">Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.</span><span class="sxs-lookup"><span data-stu-id="1f427-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 <span data-ttu-id="1f427-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f427-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="1f427-111">Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать.</span><span class="sxs-lookup"><span data-stu-id="1f427-111">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="1f427-112">Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.</span><span class="sxs-lookup"><span data-stu-id="1f427-112">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="1f427-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1f427-113">See also</span></span>  
 [<span data-ttu-id="1f427-114">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="1f427-114">LINQ Query Expressions</span></span>](index.md)

