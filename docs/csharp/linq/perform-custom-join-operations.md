---
title: "Выполнение пользовательских операций соединения"
description: "Сведения о выполнении пользовательских операций соединения."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: fef146c92a5cbbf21f8f1688f221c2bd45c99de7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="dced7-104">Выполнение пользовательских операций соединения</span><span class="sxs-lookup"><span data-stu-id="dced7-104">Perform custom join operations</span></span>

<span data-ttu-id="dced7-105">В этом примере показано, как выполнить операции соединения, которые нельзя осуществить с помощью предложения `join`.</span><span class="sxs-lookup"><span data-stu-id="dced7-105">This example shows how to perform join operations that are not possible with the `join` clause.</span></span> <span data-ttu-id="dced7-106">В выражении запроса предложение `join` ограничено уравнивающими соединениями и оптимизировано для них; они являются самым общим типом операций соединения.</span><span class="sxs-lookup"><span data-stu-id="dced7-106">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="dced7-107">При выполнении уравнивающего соединения использование предложения `join` почти всегда обеспечивает наилучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="dced7-107">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>  
  
 <span data-ttu-id="dced7-108">Однако предложение `join` нельзя использовать в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="dced7-108">However, the `join` clause cannot be used in the following cases:</span></span>  
  
-   <span data-ttu-id="dced7-109">Соединение объявлено в выражении неравенства (не уравнивающее соединение).</span><span class="sxs-lookup"><span data-stu-id="dced7-109">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>  
  
-   <span data-ttu-id="dced7-110">Соединение объявлено в нескольких выражениях равенства или неравенства.</span><span class="sxs-lookup"><span data-stu-id="dced7-110">When the join is predicated on more than one expression of equality or inequality.</span></span>  
  
-   <span data-ttu-id="dced7-111">Необходимость создания временной переменной диапазона для правосторонней (внутренней) последовательности перед операцией соединения.</span><span class="sxs-lookup"><span data-stu-id="dced7-111">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>  
  
 <span data-ttu-id="dced7-112">Чтобы независимо представить каждый источник данных при выполнении соединений, не являющихся уравнивающими, можно использовать несколько предложений `from`.</span><span class="sxs-lookup"><span data-stu-id="dced7-112">To perform joins that are not equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="dced7-113">Затем к переменной диапазона для каждого источника можно применить выражение предиката в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="dced7-113">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="dced7-114">Выражение также может принимать форму вызова метода.</span><span class="sxs-lookup"><span data-stu-id="dced7-114">The expression also can take the form of a method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dced7-115">Не путайте этот вид пользовательской операции соединения с использованием нескольких предложений `from` для доступа к внутренним коллекциям.</span><span class="sxs-lookup"><span data-stu-id="dced7-115">Do not confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="dced7-116">Дополнительные сведения см. в разделе [Предложение join](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dced7-116">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dced7-117">Пример</span><span class="sxs-lookup"><span data-stu-id="dced7-117">Example</span></span>  
 <span data-ttu-id="dced7-118">Первый метод в приведенном ниже примере показывает простое перекрестное соединение.</span><span class="sxs-lookup"><span data-stu-id="dced7-118">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="dced7-119">Перекрестные соединения следует использовать с осторожностью, так как они могут возвращать очень большие наборы результатов.</span><span class="sxs-lookup"><span data-stu-id="dced7-119">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="dced7-120">Однако такие соединения могут быть полезны при создании исходных последовательностей, относительно которых выполняются дополнительные запросы.</span><span class="sxs-lookup"><span data-stu-id="dced7-120">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>  
  
 <span data-ttu-id="dced7-121">Результатом второго метода является последовательность всех продуктов, идентификатор категории которых находится в списке категорий с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="dced7-121">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="dced7-122">Учтите необходимость использования предложения `let` и метода `Contains` для создания временного массива.</span><span class="sxs-lookup"><span data-stu-id="dced7-122">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="dced7-123">Также можно создать массив перед запросом и удалить первое предложение `from`.</span><span class="sxs-lookup"><span data-stu-id="dced7-123">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="dced7-124">Пример</span><span class="sxs-lookup"><span data-stu-id="dced7-124">Example</span></span>  
 <span data-ttu-id="dced7-125">В приведенном ниже примере запрос должен соединять две последовательности на основе сопоставления ключей, которые в случае с внутренней (правосторонней) последовательностью не могут быть получены до предложения соединения.</span><span class="sxs-lookup"><span data-stu-id="dced7-125">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="dced7-126">Если соединение было выполнено с предложением `join`, для каждого элемента требуется вызвать метод `Split`.</span><span class="sxs-lookup"><span data-stu-id="dced7-126">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="dced7-127">Использование нескольких предложений `from` позволяет запросу избежать издержек, связанных с повторным вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="dced7-127">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="dced7-128">Однако поскольку предложение `join` оптимизировано, в этом случае его использование может быть эффективнее нескольких предложений `from`.</span><span class="sxs-lookup"><span data-stu-id="dced7-128">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="dced7-129">Результаты будут зависеть в основном от затрат на вызов метода.</span><span class="sxs-lookup"><span data-stu-id="dced7-129">The results will vary depending primarily on how expensive the method call is.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dced7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="dced7-130">See also</span></span>  
 [<span data-ttu-id="dced7-131">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="dced7-131">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="dced7-132">предложение join</span><span class="sxs-lookup"><span data-stu-id="dced7-132">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="dced7-133">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="dced7-133">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
