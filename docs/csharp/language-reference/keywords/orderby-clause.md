---
title: Предложение orderby. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: cd76b2c33fe1a1a986bc05e3c3ed5f22809686ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173579"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="905cc-102">Предложение orderby (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="905cc-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="905cc-103">В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания.</span><span class="sxs-lookup"><span data-stu-id="905cc-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="905cc-104">Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей.</span><span class="sxs-lookup"><span data-stu-id="905cc-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="905cc-105">Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="905cc-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="905cc-106">По умолчанию используется порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="905cc-106">The default sort order is ascending.</span></span> <span data-ttu-id="905cc-107">Также можно указать настраиваемую функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="905cc-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="905cc-108">Тем не менее сделать это можно только с использованием синтаксиса на основе метода.</span><span class="sxs-lookup"><span data-stu-id="905cc-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="905cc-109">Дополнительные сведения см. в разделе [Сортировка данных](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="905cc-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="905cc-110">Пример</span><span class="sxs-lookup"><span data-stu-id="905cc-110">Example</span></span>

<span data-ttu-id="905cc-111">В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="905cc-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="905cc-112">(Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)</span><span class="sxs-lookup"><span data-stu-id="905cc-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="905cc-113">Пример</span><span class="sxs-lookup"><span data-stu-id="905cc-113">Example</span></span>

<span data-ttu-id="905cc-114">В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.</span><span class="sxs-lookup"><span data-stu-id="905cc-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="905cc-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="905cc-115">Remarks</span></span>

<span data-ttu-id="905cc-116">Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="905cc-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="905cc-117">Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="905cc-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="905cc-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="905cc-118">See also</span></span>

- [<span data-ttu-id="905cc-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="905cc-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="905cc-120">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="905cc-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="905cc-121">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="905cc-121">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="905cc-122">предложение group</span><span class="sxs-lookup"><span data-stu-id="905cc-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="905cc-123">LINQ</span><span class="sxs-lookup"><span data-stu-id="905cc-123">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
