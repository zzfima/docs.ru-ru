---
title: Предложение orderby. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 09a745fe3da3a5acb71972b9cf56391774c7016a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422640"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="5046f-102">Предложение orderby (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5046f-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="5046f-103">В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания.</span><span class="sxs-lookup"><span data-stu-id="5046f-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="5046f-104">Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей.</span><span class="sxs-lookup"><span data-stu-id="5046f-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="5046f-105">Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="5046f-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="5046f-106">По умолчанию используется порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="5046f-106">The default sort order is ascending.</span></span> <span data-ttu-id="5046f-107">Также можно указать настраиваемую функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="5046f-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="5046f-108">Тем не менее сделать это можно только с использованием синтаксиса на основе метода.</span><span class="sxs-lookup"><span data-stu-id="5046f-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="5046f-109">Дополнительные сведения см. в разделе [Сортировка данных](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="5046f-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="5046f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5046f-110">Example</span></span>

<span data-ttu-id="5046f-111">В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="5046f-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="5046f-112">(Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)</span><span class="sxs-lookup"><span data-stu-id="5046f-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="5046f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5046f-113">Example</span></span>

<span data-ttu-id="5046f-114">В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.</span><span class="sxs-lookup"><span data-stu-id="5046f-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="5046f-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5046f-115">Remarks</span></span>

<span data-ttu-id="5046f-116">Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="5046f-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="5046f-117">Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="5046f-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="5046f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5046f-118">See also</span></span>

- [<span data-ttu-id="5046f-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5046f-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5046f-120">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5046f-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="5046f-121">LINQ</span><span class="sxs-lookup"><span data-stu-id="5046f-121">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="5046f-122">предложение group</span><span class="sxs-lookup"><span data-stu-id="5046f-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="5046f-123">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="5046f-123">Getting Started with LINQ in C#</span></span>](/dotnet/csharp/programming-guide/concepts/linq/)
