---
title: Функции первого класса
description: Узнайте о функциях первого класса и о том, как они важны для функционального программирования в F#.
ms.date: 10/29/2018
ms.openlocfilehash: 4681d32abd59cc4aade6f4cb2d062e7888bcfbbc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629716"
---
# <a name="first-class-functions"></a><span data-ttu-id="3feab-103">Функции первого класса</span><span class="sxs-lookup"><span data-stu-id="3feab-103">First-class functions</span></span>

<span data-ttu-id="3feab-104">Определение характеристик языков функционального программирования — это повышение уровня функций до состояния первого класса.</span><span class="sxs-lookup"><span data-stu-id="3feab-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="3feab-105">Вы должны иметь возможность выполнять функции, которые можно использовать со значениями других встроенных типов, и иметь возможность сделать это с сравнимой степенью усилий.</span><span class="sxs-lookup"><span data-stu-id="3feab-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="3feab-106">К типичным мерам состояния первого класса относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="3feab-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="3feab-107">Можно ли привязать функции к идентификаторам?</span><span class="sxs-lookup"><span data-stu-id="3feab-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="3feab-108">То есть можно ли присвоить им имена?</span><span class="sxs-lookup"><span data-stu-id="3feab-108">That is, can you give them names?</span></span>

- <span data-ttu-id="3feab-109">Можно ли хранить функции в структурах данных, например в списке?</span><span class="sxs-lookup"><span data-stu-id="3feab-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="3feab-110">Можно ли передать функцию в качестве аргумента в вызове функции?</span><span class="sxs-lookup"><span data-stu-id="3feab-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="3feab-111">Можно ли вернуть функцию из вызова функции?</span><span class="sxs-lookup"><span data-stu-id="3feab-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="3feab-112">Последние две меры определяют, что называются *операциями высшего порядка* или *функциями высшего порядка*.</span><span class="sxs-lookup"><span data-stu-id="3feab-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="3feab-113">Функции высшего порядка принимают функции в качестве аргументов и возвращают функции в качестве значений вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="3feab-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="3feab-114">Эти операции поддерживают такие основ функционального программирования, как функции сопоставления и компоновка функций.</span><span class="sxs-lookup"><span data-stu-id="3feab-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="3feab-115">Присвоить значение имени</span><span class="sxs-lookup"><span data-stu-id="3feab-115">Give the Value a Name</span></span>

<span data-ttu-id="3feab-116">Если функция является значением первого класса, необходимо иметь возможность присвоить ей имя, точно так же, как целые числа, строки и другие встроенные типы.</span><span class="sxs-lookup"><span data-stu-id="3feab-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="3feab-117">В литературе по функциональному программированию это называется привязкой идентификатора к значению.</span><span class="sxs-lookup"><span data-stu-id="3feab-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="3feab-118">F#`let <identifier> = <value>` [ использует`let` привязки](../language-reference/functions/let-bindings.md) для привязки имен к значениям:.</span><span class="sxs-lookup"><span data-stu-id="3feab-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="3feab-119">В следующем коде показаны два примера.</span><span class="sxs-lookup"><span data-stu-id="3feab-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="3feab-120">Вы можете легко присвоить имя функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-120">You can name a function just as easily.</span></span> <span data-ttu-id="3feab-121">В следующем примере определяется функция с именем `squareIt` путем привязки идентификатора `squareIt` к [лямбда-выражению](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="3feab-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="3feab-122">Функция `squareIt` имеет один параметр, `n`и возвращает квадрат этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3feab-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="3feab-123">F#предоставляет следующий более краткий синтаксис для достижения того же результата с меньшей типизацией.</span><span class="sxs-lookup"><span data-stu-id="3feab-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="3feab-124">В приведенных ниже примерах используется первый стиль, `let <function-name> = <lambda-expression>`чтобы подчеркнуть сходство между объявлением функций и объявлением других типов значений.</span><span class="sxs-lookup"><span data-stu-id="3feab-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="3feab-125">Однако все именованные функции также можно записать с помощью краткого синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="3feab-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="3feab-126">Некоторые примеры написаны обоими способами.</span><span class="sxs-lookup"><span data-stu-id="3feab-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="3feab-127">Сохранение значения в структуре данных</span><span class="sxs-lookup"><span data-stu-id="3feab-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="3feab-128">Значение первого класса может храниться в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="3feab-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="3feab-129">В следующем коде показаны примеры хранения значений в списках и кортежах.</span><span class="sxs-lookup"><span data-stu-id="3feab-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="3feab-130">Чтобы убедиться, что имя функции, сохраненное в кортеже, фактически выполняет вычисление функции, в следующем примере используются `fst` операторы `snd` и для извлечения первого и второго элементов из кортежа `funAndArgTuple`.</span><span class="sxs-lookup"><span data-stu-id="3feab-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="3feab-131">Первый элемент в кортеже имеет `squareIt` значение, а второй элемент —. `num`</span><span class="sxs-lookup"><span data-stu-id="3feab-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="3feab-132">Идентификатор `num` привязывается в предыдущем примере к целому 10, допустимому аргументу `squareIt` для функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="3feab-133">Второе выражение применяет первый элемент кортежа ко второму элементу в кортеже: `squareIt num`.</span><span class="sxs-lookup"><span data-stu-id="3feab-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="3feab-134">Точно так же, как `num` идентификатор и целое число 10, можно использовать взаимозаменяемость, `squareIt` поэтому может быть `fun n -> n * n`идентификатором и лямбда-выражением.</span><span class="sxs-lookup"><span data-stu-id="3feab-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="3feab-135">Передать значение в качестве аргумента</span><span class="sxs-lookup"><span data-stu-id="3feab-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="3feab-136">Если значение имеет состояние первого класса в языке, можно передать его в качестве аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="3feab-137">Например, в качестве аргументов часто передаются целые числа и строки.</span><span class="sxs-lookup"><span data-stu-id="3feab-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="3feab-138">В следующем коде показаны целые числа и строки, передаваемые в F#качестве аргументов в.</span><span class="sxs-lookup"><span data-stu-id="3feab-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="3feab-139">Если функции имеют состояние первого класса, необходимо иметь возможность передавать их как аргументы аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="3feab-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="3feab-140">Помните, что это первая характеристика функций высшего порядка.</span><span class="sxs-lookup"><span data-stu-id="3feab-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="3feab-141">В следующем примере функция `applyIt` имеет два параметра: `op` и `arg`.</span><span class="sxs-lookup"><span data-stu-id="3feab-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="3feab-142">Если вы отправляете в функцию, имеющую один параметр `op` для `arg`, и соответствующий аргумент функции, функция возвращает результат применения `op` функции к `arg`.</span><span class="sxs-lookup"><span data-stu-id="3feab-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="3feab-143">В следующем примере аргументы функции и целочисленный аргумент отправляются одинаковым образом с использованием их имен.</span><span class="sxs-lookup"><span data-stu-id="3feab-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="3feab-144">Возможность отправки функции в качестве аргумента в другую функцию зависит от общих абстракций в языках функционального программирования, таких как операции Map или Filter.</span><span class="sxs-lookup"><span data-stu-id="3feab-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="3feab-145">Операция Map, например, — это функция более высокого порядка, которая захватывает вычисления, совместно используемые функциями, которые пошагово проходят по списку, выполняют какие-либо действия с каждым элементом, а затем возвращают список результатов.</span><span class="sxs-lookup"><span data-stu-id="3feab-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="3feab-146">Может потребоваться увеличить каждый элемент в списке целых чисел или квадратный каждый элемент или изменить каждый элемент в списке строк на верхний.</span><span class="sxs-lookup"><span data-stu-id="3feab-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="3feab-147">Подверженная ошибкам часть вычислений является рекурсивным процессом, который проходит по списку и создает список возвращаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="3feab-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="3feab-148">Эта часть захватывается функцией сопоставления.</span><span class="sxs-lookup"><span data-stu-id="3feab-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="3feab-149">Все, что необходимо написать для конкретного приложения, — это функция, которую необходимо применить к каждому элементу списка по отдельности (Добавление, возведение в изменяемый регистр).</span><span class="sxs-lookup"><span data-stu-id="3feab-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="3feab-150">Эта функция отправляется в качестве аргумента функции сопоставления, так же как `squareIt` `applyIt` и в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3feab-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="3feab-151">F#предоставляет методы Map для большинства типов коллекций, включая [списки](../language-reference/lists.md), [массивы](../language-reference/arrays.md)и [последовательности](../language-reference/sequences.md).</span><span class="sxs-lookup"><span data-stu-id="3feab-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="3feab-152">В следующих примерах используются списки.</span><span class="sxs-lookup"><span data-stu-id="3feab-152">The following examples use lists.</span></span> <span data-ttu-id="3feab-153">Синтаксис: `List.map <the function> <the list>`.</span><span class="sxs-lookup"><span data-stu-id="3feab-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="3feab-154">Дополнительные сведения см. в разделе [списки](../language-reference/lists.md).</span><span class="sxs-lookup"><span data-stu-id="3feab-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="3feab-155">Возврат значения из вызова функции</span><span class="sxs-lookup"><span data-stu-id="3feab-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="3feab-156">Наконец, если функция имеет состояние первого класса в языке, необходимо иметь возможность возвращать его как значение вызова функции, как и другие типы, такие как целые числа и строки.</span><span class="sxs-lookup"><span data-stu-id="3feab-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="3feab-157">Следующие вызовы функции возвращают целые числа и отображают их.</span><span class="sxs-lookup"><span data-stu-id="3feab-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="3feab-158">Следующий вызов функции возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="3feab-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="3feab-159">Следующий вызов функции, объявленный встроенным, возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="3feab-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="3feab-160">Отображаемое значение — `True`.</span><span class="sxs-lookup"><span data-stu-id="3feab-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="3feab-161">Возможность возвращать функцию в качестве значения вызова функции — это вторая характеристика функций более высокого порядка.</span><span class="sxs-lookup"><span data-stu-id="3feab-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="3feab-162">В следующем примере `checkFor` определяется как функция, принимающая один аргумент, `item`и возвращающая в качестве значения новую функцию.</span><span class="sxs-lookup"><span data-stu-id="3feab-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="3feab-163">Возвращаемая функция принимает список `lst` `item` в качестве аргумента, и выполняет поиск в `lst`.</span><span class="sxs-lookup"><span data-stu-id="3feab-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="3feab-164">Если `item` имеется, функция возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="3feab-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="3feab-165">Если `item` параметр не указан, функция возвращает `false`значение.</span><span class="sxs-lookup"><span data-stu-id="3feab-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="3feab-166">Как и в предыдущем разделе, следующий код использует предоставленную функцию списка [List. Exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)для поиска в списке.</span><span class="sxs-lookup"><span data-stu-id="3feab-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="3feab-167">Следующий код использует `checkFor` для создания новой функции, которая принимает один аргумент, список и выполняет поиск 7 в списке.</span><span class="sxs-lookup"><span data-stu-id="3feab-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="3feab-168">В следующем примере используется состояние первого класса функций в F# для объявления функции `compose`, которая возвращает композицию двух аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> <span data-ttu-id="3feab-169">Более короткая версия см. в следующем разделе "каррированных функции".</span><span class="sxs-lookup"><span data-stu-id="3feab-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="3feab-170">Следующий код отправляет две функции в качестве аргументов в `compose`, оба из которых принимают один аргумент того же типа.</span><span class="sxs-lookup"><span data-stu-id="3feab-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="3feab-171">Возвращаемое значение — это новая функция, которая представляет собой композицию двух аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> <span data-ttu-id="3feab-172">F#предоставляет два оператора, `<<` и `>>`, которые состоят из функций.</span><span class="sxs-lookup"><span data-stu-id="3feab-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="3feab-173">Например, `let squareAndDouble2 = doubleIt << squareIt` `let squareAndDouble = compose doubleIt squareIt` эквивалентен в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3feab-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="3feab-174">Следующий пример возврата функции в качестве значения вызова функции создает простую игру подбора.</span><span class="sxs-lookup"><span data-stu-id="3feab-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="3feab-175">Чтобы создать игру, вызовите `makeGame` метод с тем значением, `target`в котором вы хотите угадать.</span><span class="sxs-lookup"><span data-stu-id="3feab-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="3feab-176">Возвращаемое значение функции `makeGame` — это функция, которая принимает один аргумент (Guess) и сообщает, верно ли предположение.</span><span class="sxs-lookup"><span data-stu-id="3feab-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="3feab-177">Следующий код вызывает метод `makeGame`, отправляя значение `7` для `target`.</span><span class="sxs-lookup"><span data-stu-id="3feab-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="3feab-178">Идентификатор `playGame` привязан к возвращенному лямбда-выражению.</span><span class="sxs-lookup"><span data-stu-id="3feab-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="3feab-179">Таким образом `playGame` , представляет собой функцию, принимающую в качестве одного аргумента `guess`значение для.</span><span class="sxs-lookup"><span data-stu-id="3feab-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="3feab-180">Каррированных функции</span><span class="sxs-lookup"><span data-stu-id="3feab-180">Curried Functions</span></span>

<span data-ttu-id="3feab-181">Многие примеры в предыдущем разделе можно написать более кратко, используя преимущества неявного *карринг* в F# объявлениях функций.</span><span class="sxs-lookup"><span data-stu-id="3feab-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="3feab-182">Карринг — это процесс, преобразуя функцию, имеющую несколько параметров, в ряд встроенных функций, каждый из которых имеет один параметр.</span><span class="sxs-lookup"><span data-stu-id="3feab-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="3feab-183">В F#функции, имеющие более одного параметра, по сути являются каррированных.</span><span class="sxs-lookup"><span data-stu-id="3feab-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="3feab-184">Например, `compose` из предыдущего раздела можно написать, как показано в следующем кратком стиле с тремя параметрами.</span><span class="sxs-lookup"><span data-stu-id="3feab-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="3feab-185">Однако результатом является функция одного параметра, возвращающая функцию одного параметра, которая, в свою очередь, возвращает другую функцию одного параметра, как показано в `compose4curried`.</span><span class="sxs-lookup"><span data-stu-id="3feab-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="3feab-186">Доступ к этой функции можно получить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="3feab-186">You can access this function in several ways.</span></span> <span data-ttu-id="3feab-187">Каждый из следующих примеров возвращает и отображает 18.</span><span class="sxs-lookup"><span data-stu-id="3feab-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="3feab-188">В любом из `compose4` примеров `compose4curried` можно заменить на.</span><span class="sxs-lookup"><span data-stu-id="3feab-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="3feab-189">Чтобы убедиться, что функция все еще работает, как и раньше, попробуйте повторить исходные тестовые случаи.</span><span class="sxs-lookup"><span data-stu-id="3feab-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> <span data-ttu-id="3feab-190">Можно ограничить карринг, заключив параметры в кортежи.</span><span class="sxs-lookup"><span data-stu-id="3feab-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="3feab-191">Дополнительные сведения см. в разделе "Шаблоны параметров" раздела [Параметры и аргументы](../language-reference/parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="3feab-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="3feab-192">В следующем примере используется неявное карринг для записи более короткой версии `makeGame`.</span><span class="sxs-lookup"><span data-stu-id="3feab-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="3feab-193">Сведения о том, `makeGame` как конструкции и `game` возвращают функцию, менее явны в этом формате, но можно проверить с помощью исходных тестовых случаев, в которых результат совпадает.</span><span class="sxs-lookup"><span data-stu-id="3feab-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="3feab-194">Дополнительные сведения о карринг см. в разделе "частичное применение аргументов" в [функциях](../language-reference/functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="3feab-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="3feab-195">Идентификатор и определение функции взаимозаменяемы</span><span class="sxs-lookup"><span data-stu-id="3feab-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="3feab-196">Имя `num` переменной в предыдущих примерах вычисляется как целое число 10, и это не удивительно, `num` что допустимо, 10 также является допустимым.</span><span class="sxs-lookup"><span data-stu-id="3feab-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="3feab-197">То же самое касается идентификаторов функций и их значений: где можно использовать имя функции, можно использовать лямбда-выражение, к которому она привязана.</span><span class="sxs-lookup"><span data-stu-id="3feab-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="3feab-198">В следующем примере определяется `Boolean` функция с именем `isNegative`, а затем используется имя функции и определение взаимозаменяемой функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="3feab-199">В следующих трех примерах возвращаются и отображаются `False`.</span><span class="sxs-lookup"><span data-stu-id="3feab-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="3feab-200">Чтобы сделать это на один шаг дальше, замените значение, `applyIt` привязанное к для `applyIt`.</span><span class="sxs-lookup"><span data-stu-id="3feab-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="3feab-201">Функции являются значениями первого класса в F\#</span><span class="sxs-lookup"><span data-stu-id="3feab-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="3feab-202">В примерах, приведенных в предыдущих разделах, F# показано, что функции в удовлетворяют критериям для использования F#значений первого класса в:</span><span class="sxs-lookup"><span data-stu-id="3feab-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="3feab-203">Идентификатор можно привязать к определению функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="3feab-204">Функцию можно сохранить в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="3feab-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="3feab-205">Функцию можно передать в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="3feab-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="3feab-206">Функцию можно вернуть в качестве значения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="3feab-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="3feab-207">Дополнительные сведения о F#см. в справочнике по [ F# языку](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="3feab-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="3feab-208">Пример</span><span class="sxs-lookup"><span data-stu-id="3feab-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="3feab-209">Описание</span><span class="sxs-lookup"><span data-stu-id="3feab-209">Description</span></span>

<span data-ttu-id="3feab-210">Следующий код содержит все примеры, приведенные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3feab-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="3feab-211">Код</span><span class="sxs-lookup"><span data-stu-id="3feab-211">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="3feab-212">См. также</span><span class="sxs-lookup"><span data-stu-id="3feab-212">See also</span></span>

- [<span data-ttu-id="3feab-213">Списки</span><span class="sxs-lookup"><span data-stu-id="3feab-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="3feab-214">Кортежи</span><span class="sxs-lookup"><span data-stu-id="3feab-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="3feab-215">Функции</span><span class="sxs-lookup"><span data-stu-id="3feab-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="3feab-216">`let`Привязки</span><span class="sxs-lookup"><span data-stu-id="3feab-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="3feab-217">Лямбда-выражения: Ключевое слово `fun`</span><span class="sxs-lookup"><span data-stu-id="3feab-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
