---
title: into. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: ccb1463db51510d275b7053955a0257bd4fe621e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422713"
---
# <a name="into-c-reference"></a><span data-ttu-id="8725b-102">into (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8725b-102">into (C# Reference)</span></span>

<span data-ttu-id="8725b-103">Контекстное слово `into` можно использовать для создания временного идентификатора для сохранения результатов предложений [group](group-clause.md), [join](join-clause.md) или [select](select-clause.md) в новый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="8725b-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="8725b-104">Этот идентификатор может сам по себе стать источником дополнительных команд запроса.</span><span class="sxs-lookup"><span data-stu-id="8725b-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="8725b-105">При использовании в предложениях `group` или `select` применение нового идентификатора может называться *продолжением*.</span><span class="sxs-lookup"><span data-stu-id="8725b-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="8725b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8725b-106">Example</span></span>

<span data-ttu-id="8725b-107">В следующем примере показано использование ключевого слова `into` для создания временного идентификатора `fruitGroup`, который имеет выведенный тип `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="8725b-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="8725b-108">С помощью идентификатора можно вызвать метод <xref:System.Linq.Enumerable.Count%2A> для каждой группы и выбрать только те группы, которые содержат несколько слов.</span><span class="sxs-lookup"><span data-stu-id="8725b-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="8725b-109">Использование ключевого слова `into` в предложении `group` необходимо только в тех случаях, когда требуется выполнить дополнительные операции запроса для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="8725b-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="8725b-110">Дополнительные сведения см. в разделе [Предложение group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8725b-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="8725b-111">Пример использования ключевого слова `into` в предложении `join` см. в разделе [Предложение join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8725b-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8725b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8725b-112">See also</span></span>

- [<span data-ttu-id="8725b-113">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="8725b-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="8725b-114">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="8725b-114">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="8725b-115">предложение group</span><span class="sxs-lookup"><span data-stu-id="8725b-115">group clause</span></span>](group-clause.md)
