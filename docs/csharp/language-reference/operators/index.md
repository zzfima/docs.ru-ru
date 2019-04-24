---
title: Операторы в C#
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: f4267caeb6301950b9f6a8b9545a47b9f48e7920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977383"
---
# <a name="c-operators"></a><span data-ttu-id="aca85-102">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="aca85-102">C# operators</span></span>

<span data-ttu-id="aca85-103">C# предоставляет множество операторов, которые являются символами, указывающими, какие операции (математические операции, индексирование, вызов функции и т. д.) следует выполнять в выражении.</span><span class="sxs-lookup"><span data-stu-id="aca85-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="aca85-104">Вы можете [перегрузить](../../programming-guide/statements-expressions-operators/overloadable-operators.md) многие операторы, то есть изменить их значение при применении к некоторому пользовательскому типу.</span><span class="sxs-lookup"><span data-stu-id="aca85-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="aca85-105">Обычно для перечислений (`enum`) разрешены все операции, применимые к целочисленным типам (например, `==`, `!=`, `<`, `>`, `&` и `|`).</span><span class="sxs-lookup"><span data-stu-id="aca85-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="aca85-106">В следующих разделах перечислены операторы C# в порядке убывания приоритета.</span><span class="sxs-lookup"><span data-stu-id="aca85-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="aca85-107">Операторы в каждом разделе совместно используют один и тот же уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="aca85-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="aca85-108">Основные операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-108">Primary operators</span></span>

<span data-ttu-id="aca85-109">Это операторы с наивысшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="aca85-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="aca85-110">[x.y](member-access-operator.md) — доступ к членам.</span><span class="sxs-lookup"><span data-stu-id="aca85-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="aca85-111">[x?.y](null-conditional-operators.md) — доступ к членам с проверкой NULL.</span><span class="sxs-lookup"><span data-stu-id="aca85-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="aca85-112">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="aca85-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="aca85-113">[x?[y]](null-conditional-operators.md) — доступ к индексам, определяемый условием NULL.</span><span class="sxs-lookup"><span data-stu-id="aca85-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="aca85-114">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="aca85-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="aca85-115">[f(x)](invocation-operator.md) — вызов функции.</span><span class="sxs-lookup"><span data-stu-id="aca85-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="aca85-116">[a&#91;x&#93;](index-operator.md) — индексирование агрегатного объекта.</span><span class="sxs-lookup"><span data-stu-id="aca85-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="aca85-117">[x++](arithmetic-operators.md#increment-operator-) — постфиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="aca85-118">Возвращает значение x и затем обновляет расположение хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="aca85-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="aca85-119">[x--](arithmetic-operators.md#decrement-operator---) — постфиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="aca85-120">Возвращает значение x и затем обновляет расположение хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="aca85-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="aca85-121">[new](../keywords/new-operator.md) – создание экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="aca85-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="aca85-122">[typeof](../keywords/typeof.md) — возвращает объект <xref:System.Type>, представляющий операнд.</span><span class="sxs-lookup"><span data-stu-id="aca85-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="aca85-123">[checked](../keywords/checked.md) — включает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="aca85-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="aca85-124">[unchecked](../keywords/unchecked.md) — отключает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="aca85-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="aca85-125">Это поведение установлено для компилятора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aca85-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="aca85-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) — создает значение типа T по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aca85-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="aca85-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) — объявляет и возвращает экземпляр делегата.</span><span class="sxs-lookup"><span data-stu-id="aca85-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="aca85-128">[sizeof](../keywords/sizeof.md) — возвращает размер в байтах для типа операнда.</span><span class="sxs-lookup"><span data-stu-id="aca85-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="aca85-129">[->](dereference-operator.md) — разыменование указателя в сочетании с доступом к члену.</span><span class="sxs-lookup"><span data-stu-id="aca85-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="aca85-130">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-130">Unary operators</span></span>

<span data-ttu-id="aca85-131">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-132">[+x](addition-operator.md) — возвращает значение x.</span><span class="sxs-lookup"><span data-stu-id="aca85-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="aca85-133">[-x](subtraction-operator.md) — числовое отрицание.</span><span class="sxs-lookup"><span data-stu-id="aca85-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="aca85-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) — логическое отрицание.</span><span class="sxs-lookup"><span data-stu-id="aca85-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="aca85-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) — поразрядное дополнение.</span><span class="sxs-lookup"><span data-stu-id="aca85-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="aca85-136">[++x](arithmetic-operators.md#increment-operator-) — префиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="aca85-137">Возвращает значение x после обновления расположения хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="aca85-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="aca85-138">[--x](arithmetic-operators.md#decrement-operator---) — префиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="aca85-139">Возвращает значение x после обновления расположения хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="aca85-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="aca85-140">[(T)x](invocation-operator.md) — приведение типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="aca85-141">[await`Task` — ожидание выполнения ](../keywords/await.md).</span><span class="sxs-lookup"><span data-stu-id="aca85-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="aca85-142">[&x](and-operator.md) — получение адреса.</span><span class="sxs-lookup"><span data-stu-id="aca85-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="aca85-143">[\*x](multiplication-operator.md) — разыменование.</span><span class="sxs-lookup"><span data-stu-id="aca85-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

<span data-ttu-id="aca85-144">[Оператор true](../keywords/true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="aca85-144">[true operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="aca85-145">[Оператор false](../keywords/true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="aca85-145">[false operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="aca85-146">Мультипликативные операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-146">Multiplicative operators</span></span>

<span data-ttu-id="aca85-147">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-147">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-148">[x \* y](arithmetic-operators.md#multiplication-operator-) — умножение.</span><span class="sxs-lookup"><span data-stu-id="aca85-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="aca85-149">[x / y](arithmetic-operators.md#division-operator-) — деление.</span><span class="sxs-lookup"><span data-stu-id="aca85-149">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="aca85-150">Если операнды имеют целые числа, результатом является целочисленное значение, усеченное в сторону нуля (например, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="aca85-150">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="aca85-151">[x % y](arithmetic-operators.md#remainder-operator-) — остаток.</span><span class="sxs-lookup"><span data-stu-id="aca85-151">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="aca85-152">Если операнды имеют целые числа, это возвращает остаток от деления x на y.</span><span class="sxs-lookup"><span data-stu-id="aca85-152">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="aca85-153">Если `q = x / y` и `r = x % y`, то `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="aca85-153">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="aca85-154">Аддитивные операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-154">Additive operators</span></span>

<span data-ttu-id="aca85-155">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-155">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-156">[x + y](arithmetic-operators.md#addition-operator-) — сложение.</span><span class="sxs-lookup"><span data-stu-id="aca85-156">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="aca85-157">[x – y](arithmetic-operators.md#subtraction-operator--) — вычитание.</span><span class="sxs-lookup"><span data-stu-id="aca85-157">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="aca85-158">Операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="aca85-158">Shift operators</span></span>

<span data-ttu-id="aca85-159">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-159">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-160">[x <\< y](bitwise-and-shift-operators.md#left-shift-operator-) — сдвиг битов влево и заполнение правого бита нулем.</span><span class="sxs-lookup"><span data-stu-id="aca85-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="aca85-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) — сдвиг битов вправо.</span><span class="sxs-lookup"><span data-stu-id="aca85-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="aca85-162">Если левым операндом является `int` или `long`, затем левые биты заполняются битом знака.</span><span class="sxs-lookup"><span data-stu-id="aca85-162">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="aca85-163">Если левым операндом является `uint` или `ulong`, затем левые биты заполняются нулем.</span><span class="sxs-lookup"><span data-stu-id="aca85-163">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="aca85-164">Относительные операторы и операторы тестирования типа</span><span class="sxs-lookup"><span data-stu-id="aca85-164">Relational and type-testing operators</span></span>

<span data-ttu-id="aca85-165">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-165">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-166">[x \< y](less-than-operator.md) — меньше чем (возвращает true, если x меньше y).</span><span class="sxs-lookup"><span data-stu-id="aca85-166">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="aca85-167">[x > ](greater-than-operator.md) — больше чем (возвращает true, если x больше y).</span><span class="sxs-lookup"><span data-stu-id="aca85-167">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="aca85-168">[x \<= y](less-than-equal-operator.md) – меньше или равно</span><span class="sxs-lookup"><span data-stu-id="aca85-168">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="aca85-169">[x >= y](greater-than-equal-operator.md) – больше или равно.</span><span class="sxs-lookup"><span data-stu-id="aca85-169">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="aca85-170">[is](../keywords/is.md) — совместимость типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-170">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="aca85-171">Возвращает значение true, если вычисленный левый операнд может быть приведен к типу, указанному в правом операнде (статический тип).</span><span class="sxs-lookup"><span data-stu-id="aca85-171">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="aca85-172">[as](../keywords/as.md) — преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-172">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="aca85-173">Возвращает левый операнд, приведенный к типу, заданному правым операндом (статический тип), но `as` возвращает `null`, где `(T)x` вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="aca85-173">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="aca85-174">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="aca85-174">Equality operators</span></span>

<span data-ttu-id="aca85-175">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-175">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-176">[x == y](equality-operators.md#equality-operator-) — тождество.</span><span class="sxs-lookup"><span data-stu-id="aca85-176">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="aca85-177">По умолчанию для ссылочных типов, отличных от `string`, этот оператор возвращает равенство ссылок (проверка удостоверения).</span><span class="sxs-lookup"><span data-stu-id="aca85-177">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="aca85-178">Однако типы могут перегрузить `==`, поэтому если планируется проверять удостоверения, лучше использовать метод `ReferenceEquals` для `object`.</span><span class="sxs-lookup"><span data-stu-id="aca85-178">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="aca85-179">[x != y](equality-operators.md#inequality-operator-) — неравенство.</span><span class="sxs-lookup"><span data-stu-id="aca85-179">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="aca85-180">См. примечание для `==`.</span><span class="sxs-lookup"><span data-stu-id="aca85-180">See comment for `==`.</span></span> <span data-ttu-id="aca85-181">Если тип перегружает `==`, то его необходимо перегрузить `!=`.</span><span class="sxs-lookup"><span data-stu-id="aca85-181">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="aca85-182">Логический оператор AND</span><span class="sxs-lookup"><span data-stu-id="aca85-182">Logical AND operator</span></span>

<span data-ttu-id="aca85-183">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-183">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-184">`x & y` — [логическое И](boolean-logical-operators.md#logical-and-operator-) для операндов `bool` или [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-184">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="aca85-185">Оператор логического исключающего ИЛИ</span><span class="sxs-lookup"><span data-stu-id="aca85-185">Logical XOR operator</span></span>

<span data-ttu-id="aca85-186">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-187">`x ^ y` — [логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) для операндов `bool` или [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-187">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="aca85-188">Логический оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="aca85-188">Logical OR operator</span></span>

<span data-ttu-id="aca85-189">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-190">`x | y` — [логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) для операндов `bool` или [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="aca85-190">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="aca85-191">Условный оператор И</span><span class="sxs-lookup"><span data-stu-id="aca85-191">Conditional AND operator</span></span>

<span data-ttu-id="aca85-192">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) — логическое И.</span><span class="sxs-lookup"><span data-stu-id="aca85-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="aca85-194">Если первый операнд имеет значение false, то C# не вычисляет второй операнд.</span><span class="sxs-lookup"><span data-stu-id="aca85-194">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="aca85-195">Условный оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="aca85-195">Conditional OR operator</span></span>

<span data-ttu-id="aca85-196">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-196">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) — логическое ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="aca85-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="aca85-198">Если первый операнд имеет значение true, то C# не вычисляет второй операнд.</span><span class="sxs-lookup"><span data-stu-id="aca85-198">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="aca85-199">Оператор объединения с NULL</span><span class="sxs-lookup"><span data-stu-id="aca85-199">Null-coalescing operator</span></span>

<span data-ttu-id="aca85-200">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-200">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-201">[x ?? y](null-coalescing-operator.md) — возвращает `x`, если значение отличается от `null`; в противном случае возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="aca85-201">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="aca85-202">Условный оператор</span><span class="sxs-lookup"><span data-stu-id="aca85-202">Conditional operator</span></span>

<span data-ttu-id="aca85-203">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-204">[t ? x : y](conditional-operator.md) — если условие `t` имеет значение true, вычисляет и возвращает `x`, в противном случае вычисляет и возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="aca85-204">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="aca85-205">Назначение и лямбда-операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-205">Assignment and Lambda operators</span></span>

<span data-ttu-id="aca85-206">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="aca85-206">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="aca85-207">[x = y](assignment-operator.md) — назначение.</span><span class="sxs-lookup"><span data-stu-id="aca85-207">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="aca85-208">[x += y](addition-assignment-operator.md) — инкремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-208">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="aca85-209">Добавьте значение `y` к значению `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-209">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="aca85-210">Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# добавляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="aca85-210">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="aca85-211">[x -= y](subtraction-assignment-operator.md) — декремент.</span><span class="sxs-lookup"><span data-stu-id="aca85-211">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="aca85-212">Вычтите значение `y` из значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-212">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="aca85-213">Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# удаляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="aca85-213">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler.</span></span>

<span data-ttu-id="aca85-214">[x \*= y](arithmetic-operators.md#compound-assignment) — назначение с умножением.</span><span class="sxs-lookup"><span data-stu-id="aca85-214">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="aca85-215">Умножьте значение `y` на значение `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-215">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-216">[x /= y](arithmetic-operators.md#compound-assignment) — назначение с делением.</span><span class="sxs-lookup"><span data-stu-id="aca85-216">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="aca85-217">Разделите значение `x` на значение `y`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-217">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-218">[x %= y](arithmetic-operators.md#compound-assignment) — присваивание остатка.</span><span class="sxs-lookup"><span data-stu-id="aca85-218">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="aca85-219">Разделите значение `x` на значение `y`, сохраните остаток в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-219">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-220">[x &= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией И.</span><span class="sxs-lookup"><span data-stu-id="aca85-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="aca85-221">Выполните операцию И для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-221">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="aca85-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="aca85-223">Выполните операцию ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-223">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-224">[x ^= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="aca85-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="aca85-225">Выполните операцию исключающего ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-225">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-226">[x <<= ](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом влево.</span><span class="sxs-lookup"><span data-stu-id="aca85-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="aca85-227">Сдвиньте значение `x` влево на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-227">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом вправо.</span><span class="sxs-lookup"><span data-stu-id="aca85-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="aca85-229">Сдвиньте значение `x` вправо на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="aca85-229">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="aca85-230">[=>](lambda-operator.md) — объявление лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="aca85-230">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="aca85-231">См. также</span><span class="sxs-lookup"><span data-stu-id="aca85-231">See also</span></span>

- [<span data-ttu-id="aca85-232">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="aca85-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="aca85-233">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="aca85-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="aca85-234">C#</span><span class="sxs-lookup"><span data-stu-id="aca85-234">C#</span></span>](../../index.md)
- [<span data-ttu-id="aca85-235">Перегружаемые операторы</span><span class="sxs-lookup"><span data-stu-id="aca85-235">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="aca85-236">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="aca85-236">C# Keywords</span></span>](../keywords/index.md)
