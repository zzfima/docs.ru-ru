---
title: Справочник по C#. Контекстное ключевое слово by
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 23daf2aaf5d9456c76c5b2ac889243b1ed31b077
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602220"
---
# <a name="by-c-reference"></a><span data-ttu-id="b8209-102">by (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b8209-102">by (C# Reference)</span></span>

<span data-ttu-id="b8209-103">Контекстное ключевое слово `by` используется в предложении `group` в выражении запроса для определения способа группировки возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="b8209-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="b8209-104">Дополнительные сведения см. в разделе [Предложение group](./group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b8209-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="b8209-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b8209-105">Example</span></span>

<span data-ttu-id="b8209-106">В следующем примере показано использование контекстного слова `by` в предложении `group` для группировки студентов по первой букве фамилии.</span><span class="sxs-lookup"><span data-stu-id="b8209-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="b8209-107">См. также</span><span class="sxs-lookup"><span data-stu-id="b8209-107">See also</span></span>

- [<span data-ttu-id="b8209-108">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="b8209-108">LINQ Query Expressions</span></span>](../../programming-guide/linq-query-expressions/index.md)
