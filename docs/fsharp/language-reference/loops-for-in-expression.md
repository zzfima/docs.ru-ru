---
title: "Циклы: выражение for...in (F#)"
description: "В разделе как for. F #.. в выражении циклов конструкция используется для прохода по совпадений шаблона в перечислимой коллекции."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f54e3228-4aec-4d0a-ae37-bc3376508284
ms.openlocfilehash: d86aeb3bdd975261e59004d636354a740bd95c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forin-expression"></a><span data-ttu-id="0286e-104">Циклы: выражение for...in</span><span class="sxs-lookup"><span data-stu-id="0286e-104">Loops: for...in Expression</span></span>

<span data-ttu-id="0286e-105">Эта конструкция цикла используется для прохода по совпадений шаблона в перечислимой коллекции, например, выражение диапазона, последовательности, список, массив или другие конструкции, поддерживающей перечисление.</span><span class="sxs-lookup"><span data-stu-id="0286e-105">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="0286e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0286e-106">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="0286e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0286e-107">Remarks</span></span>
<span data-ttu-id="0286e-108">`for...in` Выражение можно сравнить с `for each` инструкции в других языках .NET, так как он используется для перебора элементов в перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="0286e-108">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="0286e-109">Однако `for...in` также поддерживает шаблоны коллекции, а не только простой перебор всех элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="0286e-109">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="0286e-110">Перечислимое выражение можно указать виде перечисляемой коллекции или с помощью `..` оператор в виде диапазона на целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="0286e-110">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="0286e-111">Перечислимые коллекции включают списки, последовательности, массивы, наборы, карт и т. д.</span><span class="sxs-lookup"><span data-stu-id="0286e-111">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="0286e-112">Любой тип, реализующий `System.Collections.IEnumerable` может использоваться.</span><span class="sxs-lookup"><span data-stu-id="0286e-112">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="0286e-113">Если диапазон выразить с помощью `..` оператор, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0286e-113">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="0286e-114">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="0286e-114">*start* ..</span></span> <span data-ttu-id="0286e-115">*Готово*</span><span class="sxs-lookup"><span data-stu-id="0286e-115">*finish*</span></span>

<span data-ttu-id="0286e-116">Можно также использовать версию, которая инкремент имеет *пропустить*, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0286e-116">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="0286e-117">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="0286e-117">*start* ..</span></span> <span data-ttu-id="0286e-118">*Пропустить* ...</span><span class="sxs-lookup"><span data-stu-id="0286e-118">*skip* ..</span></span> <span data-ttu-id="0286e-119">*Готово*</span><span class="sxs-lookup"><span data-stu-id="0286e-119">*finish*</span></span>

<span data-ttu-id="0286e-120">При использовании диапазоны целочисленных и переменную счетчика простой как шаблон, принятое по умолчанию поведение является увеличивается на 1 при каждой итерации переменной счетчика, но если диапазон содержит значение пропуска, этот счетчик увеличивается на это значение, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0286e-120">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="0286e-121">Значения, соответствующие шаблону также могут использоваться в теле цикла.</span><span class="sxs-lookup"><span data-stu-id="0286e-121">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="0286e-122">В следующих примерах кода показано использование `for...in` выражение.</span><span class="sxs-lookup"><span data-stu-id="0286e-122">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="0286e-123">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-123">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="0286e-124">Следующий пример показывает применение цикла последовательности и использование шаблона в виде кортежа вместо простой переменной.</span><span class="sxs-lookup"><span data-stu-id="0286e-124">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="0286e-125">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-125">The output is as follows.</span></span>

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

<span data-ttu-id="0286e-126">Приведенный ниже показано, как для циклического прохода по простой целых чисел.</span><span class="sxs-lookup"><span data-stu-id="0286e-126">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="0286e-127">Выходные данные функция1 выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-127">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="0286e-128">В следующем примере показано, как цикла со значением пропуска 2, включающий каждый элемент диапазона.</span><span class="sxs-lookup"><span data-stu-id="0286e-128">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="0286e-129">Выходные данные `function2` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-129">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="0286e-130">В следующем примере показано использование диапазона знаков.</span><span class="sxs-lookup"><span data-stu-id="0286e-130">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="0286e-131">Выходные данные `function3` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-131">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="0286e-132">Следующий пример показывает использование отрицательного значения пропуска для перебора в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="0286e-132">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="0286e-133">Выходные данные `function4` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-133">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="0286e-134">Начало и конец диапазона также может быть выражения, например функции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0286e-134">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="0286e-135">Выходные данные `function5` со входными выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-135">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="0286e-136">В следующем примере показано использование подстановочного знака (_), если элемент не требуется в цикле.</span><span class="sxs-lookup"><span data-stu-id="0286e-136">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="0286e-137">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0286e-137">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="0286e-138">`Note`Можно использовать `for...in` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `for...in` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="0286e-138">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="0286e-139">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0286e-139">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="0286e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0286e-140">See Also</span></span>
[<span data-ttu-id="0286e-141">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="0286e-141">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="0286e-142">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="0286e-142">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="0286e-143">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="0286e-143">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
