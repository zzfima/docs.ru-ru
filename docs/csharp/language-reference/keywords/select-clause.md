---
title: "Предложение \"select\" (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
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
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a><span data-ttu-id="8e388-102">Предложение "select" (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8e388-102">select clause (C# Reference)</span></span>
<span data-ttu-id="8e388-103">В выражении запроса предложение `select` задает тип значений, которые будут получены при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="8e388-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="8e388-104">Получаемый результат зависит от вычисления всех предыдущих предложений и любых выражений в самом предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="8e388-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="8e388-105">Выражение запроса должно оканчиваться предложением `select` или [group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8e388-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="8e388-106">В следующем примере показано простое предложение `select` в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="8e388-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 <span data-ttu-id="8e388-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e388-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="8e388-108">Тип последовательности, создаваемой предложением `select`, определяет тип переменной запроса `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="8e388-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="8e388-109">В самом простом случае предложение `select` просто задает переменную диапазона.</span><span class="sxs-lookup"><span data-stu-id="8e388-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="8e388-110">В этом случае возвращаемая последовательность содержит элементы того же типа, что и источник данных.</span><span class="sxs-lookup"><span data-stu-id="8e388-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="8e388-111">Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8e388-111">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="8e388-112">Тем не менее предложение `select` также реализует эффективный механизм для преобразования (или *проецирования*) данных источника в новые типы.</span><span class="sxs-lookup"><span data-stu-id="8e388-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="8e388-113">Дополнительные сведения см. в разделе [Преобразования данных с помощью LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="8e388-113">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e388-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8e388-114">Example</span></span>  
 <span data-ttu-id="8e388-115">В следующем примере показаны различные формы, которые может принимать предложение `select`.</span><span class="sxs-lookup"><span data-stu-id="8e388-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="8e388-116">В каждом запросе обратите внимание на связь между предложением `select` и типом *переменной запроса* (`studentQuery1`, `studentQuery2` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8e388-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 <span data-ttu-id="8e388-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e388-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="8e388-118">Как показано в `studentQuery8` в предыдущем примере, в некоторых случаях требуется, чтобы элементы возвращаемой последовательности содержали только подмножество свойств элементов источника.</span><span class="sxs-lookup"><span data-stu-id="8e388-118">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="8e388-119">Максимально уменьшая размер возвращаемой последовательности, вы можете снизить требования к памяти и, соответственно, повысить скорость выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="8e388-119">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="8e388-120">Это можно сделать, создав анонимный тип в предложении `select` и используя инициализатор объекта для его инициализации с соответствующими свойствами из элементов источника.</span><span class="sxs-lookup"><span data-stu-id="8e388-120">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="8e388-121">Пример того, как это сделать, см. в разделе [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="8e388-121">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e388-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e388-122">Remarks</span></span>  
 <span data-ttu-id="8e388-123">Во время компиляции предложение `select` преобразуется в вызов метода <xref:System.Linq.Enumerable.Select%2A> стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="8e388-123">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e388-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8e388-124">See Also</span></span>  
 <span data-ttu-id="8e388-125">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8e388-126">[Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-126">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="8e388-127">[Предложение From](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-127">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="8e388-128">[Разделяемый (метод) (справочник по C#)](../../../csharp/language-reference/keywords/partial-method.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-128">[partial (Method) (C# Reference)](../../../csharp/language-reference/keywords/partial-method.md) </span></span>  
 <span data-ttu-id="8e388-129">[Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-129">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="8e388-130">[Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-130">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="8e388-131">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="8e388-131">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

