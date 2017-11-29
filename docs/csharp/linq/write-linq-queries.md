---
title: "Создание запросов LINQ на языке C#"
description: "Содержит инструкции по написанию запросов."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: f3efbfd232bd7e19d3db56289f57724c71dca064
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="e1e5e-104">Создание запросов LINQ на языке C#</span><span class="sxs-lookup"><span data-stu-id="e1e5e-104">Write LINQ queries in C#</span></span>

<span data-ttu-id="e1e5e-105">В этом разделе рассматриваются три способа создания запросов LINQ в C#:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-105">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="e1e5e-106">Используя синтаксис запроса.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-106">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="e1e5e-107">Используя синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-107">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="e1e5e-108">Используя комбинацию синтаксиса запроса и синтаксиса метода.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-108">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="e1e5e-109">Следующие примеры демонстрируют некоторые простые запросы LINQ, составленные с использованием каждого из указанных выше методов.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-109">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="e1e5e-110">Как правило, по возможности следует использовать метод (1), а (2) или (3) при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-110">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1e5e-111">Эти запросы обращаются к простым коллекциям в памяти, однако базовый синтаксис при этом точно такой же, как в запросах LINQ to Entities и LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-111">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e5e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e5e-112">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="e1e5e-113">Синтаксис запроса</span><span class="sxs-lookup"><span data-stu-id="e1e5e-113">Query syntax</span></span>  
 <span data-ttu-id="e1e5e-114">Для создания запросов рекомендуется использовать *синтаксис запроса*, позволяющий создавать *выражения запросов*.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-114">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="e1e5e-115">В следующем примере показаны три выражения запросов.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-115">The following example shows three query expressions.</span></span> <span data-ttu-id="e1e5e-116">Первое выражение запроса показывает, как фильтровать или ограничивать результаты, применяя условия в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-116">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="e1e5e-117">Оно возвращает все элементы исходной последовательности, значения которых больше 7 или меньше 3.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-117">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="e1e5e-118">Второе выражение показывает, как сортировать возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-118">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="e1e5e-119">Третье выражение показывает, как группировать результаты по ключу.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-119">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="e1e5e-120">Этот запрос возвращает две группы на основе первой буквы слова.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-120">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="e1e5e-121">Обратите внимание, что запросы имеют тип <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-121">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e1e5e-122">Все эти запросы можно написать с помощью `var`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-122">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="e1e5e-123">В каждом из предыдущих примеров запросы фактически не выполняются, пока не произойдет итерация переменной запроса в операторе `foreach` или другом операторе.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-123">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="e1e5e-124">Дополнительные сведения см. в разделе [Введение в запросы LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e1e5e-124">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e5e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e5e-125">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="e1e5e-126">Синтаксис метода</span><span class="sxs-lookup"><span data-stu-id="e1e5e-126">Method syntax</span></span>  
 <span data-ttu-id="e1e5e-127">Некоторые операции запросов должны быть выражены как вызов метода.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-127">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="e1e5e-128">Как правило, такие методы возвращают одноэлементные числовые значения, например <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> и другие.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-128">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="e1e5e-129">Эти методы необходимо вызывать в запросе последними, поскольку представляют только одно значение и не могут служить источником для дополнительной операции запроса.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-129">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="e1e5e-130">В следующем примере показан вызов метода в выражении запроса:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-130">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="e1e5e-131">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e5e-131">Example</span></span>  
 <span data-ttu-id="e1e5e-132">Если метод имеет параметры Action или Func, они предоставляются в виде [лямбда](../programming-guide/statements-expressions-operators/lambda-expressions.md)-выражения, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-132">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="e1e5e-133">Из числа предыдущих запросов незамедлительно выполняется только запрос 4.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-133">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="e1e5e-134">Это связано с тем, что возвращается одно значение, а не универсальная коллекция <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-134">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="e1e5e-135">Сам метод для вычисления значения должен использовать `foreach`.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-135">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="e1e5e-136">Каждый из предыдущих запросов может быть написан с использованием неявной типизации по переменной [var](../language-reference/keywords/var.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-136">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="e1e5e-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e5e-137">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="e1e5e-138">Смешанный синтаксис запроса и метода</span><span class="sxs-lookup"><span data-stu-id="e1e5e-138">Mixed query and method syntax</span></span>  
 <span data-ttu-id="e1e5e-139">В этом примере показано, как применять синтаксис метода к результатам предложения запроса.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-139">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="e1e5e-140">Просто заключите выражение запроса в круглые скобки, а затем примените оператор точки и вызовите метод.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-140">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="e1e5e-141">В следующем примере запрос 7 возвращает количество чисел со значением от 3 до 7.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-141">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="e1e5e-142">При этом в целом сохранять результат вызова метода лучше во вторую переменную.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-142">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="e1e5e-143">В этом случае меньше вероятность спутать запрос с его результатами.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-143">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="e1e5e-144">Поскольку запрос 7 возвращает одно значение, а не коллекцию, он выполняется незамедлительно.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-144">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="e1e5e-145">Предыдущий запрос можно написать, используя неявную типизацию с переменной `var`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-145">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="e1e5e-146">При записи в синтаксисе метода он будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-146">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="e1e5e-147">При записи с явной типизацией он будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-147">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e5e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e5e-148">See Also</span></span>  
  <span data-ttu-id="e1e5e-149">[Пошаговое руководство. Написание запросов на C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="e1e5e-149">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="e1e5e-150">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="e1e5e-150">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="e1e5e-151">предложение where</span><span class="sxs-lookup"><span data-stu-id="e1e5e-151">where clause</span></span>](../language-reference/keywords/where-clause.md)
