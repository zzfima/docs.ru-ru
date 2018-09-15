---
title: 'Циклы: выражение for...in (F#)'
description: 'См. в разделе как F # for... в выражении циклов конструкция используется для итерации по совпадениям с шаблоном в перечислимой коллекции.'
ms.date: 05/16/2016
ms.openlocfilehash: c4fba1f1dea3993cafa2e37ad0f32d9fb2eed85a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615772"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="414d3-103">Циклы: выражение for...in</span><span class="sxs-lookup"><span data-stu-id="414d3-103">Loops: for...in Expression</span></span>

<span data-ttu-id="414d3-104">Этот циклическую конструкцию, используется для итерации по совпадениям с шаблоном в перечислимой коллекции, такие как выражение диапазона, последовательность, список, массив или другая конструкция, поддерживающая перечисление.</span><span class="sxs-lookup"><span data-stu-id="414d3-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="414d3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="414d3-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="414d3-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="414d3-106">Remarks</span></span>

<span data-ttu-id="414d3-107">`for...in` Выражение может сравниваться с `for each` инструкции на других языках .NET, так как он используется для перебора элементов в перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="414d3-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="414d3-108">Тем не менее `for...in` также поддерживает образцы для сопоставления в коллекции, а не только простой перебор всех элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="414d3-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="414d3-109">Перечислимое выражение должно лежать в виде перечисляемой коллекции, или с помощью `..` оператор, как диапазон на целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="414d3-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="414d3-110">Перечислимые коллекции включают списков, последовательностей, массивы, наборы, карт и т. д.</span><span class="sxs-lookup"><span data-stu-id="414d3-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="414d3-111">Любой тип, реализующий `System.Collections.IEnumerable` может использоваться.</span><span class="sxs-lookup"><span data-stu-id="414d3-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="414d3-112">Если представить диапазон с помощью `..` оператора, можно использовать следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="414d3-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="414d3-113">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="414d3-113">*start* ..</span></span> <span data-ttu-id="414d3-114">*Готово*</span><span class="sxs-lookup"><span data-stu-id="414d3-114">*finish*</span></span>

<span data-ttu-id="414d3-115">Можно также использовать версию, которая инкремент имеет *пропустить*, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="414d3-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="414d3-116">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="414d3-116">*start* ..</span></span> <span data-ttu-id="414d3-117">*Пропустить* ...</span><span class="sxs-lookup"><span data-stu-id="414d3-117">*skip* ..</span></span> <span data-ttu-id="414d3-118">*Готово*</span><span class="sxs-lookup"><span data-stu-id="414d3-118">*finish*</span></span>

<span data-ttu-id="414d3-119">При использовании диапазоны целочисленные и простой счетчик переменную как шаблон, типичное поведение для увеличения значения переменной счетчика на 1 при каждой итерации, но если диапазон содержит значение пропуска, этот счетчик увеличивается на это значение, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="414d3-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="414d3-120">Значения, соответствующие шаблону, также могут использоваться в теле цикла.</span><span class="sxs-lookup"><span data-stu-id="414d3-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="414d3-121">В следующих примерах кода показано использование `for...in` выражение.</span><span class="sxs-lookup"><span data-stu-id="414d3-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="414d3-122">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="414d3-123">Следующий пример показывает, как выполнить цикл по последовательности, а также как использовать шаблон кортежа вместо простой переменной.</span><span class="sxs-lookup"><span data-stu-id="414d3-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="414d3-124">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="414d3-125">В следующем примере показано, как цикла простым целым числом.</span><span class="sxs-lookup"><span data-stu-id="414d3-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="414d3-126">Выходные данные функции function1 выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="414d3-127">Приведенный ниже показано, как для циклического прохода диапазон с пропуска 2, включающий любым другим элементом диапазона.</span><span class="sxs-lookup"><span data-stu-id="414d3-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="414d3-128">Выходные данные `function2` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="414d3-129">В следующем примере показано, как использовать диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="414d3-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="414d3-130">Выходные данные `function3` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="414d3-131">Следующий пример показывает использование отрицательного значения пропуска для обратной итерации.</span><span class="sxs-lookup"><span data-stu-id="414d3-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="414d3-132">Выходные данные `function4` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="414d3-133">Начало и конец диапазона также может быть выражения, например функции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="414d3-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="414d3-134">Выходные данные `function5` с данным входом выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="414d3-135">В следующем примере показано использование подстановочного знака (\_) когда элемент не требуется в цикле.</span><span class="sxs-lookup"><span data-stu-id="414d3-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="414d3-136">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="414d3-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="414d3-137">`Note` Можно использовать `for...in` в выражениях последовательности и другие вычисления выражения, в этом случае настроенную версию `for...in` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="414d3-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="414d3-138">Дополнительные сведения см. в разделе [последовательностей](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения вычисления](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="414d3-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="414d3-139">См. также</span><span class="sxs-lookup"><span data-stu-id="414d3-139">See also</span></span>

- [<span data-ttu-id="414d3-140">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="414d3-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="414d3-141">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="414d3-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="414d3-142">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="414d3-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
