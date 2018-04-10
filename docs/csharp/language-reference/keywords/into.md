---
title: into (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2400143e66c68942cdec3ebfa04cfdd8cfe983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="into-c-reference"></a><span data-ttu-id="1bfcc-102">into (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1bfcc-102">into (C# Reference)</span></span>
<span data-ttu-id="1bfcc-103">Контекстное слово `into` можно использовать для создания временного идентификатора для сохранения результатов предложений [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) или [select](../../../csharp/language-reference/keywords/select-clause.md) в новый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) or [select](../../../csharp/language-reference/keywords/select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="1bfcc-104">Этот идентификатор может сам по себе стать источником дополнительных команд запроса.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="1bfcc-105">При использовании в предложениях `group` или `select` применение нового идентификатора может называться *продолжением*.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bfcc-106">Пример</span><span class="sxs-lookup"><span data-stu-id="1bfcc-106">Example</span></span>  
 <span data-ttu-id="1bfcc-107">В следующем примере показано использование ключевого слова `into` для создания временного идентификатора `fruitGroup`, который имеет выведенный тип `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="1bfcc-108">С помощью идентификатора можно вызвать метод <xref:System.Linq.Enumerable.Count%2A> для каждой группы и выбрать только те группы, которые содержат несколько слов.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 <span data-ttu-id="1bfcc-109">Использование ключевого слова `into` в предложении `group` необходимо только в тех случаях, когда требуется выполнить дополнительные операции запроса для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="1bfcc-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="1bfcc-110">Дополнительные сведения см. в разделе [Предложение group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1bfcc-110">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="1bfcc-111">Пример использования ключевого слова `into` в предложении `join` см. в разделе [Предложение join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1bfcc-111">For an example of the use of `into` in a `join` clause, see [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfcc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1bfcc-112">See Also</span></span>  
 [<span data-ttu-id="1bfcc-113">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="1bfcc-113">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="1bfcc-114">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="1bfcc-114">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="1bfcc-115">предложение group</span><span class="sxs-lookup"><span data-stu-id="1bfcc-115">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)
