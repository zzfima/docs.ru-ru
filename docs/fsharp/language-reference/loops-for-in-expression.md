---
title: 'Циклы: выражение for...in (F#)'
description: 'В разделе как for. F #.. в выражении циклов конструкция используется для прохода по совпадений шаблона в перечислимой коллекции.'
ms.date: 05/16/2016
ms.openlocfilehash: 926f0a9940021b3dc0deefc12ea158c35975e949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564078"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="9b082-103">Циклы: выражение for...in</span><span class="sxs-lookup"><span data-stu-id="9b082-103">Loops: for...in Expression</span></span>

<span data-ttu-id="9b082-104">Эта конструкция цикла используется для прохода по совпадений шаблона в перечислимой коллекции, например, выражение диапазона, последовательности, список, массив или другие конструкции, поддерживающей перечисление.</span><span class="sxs-lookup"><span data-stu-id="9b082-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="9b082-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b082-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="9b082-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b082-106">Remarks</span></span>
<span data-ttu-id="9b082-107">`for...in` Выражение можно сравнить с `for each` инструкции в других языках .NET, так как он используется для перебора элементов в перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="9b082-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="9b082-108">Однако `for...in` также поддерживает шаблоны коллекции, а не только простой перебор всех элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="9b082-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="9b082-109">Перечислимое выражение можно указать виде перечисляемой коллекции или с помощью `..` оператор в виде диапазона на целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="9b082-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="9b082-110">Перечислимые коллекции включают списки, последовательности, массивы, наборы, карт и т. д.</span><span class="sxs-lookup"><span data-stu-id="9b082-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="9b082-111">Любой тип, реализующий `System.Collections.IEnumerable` может использоваться.</span><span class="sxs-lookup"><span data-stu-id="9b082-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="9b082-112">Если диапазон выразить с помощью `..` оператор, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9b082-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="9b082-113">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="9b082-113">*start* ..</span></span> <span data-ttu-id="9b082-114">*Готово*</span><span class="sxs-lookup"><span data-stu-id="9b082-114">*finish*</span></span>

<span data-ttu-id="9b082-115">Можно также использовать версию, которая инкремент имеет *пропустить*, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9b082-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="9b082-116">*Запуск* ...</span><span class="sxs-lookup"><span data-stu-id="9b082-116">*start* ..</span></span> <span data-ttu-id="9b082-117">*Пропустить* ...</span><span class="sxs-lookup"><span data-stu-id="9b082-117">*skip* ..</span></span> <span data-ttu-id="9b082-118">*Готово*</span><span class="sxs-lookup"><span data-stu-id="9b082-118">*finish*</span></span>

<span data-ttu-id="9b082-119">При использовании диапазоны целочисленных и переменную счетчика простой как шаблон, принятое по умолчанию поведение является увеличивается на 1 при каждой итерации переменной счетчика, но если диапазон содержит значение пропуска, этот счетчик увеличивается на это значение, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9b082-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="9b082-120">Значения, соответствующие шаблону также могут использоваться в теле цикла.</span><span class="sxs-lookup"><span data-stu-id="9b082-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="9b082-121">В следующих примерах кода показано использование `for...in` выражение.</span><span class="sxs-lookup"><span data-stu-id="9b082-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="9b082-122">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="9b082-123">Следующий пример показывает применение цикла последовательности и использование шаблона в виде кортежа вместо простой переменной.</span><span class="sxs-lookup"><span data-stu-id="9b082-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="9b082-124">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-124">The output is as follows.</span></span>

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

<span data-ttu-id="9b082-125">Приведенный ниже показано, как для циклического прохода по простой целых чисел.</span><span class="sxs-lookup"><span data-stu-id="9b082-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="9b082-126">Выходные данные функция1 выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="9b082-127">В следующем примере показано, как цикла со значением пропуска 2, включающий каждый элемент диапазона.</span><span class="sxs-lookup"><span data-stu-id="9b082-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="9b082-128">Выходные данные `function2` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="9b082-129">В следующем примере показано использование диапазона знаков.</span><span class="sxs-lookup"><span data-stu-id="9b082-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="9b082-130">Выходные данные `function3` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="9b082-131">Следующий пример показывает использование отрицательного значения пропуска для перебора в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="9b082-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="9b082-132">Выходные данные `function4` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="9b082-133">Начало и конец диапазона также может быть выражения, например функции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9b082-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="9b082-134">Выходные данные `function5` со входными выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="9b082-135">В следующем примере показано использование подстановочного знака (_), если элемент не требуется в цикле.</span><span class="sxs-lookup"><span data-stu-id="9b082-135">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="9b082-136">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b082-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="9b082-137">`Note` Можно использовать `for...in` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `for...in` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="9b082-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="9b082-138">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9b082-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="9b082-139">См. также</span><span class="sxs-lookup"><span data-stu-id="9b082-139">See Also</span></span>
[<span data-ttu-id="9b082-140">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="9b082-140">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="9b082-141">Циклы: выражение `for...to`</span><span class="sxs-lookup"><span data-stu-id="9b082-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="9b082-142">Циклы: выражение `while...do`</span><span class="sxs-lookup"><span data-stu-id="9b082-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
