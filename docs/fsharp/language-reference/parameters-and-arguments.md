---
title: Параметры и аргументы (F#)
description: 'Дополнительные сведения о поддержке языка F # для определения параметров и передачи аргументов в функции, методы и свойства.'
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566224"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="bbee6-103">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="bbee6-103">Parameters and Arguments</span></span>

<span data-ttu-id="bbee6-104">В этом разделе описывается поддержка языком определения параметров и передачи аргументов в функции, методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="bbee6-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="bbee6-105">Он содержит сведения о передаче по ссылке и как определять и использовать методы, которые могут принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="bbee6-106">Параметры и аргументы</span><span class="sxs-lookup"><span data-stu-id="bbee6-106">Parameters and Arguments</span></span>
<span data-ttu-id="bbee6-107">Термин *параметр* используется для описания имена для значений, которые требуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="bbee6-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="bbee6-108">Термин *аргумент* используются значения, предоставляемые для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="bbee6-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="bbee6-109">Параметры указываются в кортеже или каррированные или некоторое сочетание этих двух.</span><span class="sxs-lookup"><span data-stu-id="bbee6-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="bbee6-110">Аргументы можно передать с помощью явно указанного имени параметра.</span><span class="sxs-lookup"><span data-stu-id="bbee6-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="bbee6-111">Параметры методов можно объявить необязательным и задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbee6-111">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="bbee6-112">Шаблоны параметров</span><span class="sxs-lookup"><span data-stu-id="bbee6-112">Parameter Patterns</span></span>
<span data-ttu-id="bbee6-113">Параметры для функций и методов, как правило, шаблоны, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="bbee6-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="bbee6-114">Это означает, что, в принципе, один из шаблонов, описанных в [выражениях сопоставления](match-expressions.md) можно использовать в списке параметров для функции или члена.</span><span class="sxs-lookup"><span data-stu-id="bbee6-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="bbee6-115">Методы обычно используют кортеже передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="bbee6-116">Это обеспечивает более четкие результаты с точки зрения других языков .NET, так как в кортеже способ передачи аргументов в методах .NET.</span><span class="sxs-lookup"><span data-stu-id="bbee6-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="bbee6-117">Каррированные чаще всего используется с функциями, созданными с помощью `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="bbee6-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="bbee6-118">Следующий псевдокод отображает примеры кортежа и переданными аргументами.</span><span class="sxs-lookup"><span data-stu-id="bbee6-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="bbee6-119">Комбинированные формы возможны, когда некоторые аргументы имеют кортежей, а некоторые — нет.</span><span class="sxs-lookup"><span data-stu-id="bbee6-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="bbee6-120">Другие шаблоны могут также использоваться в списках параметров, но если параметр шаблона не соответствует всех возможных входных значений, то возможно неполное соответствие во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbee6-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="bbee6-121">Исключение `MatchFailureException` генерируется, если значение аргумента не совпадает с шаблонами, указанными в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="bbee6-122">Компилятор выдает предупреждение, если шаблон параметров неполных совпадений.</span><span class="sxs-lookup"><span data-stu-id="bbee6-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="bbee6-123">По крайней мере один шаблон часто имеет смысл использовать списки параметров, и это шаблон подстановочного знака.</span><span class="sxs-lookup"><span data-stu-id="bbee6-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="bbee6-124">Вы можете использовать этот шаблон в списке параметров, при игнорировать любые аргументы, передаваемые.</span><span class="sxs-lookup"><span data-stu-id="bbee6-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="bbee6-125">Следующий код иллюстрирует использование этот шаблон в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="bbee6-126">Этот шаблон может быть полезным, всякий раз, когда нет необходимости аргументы, передаваемые в, как Главная точка входа в программу, если вы не заинтересованы в аргументах командной строки, которые обычно предоставляются в виде строкового массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bbee6-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="bbee6-127">Другие шаблоны, которые иногда используются в аргументах, `as` шаблон и идентификатор шаблоны, связанные с размеченные объединения и активные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="bbee6-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="bbee6-128">Шаблон размеченного объединения одиночным можно использовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbee6-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="bbee6-129">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbee6-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="bbee6-130">Активные шаблоны можно использовать как параметры, например, при преобразовании аргумента в требуемый формат, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bbee6-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="bbee6-131">Можно использовать `as` шаблон для хранения совпадающее значение как локальное значение, как показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="bbee6-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="bbee6-132">Иногда используется другой шаблон — функция, которая остается имя последнего аргумента, предоставляя в теле функции, лямбда-выражение сразу же выполняет соответствия шаблону неявный аргумент.</span><span class="sxs-lookup"><span data-stu-id="bbee6-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="bbee6-133">Примером является следующий код.</span><span class="sxs-lookup"><span data-stu-id="bbee6-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="bbee6-134">Этот код определяет функцию, которая принимает универсального списка и возвращает `true` Если список пуст, и `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="bbee6-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="bbee6-135">Использование таких приемов может сделать код более сложным для восприятия.</span><span class="sxs-lookup"><span data-stu-id="bbee6-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="bbee6-136">В некоторых случаях шаблонов, включающих неполным совпадением полезны, например, если вы знаете, что списки в программе имеют только три элемента, можно использовать шаблон, как показано ниже в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="bbee6-137">Использование шаблонов с неполным совпадением лучше всего зарезервировано для быстрого создания прототипов и других временных задач.</span><span class="sxs-lookup"><span data-stu-id="bbee6-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="bbee6-138">Компилятор выдаст предупреждение для такого кода.</span><span class="sxs-lookup"><span data-stu-id="bbee6-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="bbee6-139">Такие шаблоны не могут охватывать в общем случае, когда всех возможных входных значений и следовательно, не подходят для компонента API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="bbee6-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="bbee6-140">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="bbee6-140">Named Arguments</span></span>
<span data-ttu-id="bbee6-141">Аргументы методов могут указываться по позиции в списке аргументов, разделенных запятыми, или могут быть переданы в метод явно, указав имя, за которым следует знак равенства и значение должны быть переданы в.</span><span class="sxs-lookup"><span data-stu-id="bbee6-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="bbee6-142">Если указано, указав имя, они могут отображаться в порядке, отличном от используемого в объявлении.</span><span class="sxs-lookup"><span data-stu-id="bbee6-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="bbee6-143">Именованные аргументы можно сделать код более читаемым и более настраиваться определенные типы изменений в API-Интерфейсе, такие как изменение порядка параметров метода.</span><span class="sxs-lookup"><span data-stu-id="bbee6-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="bbee6-144">Именованные аргументы можно использовать только в методах, не для `let`-связанные функции, значения функции или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="bbee6-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="bbee6-145">В следующем примере кода показано использование именованных аргументов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="bbee6-146">При вызове конструктора класса можно задать значения свойств класса с помощью синтаксиса, аналогичного синтаксису именованных аргументов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="bbee6-147">В следующем примере показано этот синтаксис.</span><span class="sxs-lookup"><span data-stu-id="bbee6-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="bbee6-148">Дополнительные сведения см. в разделе [конструкторы (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="bbee6-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="bbee6-149">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="bbee6-149">Optional Parameters</span></span>
<span data-ttu-id="bbee6-150">Можно указать необязательный параметр для метода, используя знак вопроса перед именем параметра.</span><span class="sxs-lookup"><span data-stu-id="bbee6-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="bbee6-151">Необязательные параметры интерпретируются как тип параметра в языке F #, поэтому их можно запрашивать обычным способом, что запрашиваются типы параметров, с помощью `match` выражение с `Some` и `None`.</span><span class="sxs-lookup"><span data-stu-id="bbee6-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="bbee6-152">Необязательные параметры можно использовать только для членов, но не для функций, созданных с помощью `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="bbee6-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="bbee6-153">Можно также использовать функцию `defaultArg`, который задает значение по умолчанию для необязательного аргумента.</span><span class="sxs-lookup"><span data-stu-id="bbee6-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="bbee6-154">`defaultArg` Функция принимает необязательный параметр в качестве первого аргумента и значение по умолчанию в качестве второго.</span><span class="sxs-lookup"><span data-stu-id="bbee6-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="bbee6-155">Следующий пример иллюстрирует использование необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="bbee6-156">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbee6-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="bbee6-157">Передача по ссылке</span><span class="sxs-lookup"><span data-stu-id="bbee6-157">Passing by Reference</span></span>
<span data-ttu-id="bbee6-158">F # поддерживает `byref` ключевое слово, которое указывает, что параметр передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="bbee6-158">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="bbee6-159">Это означает, что любые изменения значения сохраняются после выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="bbee6-159">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="bbee6-160">Значения, указанные в `byref` параметр должен быть изменяемым.</span><span class="sxs-lookup"><span data-stu-id="bbee6-160">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="bbee6-161">Кроме того можно передавать ссылочные ячейки соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="bbee6-161">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="bbee6-162">Передача по ссылке в языках .NET используется как способ возврата более одного значения из функции.</span><span class="sxs-lookup"><span data-stu-id="bbee6-162">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="bbee6-163">В языке F # можно возвращать кортеж для этой цели или использовать в качестве параметра ссылочной ячейки.</span><span class="sxs-lookup"><span data-stu-id="bbee6-163">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="bbee6-164">`byref` Главным образом предназначен для взаимодействия с библиотеками .NET.</span><span class="sxs-lookup"><span data-stu-id="bbee6-164">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="bbee6-165">Следующие примеры иллюстрируют использование `byref` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="bbee6-165">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="bbee6-166">Обратите внимание, что при использовании ссылочной ячейки в качестве параметра необходимо создать ссылочную ячейку как именованное значение и использовать его в качестве параметра, не просто добавить `ref` оператора, как показано в первом вызове `Increment` в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bbee6-166">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="bbee6-167">Поскольку при создании ссылочной ячейки создается копия базового значения, первый вызов увеличивает только временное значение.</span><span class="sxs-lookup"><span data-stu-id="bbee6-167">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="bbee6-168">Кортеж можно использовать в качестве возвращаемого значения для хранения `out` параметрам в методах библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="bbee6-168">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="bbee6-169">Кроме того, можно рассматривать `out` параметр как `byref` параметр.</span><span class="sxs-lookup"><span data-stu-id="bbee6-169">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="bbee6-170">В следующем примере кода показаны оба способа.</span><span class="sxs-lookup"><span data-stu-id="bbee6-170">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="bbee6-171">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="bbee6-171">Parameter Arrays</span></span>
<span data-ttu-id="bbee6-172">Иногда бывает необходимо определить функцию, принимающую произвольное количество параметров различных типов.</span><span class="sxs-lookup"><span data-stu-id="bbee6-172">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="bbee6-173">Не было бы смысл создать все возможные перегруженные методы для учетной записи для всех типов, которые могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="bbee6-173">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="bbee6-174">В реализациях .NET обеспечивают поддержку таких методов за счет функции массивов параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-174">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="bbee6-175">Метод, который принимает массив параметров сигнатура может быть указано с произвольным числом параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-175">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="bbee6-176">Параметры помещаются в массив.</span><span class="sxs-lookup"><span data-stu-id="bbee6-176">The parameters are put into an array.</span></span> <span data-ttu-id="bbee6-177">Тип элементов массива определяет типы параметров, которые можно передать в функцию.</span><span class="sxs-lookup"><span data-stu-id="bbee6-177">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="bbee6-178">Если определить массив параметров с `System.Object` как тип элемента, затем клиентский код может передавать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="bbee6-178">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="bbee6-179">В F # массивы параметров можно определять только в методах.</span><span class="sxs-lookup"><span data-stu-id="bbee6-179">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="bbee6-180">Их нельзя использовать в отдельных функциях, а также функции, определенные в модулях.</span><span class="sxs-lookup"><span data-stu-id="bbee6-180">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="bbee6-181">Массив параметров определяются с помощью `ParamArray` атрибута.</span><span class="sxs-lookup"><span data-stu-id="bbee6-181">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="bbee6-182">`ParamArray` Атрибут может применяться только к последнему параметру.</span><span class="sxs-lookup"><span data-stu-id="bbee6-182">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="bbee6-183">Следующий код иллюстрирует вызов метода .NET, принимающего массив параметров и определение типа в F #, который содержит метод, который принимает массив параметров.</span><span class="sxs-lookup"><span data-stu-id="bbee6-183">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="bbee6-184">При запуске проекта, результат выполнения предыдущего кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbee6-184">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="bbee6-185">См. также</span><span class="sxs-lookup"><span data-stu-id="bbee6-185">See Also</span></span>
[<span data-ttu-id="bbee6-186">Члены</span><span class="sxs-lookup"><span data-stu-id="bbee6-186">Members</span></span>](members/index.md)
