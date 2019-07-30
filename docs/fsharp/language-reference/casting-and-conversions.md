---
title: Приведение и преобразование
description: Узнайте, F# как язык программирования предоставляет операторы преобразования для арифметических преобразований между различными типами-примитивами.
ms.date: 05/16/2016
ms.openlocfilehash: ee4df588caabf58c7b9e18961e217ef8f15fcf93
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630437"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="44154-103">Приведение и преобразование (F#)</span><span class="sxs-lookup"><span data-stu-id="44154-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="44154-104">В этом разделе описывается поддержка преобразований типов F#в.</span><span class="sxs-lookup"><span data-stu-id="44154-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="44154-105">Арифметические типы</span><span class="sxs-lookup"><span data-stu-id="44154-105">Arithmetic Types</span></span>

<span data-ttu-id="44154-106">F#предоставляет операторы преобразования для арифметических преобразований между различными типами-примитивами, такими как целочисленные и плавающие точки.</span><span class="sxs-lookup"><span data-stu-id="44154-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="44154-107">Операторы целочисленного и символьного преобразования имеют проверенные и непроверенные формы; Операторы с плавающей точкой и `enum` оператор преобразования не имеют значения.</span><span class="sxs-lookup"><span data-stu-id="44154-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="44154-108">Непроверенные формы определяются в `Microsoft.FSharp.Core.Operators` , а проверенные формы определяются в. `Microsoft.FSharp.Core.Operators.Checked`</span><span class="sxs-lookup"><span data-stu-id="44154-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="44154-109">Проверенная форма проверяет наличие переполнения и создает исключение во время выполнения, если полученное значение превышает ограничения целевого типа.</span><span class="sxs-lookup"><span data-stu-id="44154-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="44154-110">Имя каждого из этих операторов совпадает с именем целевого типа.</span><span class="sxs-lookup"><span data-stu-id="44154-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="44154-111">Например, в следующем коде, в котором типы помечены явно, `byte` отображаются с двумя разными значениями.</span><span class="sxs-lookup"><span data-stu-id="44154-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="44154-112">Первое вхождение — это тип, а второй — оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="44154-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="44154-113">В следующей таблице показаны операторы преобразования, определенные F#в.</span><span class="sxs-lookup"><span data-stu-id="44154-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="44154-114">Оператор</span><span class="sxs-lookup"><span data-stu-id="44154-114">Operator</span></span>|<span data-ttu-id="44154-115">Описание</span><span class="sxs-lookup"><span data-stu-id="44154-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="44154-116">Преобразование в Byte, 8-разрядный тип без знака.</span><span class="sxs-lookup"><span data-stu-id="44154-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="44154-117">Преобразовать в байт со знаком.</span><span class="sxs-lookup"><span data-stu-id="44154-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="44154-118">Преобразует в 16-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="44154-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="44154-119">Преобразование в 16-битовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="44154-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="44154-120">Преобразование в 32-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="44154-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="44154-121">Преобразование в 32-битовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="44154-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="44154-122">Преобразование в 64-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="44154-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="44154-123">Преобразование в 64-битовое целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="44154-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="44154-124">Преобразовать в собственное целое число.</span><span class="sxs-lookup"><span data-stu-id="44154-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="44154-125">Преобразование в собственное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="44154-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="44154-126">Преобразование в 64-разрядное число с плавающей запятой двойной точности (Double).</span><span class="sxs-lookup"><span data-stu-id="44154-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="44154-127">Преобразование в 32-разрядное число с плавающей запятой одиночной точности (однозначная).</span><span class="sxs-lookup"><span data-stu-id="44154-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="44154-128">Преобразовать в `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="44154-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="44154-129">Преобразование в `System.Char`символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="44154-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="44154-130">Преобразование в перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="44154-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="44154-131">Помимо встроенных типов-примитивов, эти операторы можно использовать с типами, которые реализуют `op_Explicit` методы `op_Implicit` или с соответствующими сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="44154-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="44154-132">Например, `int` оператор преобразования работает с любым типом, предоставляющим статический метод `op_Explicit` , который принимает тип в качестве параметра и возвращает `int`.</span><span class="sxs-lookup"><span data-stu-id="44154-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="44154-133">В качестве специального исключения для общего правила, которое методы не могут перегружаться типом возвращаемого значения, это можно сделать для `op_Explicit` и `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="44154-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="44154-134">Перечислимые типы</span><span class="sxs-lookup"><span data-stu-id="44154-134">Enumerated Types</span></span>

<span data-ttu-id="44154-135">Оператор является универсальным оператором, принимающим один параметр типа, представляющий тип `enum` преобразуемого объекта. `enum`</span><span class="sxs-lookup"><span data-stu-id="44154-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="44154-136">При преобразовании в перечислимый тип определение типа пытается определить тип `enum` объекта, в который необходимо выполнить преобразование.</span><span class="sxs-lookup"><span data-stu-id="44154-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="44154-137">В следующем примере переменная `col1` не объявляется явно, но ее тип выводится из более поздней проверки на равенство.</span><span class="sxs-lookup"><span data-stu-id="44154-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="44154-138">Таким образом, компилятор может вывести на себя `Color` преобразование в перечисление.</span><span class="sxs-lookup"><span data-stu-id="44154-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="44154-139">Кроме того, можно указать аннотацию типа, как `col2` показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="44154-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="44154-140">Можно также явно указать целевой тип перечисления в качестве параметра типа, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="44154-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="44154-141">Обратите внимание, что приведенные перечисления работают только в том случае, если базовый тип перечисления совместим с преобразуемым типом.</span><span class="sxs-lookup"><span data-stu-id="44154-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="44154-142">В следующем коде не удается скомпилировать преобразование из-за несоответствия между `int32` и. `uint32`</span><span class="sxs-lookup"><span data-stu-id="44154-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="44154-143">Дополнительные сведения см. в разделе [перечисления](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="44154-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="44154-144">Приведение типов объектов</span><span class="sxs-lookup"><span data-stu-id="44154-144">Casting Object Types</span></span>

<span data-ttu-id="44154-145">Преобразование между типами в иерархии объектов является фундаментальным для объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="44154-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="44154-146">Существует два базовых типа преобразований: приведение к исполнению (исходящее) и приведение вниз (образование производных).</span><span class="sxs-lookup"><span data-stu-id="44154-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="44154-147">Приведение вверх по иерархии означает приведение производного объекта к ссылке на базовый объект.</span><span class="sxs-lookup"><span data-stu-id="44154-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="44154-148">Такое приведение гарантированно будет работать, если базовый класс находится в иерархии наследования производного класса.</span><span class="sxs-lookup"><span data-stu-id="44154-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="44154-149">Приведение вниз к иерархии из базового объекта в ссылку на производный объект завершается, только если объект фактически является экземпляром правильного (производного) типа или типа, производного от целевого типа.</span><span class="sxs-lookup"><span data-stu-id="44154-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="44154-150">F#предоставляет операторы для таких типов преобразований.</span><span class="sxs-lookup"><span data-stu-id="44154-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="44154-151">Оператор выполняет приведение к иерархии вверх, `:?>` и оператор приводит вниз к иерархии. `:>`</span><span class="sxs-lookup"><span data-stu-id="44154-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="44154-152">Treat</span><span class="sxs-lookup"><span data-stu-id="44154-152">Upcasting</span></span>

<span data-ttu-id="44154-153">Во многих объектно-ориентированных языках приведение является неявным; в F#правила отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="44154-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="44154-154">При передаче аргументов в методы в типе объекта применяется автоматическое приведение.</span><span class="sxs-lookup"><span data-stu-id="44154-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="44154-155">Однако для функций, связанных с let, в модуле не выполняется автоматическое приведение, если тип параметра не объявлен как гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="44154-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="44154-156">Дополнительные сведения см. в разделе [гибкие типы](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="44154-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="44154-157">`:>` Оператор выполняет статическое приведение, которое означает, что успешность приведения определяется во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="44154-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="44154-158">Если приведение, использующее `:>` компиляцию, успешно выполняется, оно является допустимым приведением и не имеет шансов на ошибку во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="44154-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="44154-159">Можно также использовать `upcast` оператор для выполнения такого преобразования.</span><span class="sxs-lookup"><span data-stu-id="44154-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="44154-160">Следующее выражение задает преобразование в иерархию:</span><span class="sxs-lookup"><span data-stu-id="44154-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="44154-161">При использовании оператора CAST компилятор пытается определить тип, к которому выполняется преобразование, из контекста.</span><span class="sxs-lookup"><span data-stu-id="44154-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="44154-162">Если компилятору не удается определить тип целевого объекта, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="44154-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="44154-163">Опуститься</span><span class="sxs-lookup"><span data-stu-id="44154-163">Downcasting</span></span>

<span data-ttu-id="44154-164">`:?>` Оператор выполняет динамическое приведение, то есть успешность приведения определяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="44154-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="44154-165">Приведение, использующее `:?>` оператор, не проверяется во время компиляции, но во время выполнения предпринимается попытка приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="44154-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="44154-166">Если объект совместим с целевым типом, приведение будет выполняться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="44154-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="44154-167">Если объект несовместим с целевым типом, среда выполнения создает исключение `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="44154-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="44154-168">`downcast` Оператор также можно использовать для выполнения динамического преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="44154-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="44154-169">Следующее выражение задает преобразование иерархии в тип, выводимый из контекста программы:</span><span class="sxs-lookup"><span data-stu-id="44154-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="44154-170">Как и для `upcast` оператора, если компилятор не может вывести конкретный целевой тип из контекста, он сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="44154-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="44154-171">В следующем коде показано использование `:>` операторов и. `:?>`</span><span class="sxs-lookup"><span data-stu-id="44154-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="44154-172">Этот код показывает, что `:?>` оператор лучше использовать, если известно, что преобразование будет успешным, так как при `InvalidCastException` неудачном завершении преобразование вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="44154-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="44154-173">Если неизвестно, что преобразование будет выполнено, то тест типа, использующий `match` выражение, лучше, так как он позволяет избежать издержек, вызванных созданием исключения.</span><span class="sxs-lookup"><span data-stu-id="44154-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="44154-174">Поскольку универсальные `downcast` операторы `upcast` и полагаются на определение типа для определения аргумента и типа возвращаемого значения, в приведенном выше коде можно заменить</span><span class="sxs-lookup"><span data-stu-id="44154-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="44154-175">на</span><span class="sxs-lookup"><span data-stu-id="44154-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="44154-176">В приведенном выше коде тип аргумента и возвращаемые типы `Derived1` имеют `Base1`значение и соответственно.</span><span class="sxs-lookup"><span data-stu-id="44154-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="44154-177">Дополнительные сведения о типах тестов см. в разделе [выражения Match](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="44154-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44154-178">См. также</span><span class="sxs-lookup"><span data-stu-id="44154-178">See also</span></span>

- [<span data-ttu-id="44154-179">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="44154-179">F# Language Reference</span></span>](index.md)
