---
title: Выполнение пользовательских операций соединения (LINQ в C#)
description: Узнайте, как выполнять пользовательские операции соединения LINQ в C#.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659856"
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="395ab-103">Выполнение пользовательских операций соединения</span><span class="sxs-lookup"><span data-stu-id="395ab-103">Perform custom join operations</span></span>

<span data-ttu-id="395ab-104">В этом примере показано, как выполнить операции соединения, которые нельзя осуществить с помощью предложения `join`.</span><span class="sxs-lookup"><span data-stu-id="395ab-104">This example shows how to perform join operations that aren't possible with the `join` clause.</span></span> <span data-ttu-id="395ab-105">В выражении запроса предложение `join` ограничено уравнивающими соединениями и оптимизировано для них; они являются самым общим типом операций соединения.</span><span class="sxs-lookup"><span data-stu-id="395ab-105">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="395ab-106">При выполнении уравнивающего соединения использование предложения `join` почти всегда обеспечивает наилучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="395ab-106">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>

<span data-ttu-id="395ab-107">Однако предложение `join` нельзя использовать в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="395ab-107">However, the `join` clause cannot be used in the following cases:</span></span>

- <span data-ttu-id="395ab-108">Соединение объявлено в выражении неравенства (не уравнивающее соединение).</span><span class="sxs-lookup"><span data-stu-id="395ab-108">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>

- <span data-ttu-id="395ab-109">Соединение объявлено в нескольких выражениях равенства или неравенства.</span><span class="sxs-lookup"><span data-stu-id="395ab-109">When the join is predicated on more than one expression of equality or inequality.</span></span>

- <span data-ttu-id="395ab-110">Необходимость создания временной переменной диапазона для правосторонней (внутренней) последовательности перед операцией соединения.</span><span class="sxs-lookup"><span data-stu-id="395ab-110">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>

 <span data-ttu-id="395ab-111">Чтобы независимо представить каждый источник данных при выполнении соединений, не являющихся уравнивающими, можно использовать несколько предложений `from`.</span><span class="sxs-lookup"><span data-stu-id="395ab-111">To perform joins that aren't equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="395ab-112">Затем к переменной диапазона для каждого источника можно применить выражение предиката в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="395ab-112">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="395ab-113">Выражение также может принимать форму вызова метода.</span><span class="sxs-lookup"><span data-stu-id="395ab-113">The expression also can take the form of a method call.</span></span>

> [!NOTE]
> <span data-ttu-id="395ab-114">Не путайте этот вид пользовательской операции соединения с использованием нескольких предложений `from` для доступа к внутренним коллекциям.</span><span class="sxs-lookup"><span data-stu-id="395ab-114">Don't confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="395ab-115">Дополнительные сведения см. в разделе [Предложение join](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="395ab-115">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="395ab-116">Пример</span><span class="sxs-lookup"><span data-stu-id="395ab-116">Example</span></span>

<span data-ttu-id="395ab-117">Первый метод в приведенном ниже примере показывает простое перекрестное соединение.</span><span class="sxs-lookup"><span data-stu-id="395ab-117">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="395ab-118">Перекрестные соединения следует использовать с осторожностью, так как они могут возвращать очень большие наборы результатов.</span><span class="sxs-lookup"><span data-stu-id="395ab-118">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="395ab-119">Однако такие соединения могут быть полезны при создании исходных последовательностей, относительно которых выполняются дополнительные запросы.</span><span class="sxs-lookup"><span data-stu-id="395ab-119">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>

<span data-ttu-id="395ab-120">Результатом второго метода является последовательность всех продуктов, идентификатор категории которых находится в списке категорий с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="395ab-120">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="395ab-121">Учтите необходимость использования предложения `let` и метода `Contains` для создания временного массива.</span><span class="sxs-lookup"><span data-stu-id="395ab-121">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="395ab-122">Также можно создать массив перед запросом и удалить первое предложение `from`.</span><span class="sxs-lookup"><span data-stu-id="395ab-122">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a><span data-ttu-id="395ab-123">Пример</span><span class="sxs-lookup"><span data-stu-id="395ab-123">Example</span></span>

<span data-ttu-id="395ab-124">В приведенном ниже примере запрос должен соединять две последовательности на основе сопоставления ключей, которые в случае с внутренней (правосторонней) последовательностью не могут быть получены до предложения соединения.</span><span class="sxs-lookup"><span data-stu-id="395ab-124">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="395ab-125">Если соединение было выполнено с предложением `join`, для каждого элемента требуется вызвать метод `Split`.</span><span class="sxs-lookup"><span data-stu-id="395ab-125">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="395ab-126">Использование нескольких предложений `from` позволяет запросу избежать издержек, связанных с повторным вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="395ab-126">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="395ab-127">Однако поскольку предложение `join` оптимизировано, в этом случае его использование может быть эффективнее нескольких предложений `from`.</span><span class="sxs-lookup"><span data-stu-id="395ab-127">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="395ab-128">Результаты будут зависеть в основном от затрат на вызов метода.</span><span class="sxs-lookup"><span data-stu-id="395ab-128">The results will vary depending primarily on how expensive the method call is.</span></span>

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a><span data-ttu-id="395ab-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="395ab-129">See also</span></span>

- [<span data-ttu-id="395ab-130">LINQ</span><span class="sxs-lookup"><span data-stu-id="395ab-130">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="395ab-131">предложение join</span><span class="sxs-lookup"><span data-stu-id="395ab-131">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="395ab-132">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="395ab-132">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
