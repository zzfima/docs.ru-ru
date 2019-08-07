---
title: Операторы C# — справочник по C#
ms.date: 04/30/2019
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
ms.openlocfilehash: bc5e2c88314c2f590aeddcfd37bd04c3a7400804
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796477"
---
# <a name="c-operators-c-reference"></a><span data-ttu-id="927db-102">Операторы C# (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="927db-102">C# operators (C# reference)</span></span>

<span data-ttu-id="927db-103">C# предоставляет ряд стандартных операторов, поддерживаемых встроенными типами.</span><span class="sxs-lookup"><span data-stu-id="927db-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="927db-104">Например [арифметические операторы](arithmetic-operators.md) выполняют арифметические операции с операндами встроенных числовых типов, а [логические операторы](boolean-logical-operators.md) выполняют логические операции с операндами [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="927db-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="927db-105">Определяемый пользователем тип может перегружать некоторые операторы для определения соответствующего поведения операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="927db-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="927db-106">Для получения дополнительной информации см. раздел [Перегрузка операторов](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="927db-106">For more information, see [Operator overloading](operator-overloading.md).</span></span>

<span data-ttu-id="927db-107">В следующих разделах перечислены операторы C# в порядке убывания приоритета.</span><span class="sxs-lookup"><span data-stu-id="927db-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="927db-108">Операторы в каждом разделе совместно используют один и тот же уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="927db-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="927db-109">Основные операторы</span><span class="sxs-lookup"><span data-stu-id="927db-109">Primary operators</span></span>

<span data-ttu-id="927db-110">Это операторы с наивысшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="927db-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="927db-111">[x.y](member-access-operators.md#member-access-operator-) — доступ к членам.</span><span class="sxs-lookup"><span data-stu-id="927db-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="927db-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) — доступ к членам с проверкой NULL.</span><span class="sxs-lookup"><span data-stu-id="927db-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="927db-113">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="927db-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="927db-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) — условный доступ к элементу массива или индексатору типов со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="927db-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="927db-115">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="927db-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="927db-116">[f(x)](member-access-operators.md#invocation-operator-) — вызов метода или делегата.</span><span class="sxs-lookup"><span data-stu-id="927db-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="927db-117">[&#91;x&#93; ](member-access-operators.md#indexer-operator-) — доступ к элементу массива или индексатору типов.</span><span class="sxs-lookup"><span data-stu-id="927db-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="927db-118">[x++](arithmetic-operators.md#increment-operator-) — постфиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="927db-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="927db-119">Возвращает значение x и затем обновляет расположение хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="927db-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="927db-120">[x--](arithmetic-operators.md#decrement-operator---) — постфиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="927db-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="927db-121">Возвращает значение x и затем обновляет расположение хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="927db-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="927db-122">[new](new-operator.md) – создание экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="927db-122">[new](new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="927db-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) — возвращает объект <xref:System.Type>, представляющий операнд.</span><span class="sxs-lookup"><span data-stu-id="927db-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="927db-124">[checked](../keywords/checked.md) — включает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="927db-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="927db-125">[unchecked](../keywords/unchecked.md) — отключает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="927db-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="927db-126">Это поведение установлено для компилятора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="927db-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="927db-127">[default(T)](default.md) — создает значение типа T по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="927db-127">[default(T)](default.md) – produces the default value of type T.</span></span>

<span data-ttu-id="927db-128">[nameof](nameof.md) — используется для получения простого (неполного) имени переменной, типа или члена в виде строковой константы.</span><span class="sxs-lookup"><span data-stu-id="927db-128">[nameof](nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="927db-129">[delegate](delegate-operator.md) — объявляет и возвращает экземпляр делегата.</span><span class="sxs-lookup"><span data-stu-id="927db-129">[delegate](delegate-operator.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="927db-130">[sizeof](sizeof.md) — возвращает размер в байтах для типа операнда.</span><span class="sxs-lookup"><span data-stu-id="927db-130">[sizeof](sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="927db-131">[stackalloc](stackalloc.md) — выделяет блок памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="927db-131">[stackalloc](stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="927db-132">[->](pointer-related-operators.md#pointer-member-access-operator--) — косвенное обращение к указателю в сочетании с доступом к члену.</span><span class="sxs-lookup"><span data-stu-id="927db-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="927db-133">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="927db-133">Unary operators</span></span>

<span data-ttu-id="927db-134">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-135">[+x](addition-operator.md) — возвращает значение x.</span><span class="sxs-lookup"><span data-stu-id="927db-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="927db-136">[-x](subtraction-operator.md) — числовое отрицание.</span><span class="sxs-lookup"><span data-stu-id="927db-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="927db-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) — логическое отрицание.</span><span class="sxs-lookup"><span data-stu-id="927db-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="927db-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) — поразрядное дополнение.</span><span class="sxs-lookup"><span data-stu-id="927db-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="927db-139">[++x](arithmetic-operators.md#increment-operator-) — префиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="927db-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="927db-140">Возвращает значение x после обновления расположения хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="927db-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="927db-141">[--x](arithmetic-operators.md#decrement-operator---) — префиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="927db-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="927db-142">Возвращает значение x после обновления расположения хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="927db-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="927db-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) — приведение типов.</span><span class="sxs-lookup"><span data-stu-id="927db-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – type casting.</span></span>

<span data-ttu-id="927db-144">[await`Task` — ожидание выполнения ](../keywords/await.md).</span><span class="sxs-lookup"><span data-stu-id="927db-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="927db-145">[&x](pointer-related-operators.md#address-of-operator-) — адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="927db-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="927db-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) — косвенное обращение к указателю или разыменование.</span><span class="sxs-lookup"><span data-stu-id="927db-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="927db-147">[Оператор true](true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="927db-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="927db-148">[Оператор false](true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="927db-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="927db-149">Мультипликативные операторы</span><span class="sxs-lookup"><span data-stu-id="927db-149">Multiplicative operators</span></span>

<span data-ttu-id="927db-150">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-151">[x \* y](arithmetic-operators.md#multiplication-operator-) — умножение.</span><span class="sxs-lookup"><span data-stu-id="927db-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="927db-152">[x / y](arithmetic-operators.md#division-operator-) — деление.</span><span class="sxs-lookup"><span data-stu-id="927db-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="927db-153">Если операнды имеют целые числа, результатом является целочисленное значение, усеченное в сторону нуля (например, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="927db-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="927db-154">[x % y](arithmetic-operators.md#remainder-operator-) — остаток.</span><span class="sxs-lookup"><span data-stu-id="927db-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="927db-155">Если операнды имеют целые числа, это возвращает остаток от деления x на y.</span><span class="sxs-lookup"><span data-stu-id="927db-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="927db-156">Если `q = x / y` и `r = x % y`, то `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="927db-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="927db-157">Аддитивные операторы</span><span class="sxs-lookup"><span data-stu-id="927db-157">Additive operators</span></span>

<span data-ttu-id="927db-158">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-159">[x + y](arithmetic-operators.md#addition-operator-) — сложение.</span><span class="sxs-lookup"><span data-stu-id="927db-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="927db-160">[x – y](arithmetic-operators.md#subtraction-operator--) — вычитание.</span><span class="sxs-lookup"><span data-stu-id="927db-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="927db-161">Операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="927db-161">Shift operators</span></span>

<span data-ttu-id="927db-162">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-163">[x <\< y](bitwise-and-shift-operators.md#left-shift-operator-) — сдвиг битов влево и заполнение правого бита нулем.</span><span class="sxs-lookup"><span data-stu-id="927db-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="927db-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) — сдвиг битов вправо.</span><span class="sxs-lookup"><span data-stu-id="927db-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="927db-165">Если левым операндом является `int` или `long`, затем левые биты заполняются битом знака.</span><span class="sxs-lookup"><span data-stu-id="927db-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="927db-166">Если левым операндом является `uint` или `ulong`, затем левые биты заполняются нулем.</span><span class="sxs-lookup"><span data-stu-id="927db-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="927db-167">Относительные операторы и операторы тестирования типа</span><span class="sxs-lookup"><span data-stu-id="927db-167">Relational and type-testing operators</span></span>

<span data-ttu-id="927db-168">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-169">[x \< y](comparison-operators.md#less-than-operator-) — меньше чем (возвращает true, если x меньше y).</span><span class="sxs-lookup"><span data-stu-id="927db-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="927db-170">[x > ](comparison-operators.md#greater-than-operator-) — больше чем (возвращает true, если x больше y).</span><span class="sxs-lookup"><span data-stu-id="927db-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="927db-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – меньше или равно</span><span class="sxs-lookup"><span data-stu-id="927db-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="927db-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – больше или равно.</span><span class="sxs-lookup"><span data-stu-id="927db-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="927db-173">[is](type-testing-and-conversion-operators.md#is-operator) — совместимость типов.</span><span class="sxs-lookup"><span data-stu-id="927db-173">[is](type-testing-and-conversion-operators.md#is-operator) – type compatibility.</span></span> <span data-ttu-id="927db-174">Возвращает значение `true`, если вычисленный левый операнд может быть приведен к типу, заданному правым операндом.</span><span class="sxs-lookup"><span data-stu-id="927db-174">Returns `true` if the evaluated left operand can be cast to the type specified by the right operand.</span></span>

<span data-ttu-id="927db-175">[as](type-testing-and-conversion-operators.md#as-operator) — преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="927db-175">[as](type-testing-and-conversion-operators.md#as-operator) – type conversion.</span></span> <span data-ttu-id="927db-176">Возвращает левый операнд, приведенный к типу, заданному правым операндом, но `as` возвращает `null`, где `(T)x` вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="927db-176">Returns the left operand cast to the type specified by the right operand, but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="927db-177">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="927db-177">Equality operators</span></span>

<span data-ttu-id="927db-178">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-179">[x == y](equality-operators.md#equality-operator-) — тождество.</span><span class="sxs-lookup"><span data-stu-id="927db-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="927db-180">По умолчанию для ссылочных типов, отличных от `string`, этот оператор возвращает равенство ссылок (проверка удостоверения).</span><span class="sxs-lookup"><span data-stu-id="927db-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="927db-181">Однако типы могут перегрузить `==`, поэтому если планируется проверять удостоверения, лучше использовать метод `ReferenceEquals` для `object`.</span><span class="sxs-lookup"><span data-stu-id="927db-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="927db-182">[x != y](equality-operators.md#inequality-operator-) — неравенство.</span><span class="sxs-lookup"><span data-stu-id="927db-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="927db-183">См. примечание для `==`.</span><span class="sxs-lookup"><span data-stu-id="927db-183">See comment for `==`.</span></span> <span data-ttu-id="927db-184">Если тип перегружает `==`, то его необходимо перегрузить `!=`.</span><span class="sxs-lookup"><span data-stu-id="927db-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="927db-185">Логический оператор AND</span><span class="sxs-lookup"><span data-stu-id="927db-185">Logical AND operator</span></span>

<span data-ttu-id="927db-186">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-187">`x & y` — [логическое И](boolean-logical-operators.md#logical-and-operator-) для операндов `bool` или [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="927db-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="927db-188">Оператор логического исключающего ИЛИ</span><span class="sxs-lookup"><span data-stu-id="927db-188">Logical XOR operator</span></span>

<span data-ttu-id="927db-189">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-190">`x ^ y` — [логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) для операндов `bool` или [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="927db-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="927db-191">Логический оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="927db-191">Logical OR operator</span></span>

<span data-ttu-id="927db-192">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-193">`x | y` — [логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) для операндов `bool` или [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) для операндов целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="927db-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="927db-194">Условный оператор И</span><span class="sxs-lookup"><span data-stu-id="927db-194">Conditional AND operator</span></span>

<span data-ttu-id="927db-195">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) — логическое И.</span><span class="sxs-lookup"><span data-stu-id="927db-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="927db-197">Если `x` имеет значение `false`, тогда `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="927db-197">If `x` evaluates to `false`, then `y` is not evaluated.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="927db-198">Условный оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="927db-198">Conditional OR operator</span></span>

<span data-ttu-id="927db-199">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) — логическое ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="927db-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="927db-201">Если `x` имеет значение `true`, тогда `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="927db-201">If `x` evaluates to `true`, then `y` is not evaluated.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="927db-202">Оператор объединения с NULL</span><span class="sxs-lookup"><span data-stu-id="927db-202">Null-coalescing operator</span></span>

<span data-ttu-id="927db-203">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-204">[x ?? y](null-coalescing-operator.md) — возвращает `x`, если значение отличается от `null`; в противном случае возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="927db-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="927db-205">Условный оператор</span><span class="sxs-lookup"><span data-stu-id="927db-205">Conditional operator</span></span>

<span data-ttu-id="927db-206">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-207">[t ? x : y](conditional-operator.md) — если условие `t` имеет значение true, вычисляет и возвращает `x`, в противном случае вычисляет и возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="927db-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="927db-208">Операторы назначения и лямбда-операторы</span><span class="sxs-lookup"><span data-stu-id="927db-208">Assignment and lambda operators</span></span>

<span data-ttu-id="927db-209">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="927db-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="927db-210">[x = y](assignment-operator.md) — назначение.</span><span class="sxs-lookup"><span data-stu-id="927db-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="927db-211">[x += y](arithmetic-operators.md#compound-assignment) — инкремент.</span><span class="sxs-lookup"><span data-stu-id="927db-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="927db-212">Добавьте значение `y` к значению `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="927db-213">Если `x` назначает [событие](../keywords/event.md), то `y` должен быть соответствующим методом, который C# добавляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="927db-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="927db-214">[x -= y](arithmetic-operators.md#compound-assignment) — декремент.</span><span class="sxs-lookup"><span data-stu-id="927db-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="927db-215">Вычтите значение `y` из значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="927db-216">Если `x` назначает [событие](../keywords/event.md), то `y` должен быть соответствующим методом, который C# удаляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="927db-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="927db-217">[x \*= y](arithmetic-operators.md#compound-assignment) — назначение с умножением.</span><span class="sxs-lookup"><span data-stu-id="927db-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="927db-218">Умножьте значение `y` на значение `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-219">[x /= y](arithmetic-operators.md#compound-assignment) — назначение с делением.</span><span class="sxs-lookup"><span data-stu-id="927db-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="927db-220">Разделите значение `x` на значение `y`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-221">[x %= y](arithmetic-operators.md#compound-assignment) — присваивание остатка.</span><span class="sxs-lookup"><span data-stu-id="927db-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="927db-222">Разделите значение `x` на значение `y`, сохраните остаток в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-223">[x &= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией И.</span><span class="sxs-lookup"><span data-stu-id="927db-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="927db-224">Выполните операцию И для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="927db-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="927db-226">Выполните операцию ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-227">[x ^= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="927db-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="927db-228">Выполните операцию исключающего ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-229">[x <<= ](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом влево.</span><span class="sxs-lookup"><span data-stu-id="927db-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="927db-230">Сдвиньте значение `x` влево на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом вправо.</span><span class="sxs-lookup"><span data-stu-id="927db-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="927db-232">Сдвиньте значение `x` вправо на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="927db-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="927db-233">[=>](lambda-operator.md) — объявление лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="927db-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="927db-234">См. также</span><span class="sxs-lookup"><span data-stu-id="927db-234">See also</span></span>

- [<span data-ttu-id="927db-235">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="927db-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="927db-236">Инструкции</span><span class="sxs-lookup"><span data-stu-id="927db-236">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)
