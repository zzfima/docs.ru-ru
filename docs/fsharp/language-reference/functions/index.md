---
title: Функции
description: Сведения о функциях F# в и F# о том, как поддерживает стандартные конструкции функционального программирования.
ms.date: 05/16/2016
ms.openlocfilehash: c6b8307f51ffcdc77fe4352b2305fca1f247ccbb
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423954"
---
# <a name="functions"></a><span data-ttu-id="6ff17-103">Функции</span><span class="sxs-lookup"><span data-stu-id="6ff17-103">Functions</span></span>

<span data-ttu-id="6ff17-104">Функции являются основным элементом выполнения программы на любом языке программирования.</span><span class="sxs-lookup"><span data-stu-id="6ff17-104">Functions are the fundamental unit of program execution in any programming language.</span></span> <span data-ttu-id="6ff17-105">Как и в других языках, функция F# имеет имя, может иметь параметры и принимать аргументы, а также имеет тело.</span><span class="sxs-lookup"><span data-stu-id="6ff17-105">As in other languages, an F# function has a name, can have parameters and take arguments, and has a body.</span></span> <span data-ttu-id="6ff17-106">F# также поддерживает конструкции функционального программирования, например, обработку функций как значений, использование неименованных функций в выражениях, объединение функций для образования новых функций, каррированные функции и неявное определение функций посредством частичного применения аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-106">F# also supports functional programming constructs such as treating functions as values, using unnamed functions in expressions, composition of functions to form new functions, curried functions, and the implicit definition of functions by way of the partial application of function arguments.</span></span>

<span data-ttu-id="6ff17-107">Функции определяются с помощью ключевого слова `let`, или, если функция является рекурсивной, сочетания ключевых слов `let rec`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-107">You define functions by using the `let` keyword, or, if the function is recursive, the `let rec` keyword combination.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ff17-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ff17-108">Syntax</span></span>

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a><span data-ttu-id="6ff17-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6ff17-109">Remarks</span></span>

<span data-ttu-id="6ff17-110">Элемент *function-name* — это идентификатор, который представляет функцию.</span><span class="sxs-lookup"><span data-stu-id="6ff17-110">The *function-name* is an identifier that represents the function.</span></span> <span data-ttu-id="6ff17-111">Элемент *parameter-list* состоит из последовательных параметров, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="6ff17-111">The *parameter-list* consists of successive parameters that are separated by spaces.</span></span> <span data-ttu-id="6ff17-112">Вы можете указать явный тип для каждого параметра, как описано в разделе "Параметры".</span><span class="sxs-lookup"><span data-stu-id="6ff17-112">You can specify an explicit type for each parameter, as described in the Parameters section.</span></span> <span data-ttu-id="6ff17-113">Если не указать конкретный тип аргумента, компилятор пытается определить тип из тела функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-113">If you do not specify a specific argument type, the compiler attempts to infer the type from the function body.</span></span> <span data-ttu-id="6ff17-114">Элемент *function-body* состоит из выражения.</span><span class="sxs-lookup"><span data-stu-id="6ff17-114">The *function-body* consists of an expression.</span></span> <span data-ttu-id="6ff17-115">Выражение, представляющее тело функции, обычно является составным. Оно состоит из нескольких выражений, которые в результате дают итоговое выражение, являющееся возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="6ff17-115">The expression that makes up the function body is typically a compound expression consisting of a number of expressions that culminate in a final expression that is the return value.</span></span> <span data-ttu-id="6ff17-116">Элемент *return-type* представляет собой двоеточие, за которым следует тип, и является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6ff17-116">The *return-type* is a colon followed by a type and is optional.</span></span> <span data-ttu-id="6ff17-117">Если вы явно не указываете тип возвращаемого значения, компилятор определяет тип возвращаемого значения из итогового выражения.</span><span class="sxs-lookup"><span data-stu-id="6ff17-117">If you do not specify the type of the return value explicitly, the compiler determines the return type from the final expression.</span></span>

<span data-ttu-id="6ff17-118">Простое определение функции выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ff17-118">A simple function definition resembles the following:</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="6ff17-119">В предыдущем примере `f` является именем функции, `x` — аргументом, имеющим тип `int`, `x + 1` является телом функции, а возвращаемое значение имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-119">In the previous example, the function name is `f`, the argument is `x`, which has type `int`, the function body is `x + 1`, and the return value is of type `int`.</span></span>

<span data-ttu-id="6ff17-120">Функции могут быть помечены как `inline`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-120">Functions can be marked `inline`.</span></span> <span data-ttu-id="6ff17-121">Сведения о `inline` см. в статье [Встраиваемые функции](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6ff17-121">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

## <a name="scope"></a><span data-ttu-id="6ff17-122">Область</span><span class="sxs-lookup"><span data-stu-id="6ff17-122">Scope</span></span>

<span data-ttu-id="6ff17-123">На любом уровне области, отличной от области модуля, не будет ошибкой повторно использовать значение или имя функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-123">At any level of scope other than module scope, it is not an error to reuse a value or function name.</span></span> <span data-ttu-id="6ff17-124">При повторном использовании имя, объявленное позже, затемняет имя, объявленное раньше.</span><span class="sxs-lookup"><span data-stu-id="6ff17-124">If you reuse a name, the name declared later shadows the name declared earlier.</span></span> <span data-ttu-id="6ff17-125">Но в области верхнего уровня в модуле имена должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="6ff17-125">However, at the top level scope in a module, names must be unique.</span></span> <span data-ttu-id="6ff17-126">Например, следующий код вызывает ошибку, когда отображается в области модуля, и не вызывает ее при отображении внутри функции:</span><span class="sxs-lookup"><span data-stu-id="6ff17-126">For example, the following code produces an error when it appears at module scope, but not when it appears inside a function:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

<span data-ttu-id="6ff17-127">Но следующий код допустим на любом уровне области:</span><span class="sxs-lookup"><span data-stu-id="6ff17-127">But the following code is acceptable at any level of scope:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a><span data-ttu-id="6ff17-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ff17-128">Parameters</span></span>

<span data-ttu-id="6ff17-129">Имена параметров указываются после имени функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-129">Names of parameters are listed after the function name.</span></span> <span data-ttu-id="6ff17-130">Можно указать тип для параметра, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6ff17-130">You can specify a type for a parameter, as shown in the following example:</span></span>

```fsharp
let f (x : int) = x + 1
```

<span data-ttu-id="6ff17-131">Если тип указан, он стоит после имени параметра и отделяется от него двоеточием.</span><span class="sxs-lookup"><span data-stu-id="6ff17-131">If you specify a type, it follows the name of the parameter and is separated from the name by a colon.</span></span> <span data-ttu-id="6ff17-132">Если тип параметра не указан, он определяется компилятором.</span><span class="sxs-lookup"><span data-stu-id="6ff17-132">If you omit the type for the parameter, the parameter type is inferred by the compiler.</span></span> <span data-ttu-id="6ff17-133">Например, в следующем определении функции аргумент `x` определяется, как относящийся к типу `int`, так как 1 имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-133">For example, in the following function definition, the argument `x` is inferred to be of type `int` because 1 is of type `int`.</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="6ff17-134">Но компилятор попытается сделать функцию как можно более универсальной.</span><span class="sxs-lookup"><span data-stu-id="6ff17-134">However, the compiler will attempt to make the function as generic as possible.</span></span> <span data-ttu-id="6ff17-135">Например, изучите следующий код:</span><span class="sxs-lookup"><span data-stu-id="6ff17-135">For example, note the following code:</span></span>

```fsharp
let f x = (x, x)
```

<span data-ttu-id="6ff17-136">Функция создает кортеж из одного аргумента любого типа.</span><span class="sxs-lookup"><span data-stu-id="6ff17-136">The function creates a tuple from one argument of any type.</span></span> <span data-ttu-id="6ff17-137">Так как тип не задан, функция может использоваться с любым типом аргумента.</span><span class="sxs-lookup"><span data-stu-id="6ff17-137">Because the type is not specified, the function can be used with any argument type.</span></span> <span data-ttu-id="6ff17-138">Дополнительные сведения см. в статье [Автоматическое обобщение](../generics/automatic-generalization.md).</span><span class="sxs-lookup"><span data-stu-id="6ff17-138">For more information, see [Automatic Generalization](../generics/automatic-generalization.md).</span></span>

## <a name="function-bodies"></a><span data-ttu-id="6ff17-139">Тела функций</span><span class="sxs-lookup"><span data-stu-id="6ff17-139">Function Bodies</span></span>

<span data-ttu-id="6ff17-140">Тело функции может содержать определения локальных переменных и функций.</span><span class="sxs-lookup"><span data-stu-id="6ff17-140">A function body can contain definitions of local variables and functions.</span></span> <span data-ttu-id="6ff17-141">Такие переменные и функции находятся в области действия внутри тела текущей функции, но не за его пределами.</span><span class="sxs-lookup"><span data-stu-id="6ff17-141">Such variables and functions are in scope in the body of the current function but not outside it.</span></span> <span data-ttu-id="6ff17-142">Если включен упрощенный синтаксис, нужно использовать отступ, чтобы указать, что определение находится внутри тела функции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6ff17-142">When you have the lightweight syntax option enabled, you must use indentation to indicate that a definition is in a function body, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

<span data-ttu-id="6ff17-143">Дополнительные сведения см. в статьях [Рекомендации по форматированию кода](../../style-guide/formatting.md) и [Подробный синтаксис](../verbose-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="6ff17-143">For more information, see [Code Formatting Guidelines](../../style-guide/formatting.md) and [Verbose Syntax](../verbose-syntax.md).</span></span>

## <a name="return-values"></a><span data-ttu-id="6ff17-144">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="6ff17-144">Return Values</span></span>

<span data-ttu-id="6ff17-145">Компилятор использует итоговое выражение в теле функции, чтобы определить возвращаемое значение и его тип.</span><span class="sxs-lookup"><span data-stu-id="6ff17-145">The compiler uses the final expression in a function body to determine the return value and type.</span></span> <span data-ttu-id="6ff17-146">Компилятор может вывести тип итогового выражения из предыдущих выражений.</span><span class="sxs-lookup"><span data-stu-id="6ff17-146">The compiler might infer the type of the final expression from previous expressions.</span></span> <span data-ttu-id="6ff17-147">В функции `cylinderVolume`, показанной в предыдущем разделе, тип `pi` определяется по типу литерала `3.14159` как `float`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-147">In the function `cylinderVolume`, shown in the previous section, the type of `pi` is determined from the type of the literal `3.14159` to be `float`.</span></span> <span data-ttu-id="6ff17-148">Компилятор использует тип `pi`, чтобы определить тип выражения `h * pi * r * r` как `float`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-148">The compiler uses the type of `pi` to determine the type of the expression `h * pi * r * r` to be `float`.</span></span> <span data-ttu-id="6ff17-149">Таким образом, общим типом возвращаемого значения функции является `float`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-149">Therefore, the overall return type of the function is `float`.</span></span>

<span data-ttu-id="6ff17-150">Чтобы явно задать возвращаемое значение, составьте код следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ff17-150">To specify the return value explicitly, write the code as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

<span data-ttu-id="6ff17-151">В приведенном выше коде компилятор применяет **float** ко всей функции. Если требуется применить его и к типам параметров, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="6ff17-151">As the code is written above, the compiler applies **float** to the entire function; if you mean to apply it to the parameter types as well, use the following code:</span></span>

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a><span data-ttu-id="6ff17-152">Вызов функции</span><span class="sxs-lookup"><span data-stu-id="6ff17-152">Calling a Function</span></span>

<span data-ttu-id="6ff17-153">Вы можете вызывать функции, указав имя функции, за которыми следует пробел, а затем аргументы, разделенные пробелами.</span><span class="sxs-lookup"><span data-stu-id="6ff17-153">You call functions by specifying the function name followed by a space and then any arguments separated by spaces.</span></span> <span data-ttu-id="6ff17-154">Например, чтобы вызвать функцию **cylinderVolume** и назначить результат значению **vol**, составьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="6ff17-154">For example, to call the function **cylinderVolume** and assign the result to the value **vol**, you write the following code:</span></span>

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a><span data-ttu-id="6ff17-155">Частичное применение аргументов</span><span class="sxs-lookup"><span data-stu-id="6ff17-155">Partial Application of Arguments</span></span>

<span data-ttu-id="6ff17-156">Если число предоставленных аргументов меньше заданного их количества, создается новая функция, ожидающая оставшиеся аргументы.</span><span class="sxs-lookup"><span data-stu-id="6ff17-156">If you supply fewer than the specified number of arguments, you create a new function that expects the remaining arguments.</span></span> <span data-ttu-id="6ff17-157">Такой метод работы с аргументами называется *каррингом* и характерен для языков функционального программирования, таких как F#.</span><span class="sxs-lookup"><span data-stu-id="6ff17-157">This method of handling arguments is referred to as *currying* and is a characteristic of functional programming languages like F#.</span></span> <span data-ttu-id="6ff17-158">Предположим, вы работаете с двумя размерами труб: одна имеет радиус **2,0**, а другая — радиус **3,0**.</span><span class="sxs-lookup"><span data-stu-id="6ff17-158">For example, suppose you are working with two sizes of pipe: one has a radius of **2.0** and the other has a radius of **3.0**.</span></span> <span data-ttu-id="6ff17-159">Можно создать функции, определяющие объем трубы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ff17-159">You could create functions that determine the volume of pipe as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

<span data-ttu-id="6ff17-160">Затем можно предоставить дополнительный аргумент для различных длин трубы двух разных размеров:</span><span class="sxs-lookup"><span data-stu-id="6ff17-160">You would then supply the additional argument as needed for various lengths of pipe of the two different sizes:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a><span data-ttu-id="6ff17-161">Рекурсивные функции</span><span class="sxs-lookup"><span data-stu-id="6ff17-161">Recursive Functions</span></span>

<span data-ttu-id="6ff17-162">*Рекурсивными* называются функциями, которые вызывают сами себя.</span><span class="sxs-lookup"><span data-stu-id="6ff17-162">*Recursive functions* are functions that call themselves.</span></span> <span data-ttu-id="6ff17-163">Для них нужно указать ключевое слово **rec**, следующее за ключевым словом **let**.</span><span class="sxs-lookup"><span data-stu-id="6ff17-163">They require that you specify the **rec** keyword following the **let** keyword.</span></span> <span data-ttu-id="6ff17-164">Вызов рекурсивной функции в теле функции выполняется так же, как и для любой другой функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-164">Invoke the recursive function from within the body of the function just as you would invoke any function call.</span></span> <span data-ttu-id="6ff17-165">Следующая рекурсивная функция выполняет вычисление n-<sup>го</sup> числа Фибоначчи.</span><span class="sxs-lookup"><span data-stu-id="6ff17-165">The following recursive function computes the *n*<sup>th</sup> Fibonacci number.</span></span> <span data-ttu-id="6ff17-166">Последовательность чисел Фибоначчи известна с античных времен. В ней каждый последующий элемент равен сумме двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="6ff17-166">The Fibonacci number sequence has been known since antiquity and is a sequence in which each successive number is the sum of the previous two numbers in the sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

<span data-ttu-id="6ff17-167">Некоторые рекурсивные функции могут переполнить стек программы или работать неэффективно, если при их написании не принимать меры предосторожности и не использовать специальные методики, такие как накапливаемые значения и продолжения.</span><span class="sxs-lookup"><span data-stu-id="6ff17-167">Some recursive functions might overflow the program stack or perform inefficiently if you do not write them with care and with awareness of special techniques, such as the use of accumulators and continuations.</span></span>

## <a name="function-values"></a><span data-ttu-id="6ff17-168">Значения функции</span><span class="sxs-lookup"><span data-stu-id="6ff17-168">Function Values</span></span>

<span data-ttu-id="6ff17-169">В языке F# все функции считаются значениями. На самом деле они называются *значениями функции*.</span><span class="sxs-lookup"><span data-stu-id="6ff17-169">In F#, all functions are considered values; in fact, they are known as *function values*.</span></span> <span data-ttu-id="6ff17-170">Так как функции являются значениями, они могут использоваться в качестве аргументов для других функций или в других контекстах, где применяются значения.</span><span class="sxs-lookup"><span data-stu-id="6ff17-170">Because functions are values, they can be used as arguments to other functions or in other contexts where values are used.</span></span> <span data-ttu-id="6ff17-171">Ниже приведен пример функции, которая принимает значение функции в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="6ff17-171">Following is an example of a function that takes a function value as an argument:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

<span data-ttu-id="6ff17-172">Укажите тип значения функции с помощью токена `->`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-172">You specify the type of a function value by using the `->` token.</span></span> <span data-ttu-id="6ff17-173">В левой части токена находится тип аргумента, а в правой части — возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="6ff17-173">On the left side of this token is the type of the argument, and on the right side is the return value.</span></span> <span data-ttu-id="6ff17-174">В предыдущем примере `apply1` является функцией, которая принимает функцию `transform` как аргумент, где `transform` — это функция, которая принимает целое число и возвращает другое целое число.</span><span class="sxs-lookup"><span data-stu-id="6ff17-174">In the previous example, `apply1` is a function that takes a function `transform` as an argument, where `transform` is a function that takes an integer and returns another integer.</span></span> <span data-ttu-id="6ff17-175">В следующем коде показано использование `apply1`:</span><span class="sxs-lookup"><span data-stu-id="6ff17-175">The following code shows how to use `apply1`:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

<span data-ttu-id="6ff17-176">После выполнения предыдущего кода `result` будет иметь значение 101.</span><span class="sxs-lookup"><span data-stu-id="6ff17-176">The value of `result` will be 101 after the previous code runs.</span></span>

<span data-ttu-id="6ff17-177">Несколько аргументов разделяются токенами `->`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6ff17-177">Multiple arguments are separated by successive `->` tokens, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

<span data-ttu-id="6ff17-178">Результат равен 200.</span><span class="sxs-lookup"><span data-stu-id="6ff17-178">The result is 200.</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="6ff17-179">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="6ff17-179">Lambda Expressions</span></span>

<span data-ttu-id="6ff17-180">*Лямбда-выражение* — это неименованная функция.</span><span class="sxs-lookup"><span data-stu-id="6ff17-180">A *lambda expression* is an unnamed function.</span></span> <span data-ttu-id="6ff17-181">В предыдущих примерах вместо определения именованных функций **increment** и **mul** можно было воспользоваться лямбда-выражением:</span><span class="sxs-lookup"><span data-stu-id="6ff17-181">In the previous examples, instead of defining named functions **increment** and **mul**, you could use lambda expressions as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

<span data-ttu-id="6ff17-182">Лямбда-выражения определяются с помощью ключевого слова `fun`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-182">You define lambda expressions by using the `fun` keyword.</span></span> <span data-ttu-id="6ff17-183">Лямбда-выражение напоминает определение функции, за исключением того, что вместо токена `=` для отделения списка аргументов от тела функции используется токен `->`.</span><span class="sxs-lookup"><span data-stu-id="6ff17-183">A lambda expression resembles a function definition, except that instead of the `=` token, the `->` token is used to separate the argument list from the function body.</span></span> <span data-ttu-id="6ff17-184">Как и в обычном определении функции, типы аргументов могут выводиться или указываться явно, а тип возвращаемого значения лямбда-выражения выводится из типа последнего выражения в теле.</span><span class="sxs-lookup"><span data-stu-id="6ff17-184">As in a regular function definition, the argument types can be inferred or specified explicitly, and the return type of the lambda expression is inferred from the type of the last expression in the body.</span></span> <span data-ttu-id="6ff17-185">Дополнительные сведения см. в статье [Лямбда-выражения: ключевое слово `fun`](../functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="6ff17-185">For more information, see [Lambda Expressions: The `fun` Keyword](../functions/lambda-expressions-the-fun-keyword.md).</span></span>

## <a name="function-composition-and-pipelining"></a><span data-ttu-id="6ff17-186">Композиция и конвейеризация функций</span><span class="sxs-lookup"><span data-stu-id="6ff17-186">Function Composition and Pipelining</span></span>

<span data-ttu-id="6ff17-187">В F# функции могут состоять из других функций.</span><span class="sxs-lookup"><span data-stu-id="6ff17-187">Functions in F# can be composed from other functions.</span></span> <span data-ttu-id="6ff17-188">Композицией двух функций **function1** и **function2** является другая функция, которая представляет применение функции **function1** с последующим применением функции **function2**:</span><span class="sxs-lookup"><span data-stu-id="6ff17-188">The composition of two functions **function1** and **function2** is another function that represents the application of **function1** followed the application of **function2**:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

<span data-ttu-id="6ff17-189">Результат равен 202.</span><span class="sxs-lookup"><span data-stu-id="6ff17-189">The result is 202.</span></span>

<span data-ttu-id="6ff17-190">Конвейеризация позволяет объединять вызовы функций в виде последовательных операций.</span><span class="sxs-lookup"><span data-stu-id="6ff17-190">Pipelining enables function calls to be chained together as successive operations.</span></span> <span data-ttu-id="6ff17-191">Конвейеризация работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ff17-191">Pipelining works as follows:</span></span>

```fsharp
let result = 100 |> function1 |> function2
```

<span data-ttu-id="6ff17-192">Результат снова равен 202.</span><span class="sxs-lookup"><span data-stu-id="6ff17-192">The result is again 202.</span></span>

<span data-ttu-id="6ff17-193">Операторы композиции принимают две функции и возвращают функцию. Операторы конвейера принимают функцию и аргумент и возвращают значение.</span><span class="sxs-lookup"><span data-stu-id="6ff17-193">The composition operators take two functions and return a function; by contrast, the pipeline operators take a function and an argument and return a value.</span></span> <span data-ttu-id="6ff17-194">В следующем примере кода показано различие между операторами конвейера и композиции. Там продемонстрировано отличие в сигнатурах и использовании функций.</span><span class="sxs-lookup"><span data-stu-id="6ff17-194">The following code example shows the difference between the pipeline and composition operators by showing the differences in the function signatures and usage.</span></span>

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a><span data-ttu-id="6ff17-195">Перегрузка функций</span><span class="sxs-lookup"><span data-stu-id="6ff17-195">Overloading Functions</span></span>

<span data-ttu-id="6ff17-196">Можно перегружать методы типа, но не функции.</span><span class="sxs-lookup"><span data-stu-id="6ff17-196">You can overload methods of a type but not functions.</span></span> <span data-ttu-id="6ff17-197">Дополнительные сведения см. в статье [Методы](../members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="6ff17-197">For more information, see [Methods](../members/methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ff17-198">См. также</span><span class="sxs-lookup"><span data-stu-id="6ff17-198">See also</span></span>

- [<span data-ttu-id="6ff17-199">Значения</span><span class="sxs-lookup"><span data-stu-id="6ff17-199">Values</span></span>](../values/index.md)
- [<span data-ttu-id="6ff17-200">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6ff17-200">F# Language Reference</span></span>](../index.md)
