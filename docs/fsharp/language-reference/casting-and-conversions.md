---
title: Приведение и преобразование (F#)
description: 'Узнайте, как на языке программирования F # предоставляет операторы преобразования для преобразования между различными типами-примитивами.'
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338237"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="02d60-103">Приведение и преобразование (F#)</span><span class="sxs-lookup"><span data-stu-id="02d60-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="02d60-104">В этом разделе описывается поддержка преобразований типов в F #.</span><span class="sxs-lookup"><span data-stu-id="02d60-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="02d60-105">Арифметические типы</span><span class="sxs-lookup"><span data-stu-id="02d60-105">Arithmetic Types</span></span>

<span data-ttu-id="02d60-106">F # предоставляет операторы преобразования для преобразования между различными типами-примитивами, например между целое число и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="02d60-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="02d60-107">Операторы преобразования целочисленных типов и char проверили и непроверяемые формы; с плавающей запятой операторы и `enum` оператор преобразования — нет.</span><span class="sxs-lookup"><span data-stu-id="02d60-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="02d60-108">Unchecked формы определяются в `Microsoft.FSharp.Core.Operators` и проверяемые определяются в `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="02d60-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="02d60-109">Проверяемые наличие переполнения и создает исключение времени выполнения, если полученное значение превышает ограничения типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="02d60-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="02d60-110">Каждый из этих операторов имеет имя, совпадающее имя конечного типа.</span><span class="sxs-lookup"><span data-stu-id="02d60-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="02d60-111">Например, в следующем коде, явно указанными типами слово `byte` имеет два значения.</span><span class="sxs-lookup"><span data-stu-id="02d60-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="02d60-112">Первое — это тип, а второй — оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="02d60-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="02d60-113">В следующей таблице показаны операторы преобразования, определенные в F #.</span><span class="sxs-lookup"><span data-stu-id="02d60-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="02d60-114">Оператор</span><span class="sxs-lookup"><span data-stu-id="02d60-114">Operator</span></span>|<span data-ttu-id="02d60-115">Описание</span><span class="sxs-lookup"><span data-stu-id="02d60-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="02d60-116">Преобразуйте в тип byte, 8-разрядное тип без знака.</span><span class="sxs-lookup"><span data-stu-id="02d60-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="02d60-117">Преобразуйте байт со знаком.</span><span class="sxs-lookup"><span data-stu-id="02d60-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="02d60-118">Преобразуйте в 16-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="02d60-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="02d60-119">Преобразуйте в 16-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="02d60-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="02d60-120">Преобразуйте в 32-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="02d60-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="02d60-121">Преобразуйте в 32-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="02d60-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="02d60-122">Преобразуйте в 64-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="02d60-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="02d60-123">Преобразуйте в 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="02d60-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="02d60-124">Преобразуйте в собственном целое число.</span><span class="sxs-lookup"><span data-stu-id="02d60-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="02d60-125">Преобразуйте в целое число без знака собственного.</span><span class="sxs-lookup"><span data-stu-id="02d60-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="02d60-126">Преобразование в стандарт IEEE двойной точности 64-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="02d60-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="02d60-127">Преобразование в стандарт IEEE одинарной точности 32-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="02d60-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="02d60-128">Преобразовать в `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="02d60-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="02d60-129">Преобразовать в `System.Char`, символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="02d60-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="02d60-130">Преобразуйте в перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="02d60-130">Convert to an enumerated type.</span></span>|
<span data-ttu-id="02d60-131">Помимо встроенных примитивных типов, эти операторы можно использовать с типами, реализующими `op_Explicit` или `op_Implicit` методы с подходящими сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="02d60-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="02d60-132">Например `int` оператор преобразования работает с любым типом, который предоставляет статический метод `op_Explicit` , принимает тип в качестве параметра и возвращает `int`.</span><span class="sxs-lookup"><span data-stu-id="02d60-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="02d60-133">Как специальные исключение из правила, что методы не могут быть перегружены типом возвращаемого значения, это можно сделать `op_Explicit` и `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="02d60-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="02d60-134">Перечисляемые типы</span><span class="sxs-lookup"><span data-stu-id="02d60-134">Enumerated Types</span></span>

<span data-ttu-id="02d60-135">`enum` Оператор представляет собой универсальный оператор, принимающий один параметр типа, представляющий тип `enum` для преобразования.</span><span class="sxs-lookup"><span data-stu-id="02d60-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="02d60-136">При преобразовании в перечисляемый тип, алгоритм определения типа пытается определить тип `enum` , требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="02d60-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="02d60-137">В следующем примере переменная `col1` не указан явно, но его тип выводится из более поздней версии тест на равенство.</span><span class="sxs-lookup"><span data-stu-id="02d60-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="02d60-138">Таким образом, компилятор может определить, что при преобразовании к `Color` перечисления.</span><span class="sxs-lookup"><span data-stu-id="02d60-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="02d60-139">Кроме того, можно указывать аннотации типа, как и в `col2` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="02d60-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="02d60-140">Можно также явным образом указать целевой тип перечисления как параметр типа, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="02d60-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="02d60-141">Обратите внимание на то, что перечисление приводит работы только в том случае, если базовый тип перечисления совместима с преобразуемого типа.</span><span class="sxs-lookup"><span data-stu-id="02d60-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="02d60-142">В следующем коде, преобразование завершается неудачей, для компиляции из-за несоответствия между `int32` и `uint32`.</span><span class="sxs-lookup"><span data-stu-id="02d60-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="02d60-143">Дополнительные сведения см. в разделе [перечисления](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="02d60-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="02d60-144">Приведение типов объектов</span><span class="sxs-lookup"><span data-stu-id="02d60-144">Casting Object Types</span></span>

<span data-ttu-id="02d60-145">Преобразование типов в иерархии объектов — это основа для объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="02d60-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="02d60-146">Существует два основных типа преобразований: приведение повышением и понижением приведение.</span><span class="sxs-lookup"><span data-stu-id="02d60-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="02d60-147">Приведение вверх по иерархии означает приведение из производного объекта ссылки на ссылку на базовый объект.</span><span class="sxs-lookup"><span data-stu-id="02d60-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="02d60-148">Такое приведение будет гарантированно работать до тех пор, пока базовый класс находится в иерархии наследования производного класса.</span><span class="sxs-lookup"><span data-stu-id="02d60-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="02d60-149">Приведение с понижением по иерархии из базового объекта ссылки на ссылку производного объекта, завершается успешно только в том случае, если объект фактически является экземпляром типа целевого (производного) или типа, производного от целевого типа.</span><span class="sxs-lookup"><span data-stu-id="02d60-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="02d60-150">F # предоставляет операторы для этих типов преобразований.</span><span class="sxs-lookup"><span data-stu-id="02d60-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="02d60-151">`:>` Оператор приводит вверх по иерархии и `:?>` оператор приводит вниз по иерархии.</span><span class="sxs-lookup"><span data-stu-id="02d60-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="02d60-152">Приведение</span><span class="sxs-lookup"><span data-stu-id="02d60-152">Upcasting</span></span>

<span data-ttu-id="02d60-153">Во многих языках объектно ориентированного приведение является неявным; в F # правила несколько отличаются.</span><span class="sxs-lookup"><span data-stu-id="02d60-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="02d60-154">Приведение применяется автоматически при передаче аргументов к методам на основе типа объекта.</span><span class="sxs-lookup"><span data-stu-id="02d60-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="02d60-155">Тем не менее для функций привязки let в модуле, приведение не выполняется автоматически, если тип параметра не объявлена как гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="02d60-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="02d60-156">Дополнительные сведения см. в разделе [гибкие типы](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="02d60-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="02d60-157">`:>` Оператор выполняет статическое приведение, что означает, что успешность приведения определяется во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="02d60-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="02d60-158">Если приведение с помощью `:>` компилируется успешно, он является допустимым приведения к типу и не существует возможности сбоя во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02d60-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="02d60-159">Можно также использовать `upcast` оператор для выполнения такого преобразования.</span><span class="sxs-lookup"><span data-stu-id="02d60-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="02d60-160">Следующее выражение задает преобразование вверх по иерархии:</span><span class="sxs-lookup"><span data-stu-id="02d60-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="02d60-161">При использовании оператор приведения с повышением, компилятор пытается определить тип, который преобразуется из контекста.</span><span class="sxs-lookup"><span data-stu-id="02d60-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="02d60-162">Если компилятору не удалось определить тип объекта, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="02d60-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="02d60-163">Приведение</span><span class="sxs-lookup"><span data-stu-id="02d60-163">Downcasting</span></span>

<span data-ttu-id="02d60-164">`:?>` Оператор выполняет динамическое приведение, что означает, что успешность приведения определяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02d60-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="02d60-165">Приведение с помощью `:?>` оператор не проверяется во время компиляции; но во время выполнения попытки для приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="02d60-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="02d60-166">Если объект совместим с целевым типом, приведение выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="02d60-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="02d60-167">Если объект не совместим с типом целевого объекта, то среда выполнения вызывает `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="02d60-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="02d60-168">Можно также использовать `downcast` оператор для выполнения преобразования динамического типа.</span><span class="sxs-lookup"><span data-stu-id="02d60-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="02d60-169">Следующее выражение задает преобразование к типу, который выводится из контекста программы вниз по иерархии:</span><span class="sxs-lookup"><span data-stu-id="02d60-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="02d60-170">Как и для `upcast` оператора, если компилятор не может определить целевой тип из контекста, он сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="02d60-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="02d60-171">Следующий код иллюстрирует использование `:>` и `:?>` операторы.</span><span class="sxs-lookup"><span data-stu-id="02d60-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="02d60-172">В коде показано, что `:?>` оператор используется наилучшим образом в том случае, если вы знаете успешное преобразование, так как он создает `InvalidCastException` при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="02d60-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="02d60-173">Если вы не знаете, что преобразование будет успешным, тип теста, который использует `match` выражение лучше, так как позволяет избежать затрат на генерации исключения.</span><span class="sxs-lookup"><span data-stu-id="02d60-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="02d60-174">Поскольку универсальные операторы `downcast` и `upcast` полагаться на определение типа для определения аргументов и возвращаемых типов, в приведенном выше коде, можно заменить</span><span class="sxs-lookup"><span data-stu-id="02d60-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="02d60-175">на</span><span class="sxs-lookup"><span data-stu-id="02d60-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="02d60-176">В предыдущем коде, тип аргумента и возвращаемые типы являются `Derived1` и `Base1`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="02d60-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="02d60-177">Дополнительные сведения о тестировании типов см. в разделе [выражения сопоставления](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="02d60-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02d60-178">См. также</span><span class="sxs-lookup"><span data-stu-id="02d60-178">See also</span></span>

- [<span data-ttu-id="02d60-179">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="02d60-179">F# Language Reference</span></span>](index.md)
