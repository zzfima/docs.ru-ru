---
title: Приведение и преобразование (F#)
description: 'Узнайте, как на языке программирования F # предоставляет операторы преобразования для преобразования между различными типами-примитивами.'
keywords: visual f#, f#, функциональное программирование
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: df8352b0dd8651f1480515311454a218ea79b971
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="63f59-104">Приведение и преобразование (F#)</span><span class="sxs-lookup"><span data-stu-id="63f59-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="63f59-105">В этом разделе описывается поддержка преобразований типов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="63f59-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="63f59-106">Арифметические типы</span><span class="sxs-lookup"><span data-stu-id="63f59-106">Arithmetic Types</span></span>
<span data-ttu-id="63f59-107">F # предоставляет операторы преобразования для преобразования между различными типами-примитивами, например между целое число и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="63f59-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="63f59-108">Операторы преобразования целочисленным типом и char проверили и непроверяемые формы; значение с плавающей запятой операторы и `enum` оператор преобразования — нет.</span><span class="sxs-lookup"><span data-stu-id="63f59-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="63f59-109">Снят флажок формы определяются в `Microsoft.FSharp.Core.Operators` и проверенные формы определяются в `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="63f59-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="63f59-110">Проверяемые на переполнение и создавать исключение времени выполнения, если результирующее значение нарушает ограничения типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="63f59-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="63f59-111">Каждый из этих операторов имеет имя, совпадающее с именем имя конечного типа.</span><span class="sxs-lookup"><span data-stu-id="63f59-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="63f59-112">Например, в следующем коде с явно указанными типами слово `byte` имеет два значения.</span><span class="sxs-lookup"><span data-stu-id="63f59-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="63f59-113">Первое вхождение является типом, а второй — оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="63f59-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="63f59-114">В следующей таблице показаны операторы преобразования, определенные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="63f59-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="63f59-115">Оператор</span><span class="sxs-lookup"><span data-stu-id="63f59-115">Operator</span></span>|<span data-ttu-id="63f59-116">Описание</span><span class="sxs-lookup"><span data-stu-id="63f59-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="63f59-117">Преобразуйте в тип byte, 8-разрядного беззнакового типа.</span><span class="sxs-lookup"><span data-stu-id="63f59-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="63f59-118">Преобразуйте байт со знаком.</span><span class="sxs-lookup"><span data-stu-id="63f59-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="63f59-119">Преобразуйте в 16-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="63f59-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="63f59-120">Преобразуйте в 16-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="63f59-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="63f59-121">Преобразуйте в 32-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="63f59-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="63f59-122">Преобразуйте в 32-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="63f59-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="63f59-123">Преобразуйте в 64-разрядное целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="63f59-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="63f59-124">Преобразуйте в 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="63f59-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="63f59-125">Преобразуйте в машинном коде целое число.</span><span class="sxs-lookup"><span data-stu-id="63f59-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="63f59-126">Преобразуйте в машинном коде целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="63f59-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="63f59-127">Преобразование в стандарт IEEE двойной точности 64-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="63f59-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="63f59-128">Преобразование в стандарт IEEE одинарной точности 32-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="63f59-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="63f59-129">Преобразовать в `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63f59-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="63f59-130">Преобразовать в `System.Char`, символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="63f59-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="63f59-131">Преобразуйте в перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="63f59-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="63f59-132">Помимо встроенных примитивных типов, эти операторы можно использовать с типами, реализующими `op_Explicit` или `op_Implicit` методы с подходящими сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="63f59-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="63f59-133">Например `int` оператор преобразования работает с любым типом, который предоставляет статический метод `op_Explicit` , принимает этот тип в качестве параметра и возвращает `int`.</span><span class="sxs-lookup"><span data-stu-id="63f59-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="63f59-134">В качестве особого исключения из правила, что методы не могут быть перегружены тип возвращаемого значения, это можно сделать `op_Explicit` и `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="63f59-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="63f59-135">Перечисляемые типы</span><span class="sxs-lookup"><span data-stu-id="63f59-135">Enumerated Types</span></span>
<span data-ttu-id="63f59-136">`enum` Является универсальный оператор, принимающий один параметр типа, представляющий тип `enum` для преобразования.</span><span class="sxs-lookup"><span data-stu-id="63f59-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="63f59-137">При преобразовании в перечисляемый тип алгоритм определения типа пытается определить тип `enum` , необходимо преобразовать.</span><span class="sxs-lookup"><span data-stu-id="63f59-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="63f59-138">В следующем примере переменная `col1` не указан явно, но его тип выводится из более поздней версии проверку равенства.</span><span class="sxs-lookup"><span data-stu-id="63f59-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="63f59-139">Таким образом, компилятор может определить, что перевод `Color` перечисления.</span><span class="sxs-lookup"><span data-stu-id="63f59-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="63f59-140">Кроме того, можно указывать аннотации типа, как и в `col2` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63f59-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="63f59-141">Можно также явно задать целевой тип перечисления как параметр типа, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="63f59-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="63f59-142">Обратите внимание, что перечисление приводит работы только в том случае, если базовый тип перечисления является совместимым с преобразуемого типа.</span><span class="sxs-lookup"><span data-stu-id="63f59-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="63f59-143">В следующем коде преобразование вызывает ошибку при компиляции из-за несоответствия между `int32` и `uint32`.</span><span class="sxs-lookup"><span data-stu-id="63f59-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="63f59-144">Дополнительные сведения см. в разделе [перечисления](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="63f59-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="63f59-145">Приведение типов объектов</span><span class="sxs-lookup"><span data-stu-id="63f59-145">Casting Object Types</span></span>
<span data-ttu-id="63f59-146">Преобразование между типами в иерархии объектов — это основа для объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="63f59-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="63f59-147">Существует два основных типа преобразования: приведение с повышением и приведение с понижением.</span><span class="sxs-lookup"><span data-stu-id="63f59-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="63f59-148">Приведение с повышением по иерархии означает приведение из производного объекта ссылку на ссылку на базовый объект.</span><span class="sxs-lookup"><span data-stu-id="63f59-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="63f59-149">Такое приведение будет работать гарантированно при условии, что базовый класс находится в иерархии наследования производного класса.</span><span class="sxs-lookup"><span data-stu-id="63f59-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="63f59-150">Приведение с понижением по иерархии из базового объекта ссылку на ссылку на объект производного, завершается успешно только в том случае, если объект является экземпляром целевого (производного) типа или типа, производного от типа назначения.</span><span class="sxs-lookup"><span data-stu-id="63f59-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="63f59-151">F # предоставляет операторы для этих типах преобразования.</span><span class="sxs-lookup"><span data-stu-id="63f59-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="63f59-152">`:>` Оператор приводит вверх по иерархии и `:?>` оператор приводит вниз по иерархии.</span><span class="sxs-lookup"><span data-stu-id="63f59-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="63f59-153">Приведение</span><span class="sxs-lookup"><span data-stu-id="63f59-153">Upcasting</span></span>
<span data-ttu-id="63f59-154">Во многих языках объектно ориентированного восходящее преобразование происходит неявно; в языке F # правила несколько отличаются.</span><span class="sxs-lookup"><span data-stu-id="63f59-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="63f59-155">Приведение применяется автоматически при передаче аргументов методов на основе типа объекта.</span><span class="sxs-lookup"><span data-stu-id="63f59-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="63f59-156">Однако для функций привязки let в модуле, приведение не выполняется автоматически, если тип параметра не объявлена как гибкий тип.</span><span class="sxs-lookup"><span data-stu-id="63f59-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="63f59-157">Дополнительные сведения см. в разделе [гибкие типы](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="63f59-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="63f59-158">`:>` Оператор выполняет статическое приведение, это означает, что успешность приведения определяется во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="63f59-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="63f59-159">Если приведение с помощью `:>` компиляцию, он является допустимым приведения и имеет вероятность сбоя во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="63f59-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="63f59-160">Можно также использовать `upcast` оператор для выполнения такого преобразования.</span><span class="sxs-lookup"><span data-stu-id="63f59-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="63f59-161">Следующее выражение задает преобразование вверх по иерархии:</span><span class="sxs-lookup"><span data-stu-id="63f59-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="63f59-162">При использовании оператора приведения с повышением, компилятор пытается определить нужный тип преобразуемых из контекста.</span><span class="sxs-lookup"><span data-stu-id="63f59-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="63f59-163">Если компилятор не может определить тип объекта, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="63f59-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="63f59-164">Приведение</span><span class="sxs-lookup"><span data-stu-id="63f59-164">Downcasting</span></span>
<span data-ttu-id="63f59-165">`:?>` Оператор выполняет динамическое приведение, это означает, что успешность приведения определяется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="63f59-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="63f59-166">Приведение с помощью `:?>` оператор не проверяется во время компиляции; Однако во время выполнения будет предпринята попытка привести к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="63f59-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="63f59-167">Если объект совместим с целевым типом, приведение завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="63f59-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="63f59-168">Если объект не совместим с типом целевого объекта, среда выполнения вызывает `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="63f59-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="63f59-169">Можно также использовать `downcast` оператор для преобразования динамического типа.</span><span class="sxs-lookup"><span data-stu-id="63f59-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="63f59-170">Следующее выражение задает преобразование к типу, определяемому по контексту программы вниз по иерархии:</span><span class="sxs-lookup"><span data-stu-id="63f59-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="63f59-171">Как для `upcast` оператор, если компилятор не может определить целевой тип из контекста, появляется сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="63f59-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="63f59-172">Следующий код иллюстрирует использование `:>` и `:?>` операторы.</span><span class="sxs-lookup"><span data-stu-id="63f59-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="63f59-173">Код показывает, что `:?>` оператор лучше всего использовать, если известно, преобразование завершится успешно, так как он создает `InvalidCastException` при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="63f59-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="63f59-174">Если вы не знаете, что преобразование будет выполнено успешно, тип теста, который использует `match` выражение лучше, так как позволяет избежать издержек создания исключения.</span><span class="sxs-lookup"><span data-stu-id="63f59-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="63f59-175">Поскольку универсальные операторы `downcast` и `upcast` полагаться на определение типа для определения типа аргументов и возвращаемых в приведенном выше коде, можно заменить</span><span class="sxs-lookup"><span data-stu-id="63f59-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="63f59-176">на</span><span class="sxs-lookup"><span data-stu-id="63f59-176">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="63f59-177">В приведенном выше коде тип аргумента и типы возвращаемых значений являются `Derived1` и `Base1`соответственно.</span><span class="sxs-lookup"><span data-stu-id="63f59-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="63f59-178">Дополнительные сведения о тестировании типов см. в разделе [выражениях сопоставления](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63f59-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63f59-179">См. также</span><span class="sxs-lookup"><span data-stu-id="63f59-179">See Also</span></span>
[<span data-ttu-id="63f59-180">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="63f59-180">F# Language Reference</span></span>](index.md)
