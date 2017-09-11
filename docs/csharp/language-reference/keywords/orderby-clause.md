---
title: "Предложение orderby (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="31446-102">Предложение orderby (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="31446-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="31446-103">В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания.</span><span class="sxs-lookup"><span data-stu-id="31446-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="31446-104">Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей.</span><span class="sxs-lookup"><span data-stu-id="31446-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="31446-105">Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="31446-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="31446-106">По умолчанию используется порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="31446-106">The default sort order is ascending.</span></span> <span data-ttu-id="31446-107">Также можно указать настраиваемую функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="31446-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="31446-108">Тем не менее сделать это можно только с использованием синтаксиса на основе метода.</span><span class="sxs-lookup"><span data-stu-id="31446-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="31446-109">Дополнительные сведения см. в разделе [Сортировка данных](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span><span class="sxs-lookup"><span data-stu-id="31446-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31446-110">Пример</span><span class="sxs-lookup"><span data-stu-id="31446-110">Example</span></span>  
 <span data-ttu-id="31446-111">В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="31446-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="31446-112">(Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)</span><span class="sxs-lookup"><span data-stu-id="31446-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="31446-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="31446-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="31446-114">Пример</span><span class="sxs-lookup"><span data-stu-id="31446-114">Example</span></span>  
 <span data-ttu-id="31446-115">В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.</span><span class="sxs-lookup"><span data-stu-id="31446-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="31446-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="31446-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31446-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="31446-117">Remarks</span></span>  
 <span data-ttu-id="31446-118">Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="31446-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="31446-119">Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="31446-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31446-120">См. также</span><span class="sxs-lookup"><span data-stu-id="31446-120">See Also</span></span>  
 <span data-ttu-id="31446-121">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="31446-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="31446-122">[Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="31446-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="31446-123">[Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="31446-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="31446-124">[Предложение group](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="31446-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="31446-125">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="31446-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

