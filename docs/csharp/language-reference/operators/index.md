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
ms.openlocfilehash: 4958f3e28b80fca2086d45827df1ced8fc26bd8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672294"
---
# <a name="c-operators"></a><span data-ttu-id="a56e8-102">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a56e8-102">C# operators</span></span>

<span data-ttu-id="a56e8-103">C# предоставляет множество операторов, которые являются символами, указывающими, какие операции (математические операции, индексирование, вызов функции и т. д.) следует выполнять в выражении.</span><span class="sxs-lookup"><span data-stu-id="a56e8-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="a56e8-104">Вы можете [перегрузить](../../programming-guide/statements-expressions-operators/overloadable-operators.md) многие операторы, то есть изменить их значение при применении к некоторому пользовательскому типу.</span><span class="sxs-lookup"><span data-stu-id="a56e8-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="a56e8-105">Обычно для перечислений (`enum`) разрешены все операции, применимые к целочисленным типам (например, `==`, `!=`, `<`, `>`, `&` и `|`).</span><span class="sxs-lookup"><span data-stu-id="a56e8-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="a56e8-106">В следующих разделах перечислены операторы C# в порядке убывания приоритета.</span><span class="sxs-lookup"><span data-stu-id="a56e8-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="a56e8-107">Операторы в каждом разделе совместно используют один и тот же уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="a56e8-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="a56e8-108">Основные операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-108">Primary operators</span></span>

<span data-ttu-id="a56e8-109">Это операторы с наивысшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="a56e8-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="a56e8-110">[x.y](member-access-operator.md) — доступ к членам.</span><span class="sxs-lookup"><span data-stu-id="a56e8-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="a56e8-111">[x?.y](null-conditional-operators.md) — доступ к членам с проверкой NULL.</span><span class="sxs-lookup"><span data-stu-id="a56e8-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="a56e8-112">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="a56e8-113">[x?[y]](null-conditional-operators.md) — доступ к индексам, определяемый условием NULL.</span><span class="sxs-lookup"><span data-stu-id="a56e8-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="a56e8-114">Возвращает значение `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="a56e8-115">[f(x)](invocation-operator.md) — вызов функции.</span><span class="sxs-lookup"><span data-stu-id="a56e8-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="a56e8-116">[a&#91;x&#93;](index-operator.md) — индексирование агрегатного объекта.</span><span class="sxs-lookup"><span data-stu-id="a56e8-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="a56e8-117">[x++](arithmetic-operators.md#increment-operator-) — постфиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="a56e8-118">Возвращает значение x и затем обновляет расположение хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="a56e8-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="a56e8-119">[x--](arithmetic-operators.md#decrement-operator---) — постфиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="a56e8-120">Возвращает значение x и затем обновляет расположение хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="a56e8-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="a56e8-121">[new](../keywords/new-operator.md) – создание экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="a56e8-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="a56e8-122">[typeof](../keywords/typeof.md) — возвращает объект <xref:System.Type>, представляющий операнд.</span><span class="sxs-lookup"><span data-stu-id="a56e8-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="a56e8-123">[checked](../keywords/checked.md) — включает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="a56e8-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="a56e8-124">[unchecked](../keywords/unchecked.md) — отключает проверку на переполнение при выполнении операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="a56e8-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="a56e8-125">Это поведение установлено для компилятора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a56e8-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="a56e8-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) — создает значение типа T по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a56e8-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="a56e8-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) — объявляет и возвращает экземпляр делегата.</span><span class="sxs-lookup"><span data-stu-id="a56e8-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="a56e8-128">[sizeof](../keywords/sizeof.md) — возвращает размер в байтах для типа операнда.</span><span class="sxs-lookup"><span data-stu-id="a56e8-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="a56e8-129">[->](dereference-operator.md) — разыменование указателя в сочетании с доступом к члену.</span><span class="sxs-lookup"><span data-stu-id="a56e8-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="a56e8-130">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-130">Unary operators</span></span>

<span data-ttu-id="a56e8-131">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-132">[+x](addition-operator.md) — возвращает значение x.</span><span class="sxs-lookup"><span data-stu-id="a56e8-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="a56e8-133">[-x](subtraction-operator.md) — числовое отрицание.</span><span class="sxs-lookup"><span data-stu-id="a56e8-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="a56e8-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) — логическое отрицание.</span><span class="sxs-lookup"><span data-stu-id="a56e8-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="a56e8-135">[~x](bitwise-complement-operator.md) — поразрядное дополнение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="a56e8-136">[++x](arithmetic-operators.md#increment-operator-) — префиксный инкремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="a56e8-137">Возвращает значение x после обновления расположения хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="a56e8-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="a56e8-138">[--x](arithmetic-operators.md#decrement-operator---) — префиксный декремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="a56e8-139">Возвращает значение x после обновления расположения хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).</span><span class="sxs-lookup"><span data-stu-id="a56e8-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="a56e8-140">[(T)x](invocation-operator.md) — приведение типов.</span><span class="sxs-lookup"><span data-stu-id="a56e8-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="a56e8-141">[await`Task` — ожидание выполнения ](../keywords/await.md).</span><span class="sxs-lookup"><span data-stu-id="a56e8-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="a56e8-142">[&x](and-operator.md) — получение адреса.</span><span class="sxs-lookup"><span data-stu-id="a56e8-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="a56e8-143">[\*x](multiplication-operator.md) — разыменование.</span><span class="sxs-lookup"><span data-stu-id="a56e8-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="a56e8-144">Мультипликативные операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-144">Multiplicative operators</span></span>

<span data-ttu-id="a56e8-145">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-146">[x \* y](arithmetic-operators.md#multiplication-operator-) — умножение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="a56e8-147">[x / y](arithmetic-operators.md#division-operator-) — деление.</span><span class="sxs-lookup"><span data-stu-id="a56e8-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="a56e8-148">Если операнды имеют целые числа, результатом является целочисленное значение, усеченное в сторону нуля (например, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="a56e8-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="a56e8-149">[x % y](arithmetic-operators.md#remainder-operator-) — остаток.</span><span class="sxs-lookup"><span data-stu-id="a56e8-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="a56e8-150">Если операнды имеют целые числа, это возвращает остаток от деления x на y.</span><span class="sxs-lookup"><span data-stu-id="a56e8-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="a56e8-151">Если `q = x / y` и `r = x % y`, то `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="a56e8-152">Аддитивные операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-152">Additive operators</span></span>

<span data-ttu-id="a56e8-153">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-154">[x + y](arithmetic-operators.md#addition-operator-) — сложение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="a56e8-155">[x – y](arithmetic-operators.md#subtraction-operator--) — вычитание.</span><span class="sxs-lookup"><span data-stu-id="a56e8-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="a56e8-156">Операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="a56e8-156">Shift operators</span></span>

<span data-ttu-id="a56e8-157">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-158">[x <\< y](left-shift-operator.md) — сдвиг битов влево и заполнение правого бита нулем.</span><span class="sxs-lookup"><span data-stu-id="a56e8-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="a56e8-159">[x >> y](right-shift-operator.md) — сдвиг битов вправо.</span><span class="sxs-lookup"><span data-stu-id="a56e8-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="a56e8-160">Если левым операндом является `int` или `long`, затем левые биты заполняются битом знака.</span><span class="sxs-lookup"><span data-stu-id="a56e8-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="a56e8-161">Если левым операндом является `uint` или `ulong`, затем левые биты заполняются нулем.</span><span class="sxs-lookup"><span data-stu-id="a56e8-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="a56e8-162">Относительные операторы и операторы тестирования типа</span><span class="sxs-lookup"><span data-stu-id="a56e8-162">Relational and type-testing operators</span></span>

<span data-ttu-id="a56e8-163">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-164">[x \< y](less-than-operator.md) — меньше чем (возвращает true, если x меньше y).</span><span class="sxs-lookup"><span data-stu-id="a56e8-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="a56e8-165">[x > ](greater-than-operator.md) — больше чем (возвращает true, если x больше y).</span><span class="sxs-lookup"><span data-stu-id="a56e8-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="a56e8-166">[x \<= y](less-than-equal-operator.md) – меньше или равно</span><span class="sxs-lookup"><span data-stu-id="a56e8-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="a56e8-167">[x >= y](greater-than-equal-operator.md) – больше или равно.</span><span class="sxs-lookup"><span data-stu-id="a56e8-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="a56e8-168">[is](../keywords/is.md) — совместимость типов.</span><span class="sxs-lookup"><span data-stu-id="a56e8-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="a56e8-169">Возвращает значение true, если вычисленный левый операнд может быть приведен к типу, указанному в правом операнде (статический тип).</span><span class="sxs-lookup"><span data-stu-id="a56e8-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="a56e8-170">[as](../keywords/as.md) — преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="a56e8-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="a56e8-171">Возвращает левый операнд, приведенный к типу, заданному правым операндом (статический тип), но `as` возвращает `null`, где `(T)x` вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="a56e8-172">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="a56e8-172">Equality operators</span></span>

<span data-ttu-id="a56e8-173">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-174">[x == y](equality-operators.md#equality-operator-) — тождество.</span><span class="sxs-lookup"><span data-stu-id="a56e8-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="a56e8-175">По умолчанию для ссылочных типов, отличных от `string`, этот оператор возвращает равенство ссылок (проверка удостоверения).</span><span class="sxs-lookup"><span data-stu-id="a56e8-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="a56e8-176">Однако типы могут перегрузить `==`, поэтому если планируется проверять удостоверения, лучше использовать метод `ReferenceEquals` для `object`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="a56e8-177">[x != y](equality-operators.md#inequality-operator-) — неравенство.</span><span class="sxs-lookup"><span data-stu-id="a56e8-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="a56e8-178">См. примечание для `==`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-178">See comment for `==`.</span></span> <span data-ttu-id="a56e8-179">Если тип перегружает `==`, то его необходимо перегрузить `!=`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="a56e8-180">Логический оператор AND</span><span class="sxs-lookup"><span data-stu-id="a56e8-180">Logical AND operator</span></span>

<span data-ttu-id="a56e8-181">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-182">[x & y](and-operator.md) — логическая или битовая операция И.</span><span class="sxs-lookup"><span data-stu-id="a56e8-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="a56e8-183">Обычно их можно использовать с целочисленными типами и типами `enum`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="a56e8-184">Оператор логического исключающего ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a56e8-184">Logical XOR operator</span></span>

<span data-ttu-id="a56e8-185">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-186">[x ^ y](xor-operator.md) — логическая или битовая операция исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="a56e8-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="a56e8-187">Обычно их можно использовать с целочисленными типами и типами `enum`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="a56e8-188">Логический оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a56e8-188">Logical OR operator</span></span>

<span data-ttu-id="a56e8-189">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-190">[x &#124; y](or-operator.md) – логическая или битовая операция ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="a56e8-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="a56e8-191">Обычно их можно использовать с целочисленными типами и типами `enum`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="true-operator"></a><span data-ttu-id="a56e8-192">Оператор true</span><span class="sxs-lookup"><span data-stu-id="a56e8-192">True operator</span></span>

<span data-ttu-id="a56e8-193">Оператор [true](../keywords/true-false-operators.md) возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет однозначное значение true.</span><span class="sxs-lookup"><span data-stu-id="a56e8-193">The [true](../keywords/true-false-operators.md) operator returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span> 

## <a name="false-operator"></a><span data-ttu-id="a56e8-194">Оператор false</span><span class="sxs-lookup"><span data-stu-id="a56e8-194">False operator</span></span>

<span data-ttu-id="a56e8-195">Оператор [false](../keywords/true-false-operators.md) возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет однозначное значение false.</span><span class="sxs-lookup"><span data-stu-id="a56e8-195">The [false](../keywords/true-false-operators.md) operator returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span> 

## <a name="conditional-and-operator"></a><span data-ttu-id="a56e8-196">Условный оператор И</span><span class="sxs-lookup"><span data-stu-id="a56e8-196">Conditional AND operator</span></span>

<span data-ttu-id="a56e8-197">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-198">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) — логическое И.</span><span class="sxs-lookup"><span data-stu-id="a56e8-198">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="a56e8-199">Если первый операнд имеет значение false, то C# не вычисляет второй операнд.</span><span class="sxs-lookup"><span data-stu-id="a56e8-199">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="a56e8-200">Условный оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a56e8-200">Conditional OR operator</span></span>

<span data-ttu-id="a56e8-201">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-202">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) — логическое ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="a56e8-202">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="a56e8-203">Если первый операнд имеет значение true, то C# не вычисляет второй операнд.</span><span class="sxs-lookup"><span data-stu-id="a56e8-203">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="a56e8-204">Оператор объединения с NULL</span><span class="sxs-lookup"><span data-stu-id="a56e8-204">Null-coalescing operator</span></span>

<span data-ttu-id="a56e8-205">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-205">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-206">[x ?? y](null-coalescing-operator.md) — возвращает `x`, если значение отличается от `null`; в противном случае возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-206">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="a56e8-207">Условный оператор</span><span class="sxs-lookup"><span data-stu-id="a56e8-207">Conditional operator</span></span>

<span data-ttu-id="a56e8-208">Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-208">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-209">[t ? x : y](conditional-operator.md) — если условие `t` имеет значение true, вычисляет и возвращает `x`, в противном случае вычисляет и возвращает `y`.</span><span class="sxs-lookup"><span data-stu-id="a56e8-209">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="a56e8-210">Назначение и лямбда-операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-210">Assignment and Lambda operators</span></span>

<span data-ttu-id="a56e8-211">Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.</span><span class="sxs-lookup"><span data-stu-id="a56e8-211">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a56e8-212">[x = y](assignment-operator.md) — назначение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-212">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="a56e8-213">[x += y](addition-assignment-operator.md) — инкремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-213">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="a56e8-214">Добавьте значение `y` к значению `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-214">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="a56e8-215">Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# добавляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a56e8-215">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="a56e8-216">[x -= y](subtraction-assignment-operator.md) — декремент.</span><span class="sxs-lookup"><span data-stu-id="a56e8-216">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="a56e8-217">Вычтите значение `y` из значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-217">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="a56e8-218">Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# удаляет в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a56e8-218">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="a56e8-219">[x \*= y](multiplication-assignment-operator.md) — назначение с умножением.</span><span class="sxs-lookup"><span data-stu-id="a56e8-219">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="a56e8-220">Умножьте значение `y` на значение `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-220">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-221">[x /= y](arithmetic-operators.md#compound-assignment) — назначение с делением.</span><span class="sxs-lookup"><span data-stu-id="a56e8-221">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="a56e8-222">Разделите значение `x` на значение `y`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-222">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-223">[x %= y](arithmetic-operators.md#compound-assignment) — присваивание остатка.</span><span class="sxs-lookup"><span data-stu-id="a56e8-223">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="a56e8-224">Разделите значение `x` на значение `y`, сохраните остаток в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-224">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-225">[x &= y](and-assignment-operator.md) — назначение с операцией И.</span><span class="sxs-lookup"><span data-stu-id="a56e8-225">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="a56e8-226">Выполните операцию И для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-226">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-227">[x &#124;= y](or-assignment-operator.md) — назначение с операцией ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="a56e8-227">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="a56e8-228">Выполните операцию ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-228">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-229">[x ^= y](xor-assignment-operator.md) — назначение с операцией исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="a56e8-229">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="a56e8-230">Выполните операцию исключающего ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-230">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-231">[x <<= ](left-shift-assignment-operator.md) — назначение со сдвигом влево.</span><span class="sxs-lookup"><span data-stu-id="a56e8-231">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="a56e8-232">Сдвиньте значение `x` влево на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-232">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-233">[x >>= y](right-shift-assignment-operator.md) — назначение со сдвигом вправо.</span><span class="sxs-lookup"><span data-stu-id="a56e8-233">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="a56e8-234">Сдвиньте значение `x` вправо на `y` позиций, сохраните результат в `x` и возвратите новое значение.</span><span class="sxs-lookup"><span data-stu-id="a56e8-234">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a56e8-235">[=>](lambda-operator.md) — объявление лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="a56e8-235">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="a56e8-236">См. также</span><span class="sxs-lookup"><span data-stu-id="a56e8-236">See also</span></span>

- [<span data-ttu-id="a56e8-237">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a56e8-237">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a56e8-238">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a56e8-238">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a56e8-239">C#</span><span class="sxs-lookup"><span data-stu-id="a56e8-239">C#</span></span>](../../index.md)
- [<span data-ttu-id="a56e8-240">Перегружаемые операторы</span><span class="sxs-lookup"><span data-stu-id="a56e8-240">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="a56e8-241">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a56e8-241">C# Keywords</span></span>](../keywords/index.md)
