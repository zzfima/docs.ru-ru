---
title: "Предложение where (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="8041a-102">Предложение where (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8041a-102">where clause (C# Reference)</span></span>
<span data-ttu-id="8041a-103">Предложение `where` используется в выражении запроса для того, чтобы указать, какие элементы из источника данных будут возвращаться в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="8041a-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="8041a-104">Оно применяет логическое условие (*предикат*) к каждому исходному элементу (на который ссылается переменная диапазона) и возвращает те из них, для которых указанное условие имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="8041a-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="8041a-105">Одно выражение запроса может содержать сразу несколько предложений `where`, а одно предложение — несколько частей выражения предиката.</span><span class="sxs-lookup"><span data-stu-id="8041a-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8041a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8041a-106">Example</span></span>  
 <span data-ttu-id="8041a-107">В следующем примере предложение `where` отфильтровывает все номера, кроме тех, которые меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="8041a-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="8041a-108">Если удалить предложение `where`, возвращаются все номера из источника данных.</span><span class="sxs-lookup"><span data-stu-id="8041a-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="8041a-109">Выражение `num < 5` является предикатом, который применяется к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="8041a-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="8041a-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8041a-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8041a-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8041a-111">Example</span></span>  
 <span data-ttu-id="8041a-112">В одном предложении `where` можно указать необходимое число предикатов, используя операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8041a-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="8041a-113">В следующем примере запрос определяет два предиката, позволяющие отобрать только четные номера меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="8041a-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="8041a-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8041a-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8041a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="8041a-115">Example</span></span>  
 <span data-ttu-id="8041a-116">Предложение `where` может содержать один или несколько методов, возвращающих логические значения.</span><span class="sxs-lookup"><span data-stu-id="8041a-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="8041a-117">В следующем примере предложение `where` использует метод для того, чтобы определить, является ли текущее значение диапазона четным или нечетным.</span><span class="sxs-lookup"><span data-stu-id="8041a-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="8041a-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8041a-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8041a-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="8041a-119">Remarks</span></span>  
 <span data-ttu-id="8041a-120">Предложение `where` представляет собой механизм фильтрации.</span><span class="sxs-lookup"><span data-stu-id="8041a-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="8041a-121">Он может располагаться практически в любом месте выражения запроса, но не может быть первым или последним предложением.</span><span class="sxs-lookup"><span data-stu-id="8041a-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="8041a-122">Предложение `where` может отображаться до или после предложения [group](../../../csharp/language-reference/keywords/group-clause.md) в зависимости от того, необходимо ли отфильтровать исходные элементы до или после их объединения в группы.</span><span class="sxs-lookup"><span data-stu-id="8041a-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="8041a-123">Если указанный предикат недопустим для элементов в источнике данных, это вызовет ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="8041a-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="8041a-124">Это одно из преимуществ надежной проверки типов, предоставляемой [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8041a-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="8041a-125">Во время компиляции ключевое слово `where` преобразуется в вызов метода стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="8041a-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8041a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8041a-126">See Also</span></span>  
 <span data-ttu-id="8041a-127">[Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8041a-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="8041a-128">[Предложение From](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8041a-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="8041a-129">[Предложение Select](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8041a-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="8041a-130">[Фильтрация данных](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="8041a-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="8041a-131">[Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="8041a-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="8041a-132">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="8041a-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

