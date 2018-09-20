---
title: Функции как значения первого класса (F#)
description: 'Узнайте, как функции повышаются до состояния первого класса в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 45b65ab2454a592d38c80fd367e7243635614727
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46478587"
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="57127-103">Функции как значения первого класса</span><span class="sxs-lookup"><span data-stu-id="57127-103">Functions as First-Class Values</span></span>

<span data-ttu-id="57127-104">Определяющей характеристикой языков функционального программирования является повышение функций первого класса состояния.</span><span class="sxs-lookup"><span data-stu-id="57127-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="57127-105">Можно сделать с помощью функции, все, что можно сделать со значениями других встроенных типов и иметь возможность сделать это с сопоставимым усилий.</span><span class="sxs-lookup"><span data-stu-id="57127-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="57127-106">Ниже приведены типичные вопросы для первоклассному статусу:</span><span class="sxs-lookup"><span data-stu-id="57127-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="57127-107">Можно ли привязать к идентификаторам функций?</span><span class="sxs-lookup"><span data-stu-id="57127-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="57127-108">То есть можно можно давать их имена?</span><span class="sxs-lookup"><span data-stu-id="57127-108">That is, can you give them names?</span></span>

- <span data-ttu-id="57127-109">Для хранения функций в структурах данных, например, в списке.</span><span class="sxs-lookup"><span data-stu-id="57127-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="57127-110">Можно ли передать функции в качестве аргумента в вызове функции?</span><span class="sxs-lookup"><span data-stu-id="57127-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="57127-111">Может возвращать функция из вызова функции?</span><span class="sxs-lookup"><span data-stu-id="57127-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="57127-112">Последние две меры определяют, что известно как *операции более высокого порядка* или *функции высшего порядка*.</span><span class="sxs-lookup"><span data-stu-id="57127-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="57127-113">Функции высшего порядка принимают функции в качестве аргументов и возвращают функции в качестве значений из вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="57127-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="57127-114">Эти операции поддерживают такие основы функционального программирования, как функции сопоставления и объединение функций.</span><span class="sxs-lookup"><span data-stu-id="57127-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="57127-115">Присвойте значение имени</span><span class="sxs-lookup"><span data-stu-id="57127-115">Give the Value a Name</span></span>

<span data-ttu-id="57127-116">Если функция значения первого класса, необходимо присвоить ей имя так же, как целые числа, строки и другие встроенные типы данных.</span><span class="sxs-lookup"><span data-stu-id="57127-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="57127-117">Это упоминается в литературе о функциональном программировании привязкой идентификатора значение.</span><span class="sxs-lookup"><span data-stu-id="57127-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="57127-118">F # использует [ `let` привязки](../language-reference/functions/let-bindings.md) для привязки имен к значениям: `let <identifier> = <value>`.</span><span class="sxs-lookup"><span data-stu-id="57127-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="57127-119">В следующем коде показано два примера.</span><span class="sxs-lookup"><span data-stu-id="57127-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="57127-120">Функция так же, как легко можно задать имя.</span><span class="sxs-lookup"><span data-stu-id="57127-120">You can name a function just as easily.</span></span> <span data-ttu-id="57127-121">В следующем примере определяется функция с именем `squareIt` , привязав идентификатор `squareIt` для [лямбда-выражение](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="57127-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="57127-122">Функция `squareIt` имеет один параметр `n`, и она возвращает квадрат этого параметра.</span><span class="sxs-lookup"><span data-stu-id="57127-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="57127-123">F # предоставляет следующий сокращенный синтаксис для достижения того же результата с облегчен.</span><span class="sxs-lookup"><span data-stu-id="57127-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="57127-124">Примерах главным образом используется первый стиль, `let <function-name> = <lambda-expression>`, чтобы подчеркнуть сходства объявления функций и объявления других типов значений.</span><span class="sxs-lookup"><span data-stu-id="57127-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="57127-125">Тем не менее все именованные функции также могут записываться с сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="57127-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="57127-126">Некоторые примеры записываются в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="57127-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="57127-127">Значение в структуру данных Store</span><span class="sxs-lookup"><span data-stu-id="57127-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="57127-128">Значения первого класса могут храниться в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="57127-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="57127-129">В следующем коде показано примеры, которые сохраняют значения в списках и в кортежи.</span><span class="sxs-lookup"><span data-stu-id="57127-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="57127-130">Чтобы убедиться, что имя функции, хранимые в кортеже фактически выполняет вычисление функции, в следующем примере используется `fst` и `snd` операторов для извлечения элементов первого и второго из кортежа `funAndArgTuple`.</span><span class="sxs-lookup"><span data-stu-id="57127-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="57127-131">Первый элемент в кортеже — `squareIt` и второй элемент — `num`.</span><span class="sxs-lookup"><span data-stu-id="57127-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="57127-132">Идентификатор `num` привязана в предыдущем примере целое число 10, которое является допустимым аргументом для `squareIt` функции.</span><span class="sxs-lookup"><span data-stu-id="57127-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="57127-133">Второе выражение применяется первый элемент в кортеже, второй элемент в кортеже: `squareIt num`.</span><span class="sxs-lookup"><span data-stu-id="57127-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="57127-134">Точно так же просто, как идентификатор `num` и может принимать целое число 10 взаимозаменяемы, поэтому можно идентификатор `squareIt` и лямбда-выражение `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="57127-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="57127-135">Передайте значение в качестве аргумента</span><span class="sxs-lookup"><span data-stu-id="57127-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="57127-136">Если значение имеет состояние первого класса на языке, можно передать в качестве аргумента в функцию.</span><span class="sxs-lookup"><span data-stu-id="57127-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="57127-137">Например довольно часто для передачи аргументов Integer и String.</span><span class="sxs-lookup"><span data-stu-id="57127-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="57127-138">В следующем коде показано целые числа и строки, передаваемые в качестве аргументов в F #.</span><span class="sxs-lookup"><span data-stu-id="57127-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="57127-139">Если функции первого класса состояния, необходимо передать в качестве аргументов таким же образом.</span><span class="sxs-lookup"><span data-stu-id="57127-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="57127-140">Помните, что это первая характеристика функций более высокого порядка.</span><span class="sxs-lookup"><span data-stu-id="57127-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="57127-141">В следующем примере функция `applyIt` имеет два параметра `op` и `arg`.</span><span class="sxs-lookup"><span data-stu-id="57127-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="57127-142">Если отправить функцию, которая имеет один параметр для `op` и соответствующий аргумент для функции `arg`, функция возвращает результат применения `op` для `arg`.</span><span class="sxs-lookup"><span data-stu-id="57127-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="57127-143">В следующем примере аргумент функции и целочисленный аргумент отправляются таким же образом, с помощью их имен.</span><span class="sxs-lookup"><span data-stu-id="57127-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="57127-144">Возможность передавать функции в качестве аргумента другой функции лежит в основе типичных абстракций в функциональных языках программирования, таких как операции сопоставления или фильтрации.</span><span class="sxs-lookup"><span data-stu-id="57127-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="57127-145">Операция сопоставления, например, является функция высшего порядка, который фиксирует общее вычисление функций, которые проходят по списку, выполнять действия с каждым элементом и возвращается список результатов.</span><span class="sxs-lookup"><span data-stu-id="57127-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="57127-146">Вы можете увеличить значение каждого элемента в список целых чисел, или квадрат каждого элемента или для изменения каждого элемента в список строк в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="57127-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="57127-147">Ошибкам часть вычисления является рекурсивным процессом, который проходит по списку и строит список результатов для возвращения.</span><span class="sxs-lookup"><span data-stu-id="57127-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="57127-148">Эта часть захватывается в функции сопоставления.</span><span class="sxs-lookup"><span data-stu-id="57127-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="57127-149">Вам нужно написать для конкретного приложения — функция, которая будет применяться к каждому элементу списка по отдельности (Добавление, возведение в квадрат, изменение регистра).</span><span class="sxs-lookup"><span data-stu-id="57127-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="57127-150">Эта функция отправляется в качестве аргумента в функцию сопоставления, так же, как `squareIt` отправляется `applyIt` в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="57127-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="57127-151">F # предоставляет методы сопоставления для большинства типов коллекций, включая [перечислены](../language-reference/lists.md), [массивы](../language-reference/arrays.md), и [последовательностей](../language-reference/sequences.md).</span><span class="sxs-lookup"><span data-stu-id="57127-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="57127-152">В следующих примерах используются списки.</span><span class="sxs-lookup"><span data-stu-id="57127-152">The following examples use lists.</span></span> <span data-ttu-id="57127-153">Синтаксис `List.map <the function> <the list>`.</span><span class="sxs-lookup"><span data-stu-id="57127-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="57127-154">Дополнительные сведения см. в разделе [перечислены](../language-reference/lists.md).</span><span class="sxs-lookup"><span data-stu-id="57127-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="57127-155">Возврат значения из вызова функции</span><span class="sxs-lookup"><span data-stu-id="57127-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="57127-156">И, наконец Если функция имеет состояние первого класса на языке, необходимо вернуть в качестве значения вызова функции, так же, как возвращать другие типы, такие как Integer и String.</span><span class="sxs-lookup"><span data-stu-id="57127-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="57127-157">Следующие вызовы функции возвращают целые числа и отобразить их.</span><span class="sxs-lookup"><span data-stu-id="57127-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="57127-158">При вызове следующей функции возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="57127-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="57127-159">При вызове следующей функции, объявленные встроенными, возвращает значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="57127-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="57127-160">Отображаемое значение `True`.</span><span class="sxs-lookup"><span data-stu-id="57127-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="57127-161">Для возврата функции в качестве значения вызова функции является второй характеристикой функций более высокого порядка.</span><span class="sxs-lookup"><span data-stu-id="57127-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="57127-162">В следующем примере `checkFor` определяется как функцию, которая принимает один аргумент `item`и возвращает новую функцию в качестве его значения.</span><span class="sxs-lookup"><span data-stu-id="57127-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="57127-163">Возвращаемая функция принимает список в качестве аргумента, `lst`и поиск `item` в `lst`.</span><span class="sxs-lookup"><span data-stu-id="57127-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="57127-164">Если `item` присутствует, функция возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="57127-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="57127-165">Если `item` не существует, функция возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="57127-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="57127-166">Как и в предыдущем разделе, в следующем коде используется функция списка, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), для поиска в списке.</span><span class="sxs-lookup"><span data-stu-id="57127-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="57127-167">В следующем коде используется `checkFor` создать новую функцию, которая принимает один аргумент, список и выполняет поиск 7 в списке.</span><span class="sxs-lookup"><span data-stu-id="57127-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="57127-168">В следующем примере состояние первого класса функций в F # для объявления функции, `compose`, которая возвращает композицию двух аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="57127-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]

>[!NOTE]
<span data-ttu-id="57127-169">Для более краткую версию см. в разделе «Curried функции».</span><span class="sxs-lookup"><span data-stu-id="57127-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="57127-170">Следующий код отправляет две функции в качестве аргументов `compose`, оба из которых принимает один аргумент того же типа.</span><span class="sxs-lookup"><span data-stu-id="57127-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="57127-171">Возвращаемое значение имеет новую функцию, которая представляет собой сочетание двух аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="57127-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]

>[!NOTE]
<span data-ttu-id="57127-172">F # предоставляет два оператора `<<` и `>>`, который объединяет функции.</span><span class="sxs-lookup"><span data-stu-id="57127-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="57127-173">Например `let squareAndDouble2 = doubleIt << squareIt` эквивалентен `let squareAndDouble = compose doubleIt squareIt` в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="57127-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="57127-174">В следующем примере возврата функции в качестве значения вызова функции создается простая игра по угадыванию.</span><span class="sxs-lookup"><span data-stu-id="57127-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="57127-175">Чтобы создать игру, вызовите `makeGame` со значением возникает необходимость угадать, отправленным для `target`.</span><span class="sxs-lookup"><span data-stu-id="57127-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="57127-176">Возвращаемое значение из функции `makeGame` является функцией, которая принимает один аргумент (предположение) и сообщает, является ли пробное значение правильно.</span><span class="sxs-lookup"><span data-stu-id="57127-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="57127-177">Следующий код вызывает `makeGame`, отправить значение `7` для `target`.</span><span class="sxs-lookup"><span data-stu-id="57127-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="57127-178">Идентификатор `playGame` привязан к возвращаемому лямбда-выражению.</span><span class="sxs-lookup"><span data-stu-id="57127-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="57127-179">Таким образом `playGame` — это функция, которая принимает в качестве единственного аргумента значение для `guess`.</span><span class="sxs-lookup"><span data-stu-id="57127-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="57127-180">Каррированные функции</span><span class="sxs-lookup"><span data-stu-id="57127-180">Curried Functions</span></span>

<span data-ttu-id="57127-181">Во многих примерах в предыдущем разделе можно написать более кратко, используя преимущества неявного *каррирование* в объявлениях функций F #.</span><span class="sxs-lookup"><span data-stu-id="57127-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="57127-182">Каррирование — это процесс преобразования функции, которая имеет более одного параметра на ряд встроенных функций, каждая из которых имеет один параметр.</span><span class="sxs-lookup"><span data-stu-id="57127-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="57127-183">В F # по своей природе каррированные функции, которые имеют более одного параметра.</span><span class="sxs-lookup"><span data-stu-id="57127-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="57127-184">Например `compose` из предыдущего раздела может быть написано как показано в следующем кратком стиле, с тремя параметрами.</span><span class="sxs-lookup"><span data-stu-id="57127-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="57127-185">Тем не менее, результат зависит от один параметр, который возвращает функцию один параметр, который в свою очередь, возвращает другую функцию одного параметра, как показано в `compose4curried`.</span><span class="sxs-lookup"><span data-stu-id="57127-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="57127-186">Можно получить доступ к этой функции несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="57127-186">You can access this function in several ways.</span></span> <span data-ttu-id="57127-187">Каждый из следующих примеров возвращает и отображает 18.</span><span class="sxs-lookup"><span data-stu-id="57127-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="57127-188">Вы можете заменить `compose4` с `compose4curried` во всех примерах.</span><span class="sxs-lookup"><span data-stu-id="57127-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="57127-189">Чтобы убедиться, что функция будет по-прежнему работать как и раньше, повторите попытку исходных тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="57127-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]

>[!NOTE]
<span data-ttu-id="57127-190">Можно ограничить каррирование, поместив параметры в кортежи.</span><span class="sxs-lookup"><span data-stu-id="57127-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="57127-191">Дополнительные сведения см. в разделе «Шаблоны параметров» в [параметры и аргументы](../language-reference/parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="57127-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="57127-192">В следующем примере неявное каррирование записываемый краткая версия `makeGame`.</span><span class="sxs-lookup"><span data-stu-id="57127-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="57127-193">Сведения о том, как `makeGame` создает и возвращает `game` функции являются менее явными в этот формат, но можно проверить с помощью исходных тестовых случаев, что результат будет такой же.</span><span class="sxs-lookup"><span data-stu-id="57127-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="57127-194">Дополнительные сведения о каррирование, см. в разделе «Частичное приложения из аргументы» в [функции](../language-reference/functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="57127-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="57127-195">Идентификатор и определение функции являются взаимозаменяемыми</span><span class="sxs-lookup"><span data-stu-id="57127-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="57127-196">Имя переменной `num` в предыдущем примеры имеет значение целого числа 10, и не удивительно, что где `num` является допустимым, 10 также является допустимым.</span><span class="sxs-lookup"><span data-stu-id="57127-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="57127-197">То же самое относится и к идентификаторам функций и их значения: везде, где можно использовать имя функции, можно использовать лямбда-выражение, к которому он привязан.</span><span class="sxs-lookup"><span data-stu-id="57127-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="57127-198">В следующем примере определяется `Boolean` функция, вызываемая `isNegative`, а затем использует имя функции и определение функции являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="57127-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="57127-199">Следующие три примера возвращают и отображают `False`.</span><span class="sxs-lookup"><span data-stu-id="57127-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="57127-200">Чтобы продвинуться на один шаг дальнейшей, заменить значение, `applyIt` привязан к для `applyIt`.</span><span class="sxs-lookup"><span data-stu-id="57127-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="57127-201">Функции являются значениями первого класса на языке f #\#</span><span class="sxs-lookup"><span data-stu-id="57127-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="57127-202">В примерах в предыдущих разделах показано, что в F # функции удовлетворяют критериям значений первого класса F #:</span><span class="sxs-lookup"><span data-stu-id="57127-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="57127-203">Идентификатор можно привязать к определению функции.</span><span class="sxs-lookup"><span data-stu-id="57127-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="57127-204">Функцию можно хранить в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="57127-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="57127-205">Функцию можно передать в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="57127-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="57127-206">Функция может возвращать как значение вызова функции.</span><span class="sxs-lookup"><span data-stu-id="57127-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="57127-207">Дополнительные сведения о F #, см. в разделе [Справочник по языку F #](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="57127-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="57127-208">Пример</span><span class="sxs-lookup"><span data-stu-id="57127-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="57127-209">Описание</span><span class="sxs-lookup"><span data-stu-id="57127-209">Description</span></span>

<span data-ttu-id="57127-210">Следующий код содержит все примеры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="57127-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="57127-211">Код</span><span class="sxs-lookup"><span data-stu-id="57127-211">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="57127-212">См. также</span><span class="sxs-lookup"><span data-stu-id="57127-212">See also</span></span>

- [<span data-ttu-id="57127-213">Списки</span><span class="sxs-lookup"><span data-stu-id="57127-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="57127-214">Кортежи</span><span class="sxs-lookup"><span data-stu-id="57127-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="57127-215">Функции</span><span class="sxs-lookup"><span data-stu-id="57127-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="57127-216">`let` Привязки</span><span class="sxs-lookup"><span data-stu-id="57127-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="57127-217">Лямбда-выражения: `fun` ключевое слово</span><span class="sxs-lookup"><span data-stu-id="57127-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
