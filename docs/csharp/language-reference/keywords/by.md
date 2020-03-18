---
title: Справочник по C#. Контекстное ключевое слово by
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 4fa32a0dbfd8210ef8537aee849a55414b107a7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713734"
---
# <a name="by-c-reference"></a><span data-ttu-id="fc76a-102">by (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fc76a-102">by (C# Reference)</span></span>

<span data-ttu-id="fc76a-103">Контекстное ключевое слово `by` используется в предложении `group` в выражении запроса для определения способа группировки возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="fc76a-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="fc76a-104">Дополнительные сведения см. в разделе [Предложение group](./group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fc76a-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="fc76a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="fc76a-105">Example</span></span>

<span data-ttu-id="fc76a-106">В следующем примере показано использование контекстного слова `by` в предложении `group` для группировки студентов по первой букве фамилии.</span><span class="sxs-lookup"><span data-stu-id="fc76a-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="fc76a-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fc76a-107">See also</span></span>

- [<span data-ttu-id="fc76a-108">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="fc76a-108">LINQ in C#</span></span>](../../linq/index.md)
