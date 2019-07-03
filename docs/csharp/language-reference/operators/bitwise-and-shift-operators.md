---
title: Побитовые операторы и операторы сдвига. Справочник по C#
description: Дополнительные сведения об операторах C#, которые выполняют побитовые логические операции или операции сдвига с операндами целочисленного типа.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: 4a495fb5ce353bcb4f7ccda975dfc74ba711db79
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025243"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="47b28-103">Побитовые операторы и операторы сдвига (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="47b28-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="47b28-104">Следующие операторы выполняют побитовые операции или операции сдвига с операндами [целочисленных типов](../keywords/integral-types-table.md):</span><span class="sxs-lookup"><span data-stu-id="47b28-104">The following operators perform bitwise or shift operations with operands of the [integral types](../keywords/integral-types-table.md):</span></span>

- <span data-ttu-id="47b28-105">Унарный оператор [`~` (побитовое дополнение)](#bitwise-complement-operator-)</span><span class="sxs-lookup"><span data-stu-id="47b28-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="47b28-106">Бинарные операторы сдвига [`<<` (сдвиг влево)](#left-shift-operator-) и [`>>` (сдвиг вправо)](#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="47b28-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="47b28-107">Бинарные операторы [`&` (логическое и)](#logical-and-operator-), [`|` (логическое или)](#logical-or-operator-) и [`^` (логическое исключающее или)](#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="47b28-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="47b28-108">Эти операторы определены для типов `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="47b28-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="47b28-109">Если оба операнда имеют другие целочисленные типы (`sbyte`, `byte`, `short`, `ushort` или `char`), их значения преобразуются в тип `int`, который также является типом результата операции.</span><span class="sxs-lookup"><span data-stu-id="47b28-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="47b28-110">Если операнды имеют разные целочисленные типы, их значения преобразуются в ближайший содержащий целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="47b28-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="47b28-111">Дополнительные сведения см. в разделе [Числовые повышения уровня](~/_csharplang/spec/expressions.md#numeric-promotions) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="47b28-112">Операторы `&`, `|` и `^` также определяются для операндов типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="47b28-112">The `&`, `|`, and `^` operators are also defined for the operands of the `bool` type.</span></span> <span data-ttu-id="47b28-113">Дополнительные сведения см. в разделе [Логические операторы](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="47b28-114">Побитовые операции и операции сдвига никогда не вызывают переполнение и дают одинаковые результаты в [проверенных и непроверенных](../keywords/checked-and-unchecked.md) контекстах.</span><span class="sxs-lookup"><span data-stu-id="47b28-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="47b28-115">Оператор побитового дополнения ~</span><span class="sxs-lookup"><span data-stu-id="47b28-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="47b28-116">Оператор `~` создает побитовое дополнение своего операнда путем инвертирования каждого бита:</span><span class="sxs-lookup"><span data-stu-id="47b28-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="47b28-117">Можно также использовать символ `~` для объявления методов завершения.</span><span class="sxs-lookup"><span data-stu-id="47b28-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="47b28-118">Дополнительные сведения см. в разделе [Методы завершения](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="47b28-119">Оператор сдвига влево \<\<</span><span class="sxs-lookup"><span data-stu-id="47b28-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="47b28-120">Оператор `<<` сдвигает первый операнд влево на количество битов, определенное вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="47b28-120">The `<<` operator shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="47b28-121">Операция сдвига влево отбрасывает старшие биты, которые находятся за пределами диапазона типа результата, и задает позиции пустых битов низкого порядка, равные нулю, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="47b28-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="47b28-122">Поскольку операторы сдвига определены только для типов `int`, `uint`, `long` и `ulong`, результат операции всегда содержит по крайней мере 32 бита.</span><span class="sxs-lookup"><span data-stu-id="47b28-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="47b28-123">Если первый операнд имеет другой целочисленный тип (`sbyte`, `byte`, `short`, `ushort` или `char`), его значение преобразуется в тип `int`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="47b28-123">If the first operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="47b28-124">Сведения о том, как второй операнд оператора `<<` определяет величину сдвига, см. в разделе [Величина смещения операторов сдвига](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="47b28-124">For information about how the second operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="47b28-125">Оператор сдвига вправо >></span><span class="sxs-lookup"><span data-stu-id="47b28-125">Right-shift operator >></span></span>

<span data-ttu-id="47b28-126">Оператор `>>` сдвигает первый операнд вправо на количество битов, определенное вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="47b28-126">The `>>` operator shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="47b28-127">Операция сдвига вправо удаляет младшие разряды, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="47b28-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="47b28-128">Позиции пустых битов высокого порядка задаются с учетом типа первого операнда следующим образом.</span><span class="sxs-lookup"><span data-stu-id="47b28-128">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="47b28-129">Если первый операнд имеет тип [int](../keywords/int.md) или [long](../keywords/long.md), оператор сдвига вправо выполняет *арифметический* сдвиг. Значение старшего значимого бита (знаковый бит) первого операнда распространяется на пустые битовые позиции высокого разряда.</span><span class="sxs-lookup"><span data-stu-id="47b28-129">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="47b28-130">То есть пустые битовые позиции высокого порядка разряда устанавливаются на ноль, если первый операнд неотрицательный, и устанавливаются на единицу, если он отрицательный.</span><span class="sxs-lookup"><span data-stu-id="47b28-130">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="47b28-131">Если первый операнд имеет тип [uint](../keywords/uint.md) или [ulong](../keywords/ulong.md), оператор сдвига вправо выполняет *логический* сдвиг. Пустым битовым позициям высокого порядка всегда присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="47b28-131">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="47b28-132">Сведения о том, как второй операнд оператора `>>` определяет величину сдвига, см. в разделе [Величина смещения операторов сдвига](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="47b28-132">For information about how the second operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-amp"></a><span data-ttu-id="47b28-133">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="47b28-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="47b28-134">Оператор `&` вычисляет побитовое логическое И своих операндов:</span><span class="sxs-lookup"><span data-stu-id="47b28-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="47b28-135">Для операндов типа `bool` оператор `&` вычисляет [логическое И](boolean-logical-operators.md#logical-and-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="47b28-135">For the operands of the `bool` type, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="47b28-136">Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="47b28-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="47b28-137">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="47b28-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="47b28-138">Оператор `^` вычисляет побитовое логическое исключающее ИЛИ, также известное как побитовое логическое XOR, своих операндов:</span><span class="sxs-lookup"><span data-stu-id="47b28-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="47b28-139">Для операндов типа `bool` оператор `^` вычисляет [логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="47b28-139">For the operands of the `bool` type, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="47b28-140">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="47b28-140">Logical OR operator |</span></span>

<span data-ttu-id="47b28-141">Оператор `|` вычисляет побитовое логическое ИЛИ своих операндов:</span><span class="sxs-lookup"><span data-stu-id="47b28-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="47b28-142">Для операндов типа `bool` оператор `|` вычисляет [логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="47b28-142">For the operands of the `bool` type, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="47b28-143">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="47b28-143">Compound assignment</span></span>

<span data-ttu-id="47b28-144">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="47b28-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="47b28-145">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="47b28-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="47b28-146">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="47b28-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="47b28-147">В следующем примере показано использование составного присваивания с побитовыми операторами и операторами сдвига:</span><span class="sxs-lookup"><span data-stu-id="47b28-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="47b28-148">Из-за [числовых повышений уровня](~/_csharplang/spec/expressions.md#numeric-promotions) результат операции `op` может не быть явно преобразуемым в тип `T` `x`.</span><span class="sxs-lookup"><span data-stu-id="47b28-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="47b28-149">В этом случае, если `op` является предопределенным оператором, и результат операции является явно преобразуемым в тип `T` `x`, выражение составного присваивания формы `x op= y` эквивалентно `x = (T)(x op y)`, за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="47b28-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="47b28-150">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="47b28-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="47b28-151">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="47b28-151">Operator precedence</span></span>

<span data-ttu-id="47b28-152">Следующий список упорядочивает побитовые операторы и операторы сдвига по приоритету, от высокого до низкого:</span><span class="sxs-lookup"><span data-stu-id="47b28-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="47b28-153">Оператор побитового дополнения `~`</span><span class="sxs-lookup"><span data-stu-id="47b28-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="47b28-154">Операторы сдвига `<<` и `>>`</span><span class="sxs-lookup"><span data-stu-id="47b28-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="47b28-155">Оператор логического И `&`</span><span class="sxs-lookup"><span data-stu-id="47b28-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="47b28-156">Оператор логического исключающего ИЛИ `^`</span><span class="sxs-lookup"><span data-stu-id="47b28-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="47b28-157">Оператор логического ИЛИ `|`</span><span class="sxs-lookup"><span data-stu-id="47b28-157">Logical OR operator `|`</span></span>

<span data-ttu-id="47b28-158">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="47b28-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="47b28-159">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-159">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="47b28-160">Величина смещения операторов сдвига</span><span class="sxs-lookup"><span data-stu-id="47b28-160">Shift count of the shift operators</span></span>

<span data-ttu-id="47b28-161">Для операторов сдвига `<<` и `>>` тип второго операнда должен быть [int](../keywords/int.md) или типом, имеющим [предопределенное неявное числовое преобразование](../keywords/implicit-numeric-conversions-table.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="47b28-161">For the shift operators `<<` and `>>`, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="47b28-162">Для выражений `x << count` и `x >> count` фактическая величина сдвига зависит от типа `x` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="47b28-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="47b28-163">Если тип `x` — [int](../keywords/int.md) или [uint](../keywords/uint.md), величина сдвига определяется младшими *пятью* битами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="47b28-163">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is defined by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="47b28-164">То есть величина сдвига вычисляется на основе `count & 0x1F` (или `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="47b28-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="47b28-165">Если тип `x` — [long](../keywords/long.md) или [ulong](../keywords/ulong.md), величина сдвига определяется младшими *шестью* битами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="47b28-165">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is defined by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="47b28-166">То есть величина сдвига вычисляется на основе `count & 0x3F` (или `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="47b28-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="47b28-167">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="47b28-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="47b28-168">Логические операторы перечисления</span><span class="sxs-lookup"><span data-stu-id="47b28-168">Enumeration logical operators</span></span>

<span data-ttu-id="47b28-169">Операторы `~`, `&`, `|` и `^` также определены для любого типа [перечисления](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-169">The `~`, `&`, `|`, and `^` operators are also defined for any [enumeration](../keywords/enum.md) type.</span></span> <span data-ttu-id="47b28-170">Для операндов одного типа перечисления логическая операция выполняется для соответствующих значений базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="47b28-170">For the operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="47b28-171">Например, для любого `x` и `y` типа перечисления `T` с базовым типом `U` выражение `x & y` дает тот же результат, что и выражение `(T)((U)x & (U)y)`.</span><span class="sxs-lookup"><span data-stu-id="47b28-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="47b28-172">Побитовые логические операторы обычно используются с типом перечисления, который определяется с помощью атрибута [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="47b28-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="47b28-173">Дополнительные сведения см. в разделе [Типы перечислений как битовые флаги](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) в статье [Типы перечислений](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="47b28-173">For more information, see the [Enumeration types as bit flags](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../../programming-guide/enumeration-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="47b28-174">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="47b28-174">Operator overloadability</span></span>

<span data-ttu-id="47b28-175">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `~`, `<<`, `>>`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="47b28-175">A user-defined type can [overload](../keywords/operator.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="47b28-176">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="47b28-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="47b28-177">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="47b28-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="47b28-178">Если определяемый пользователем тип `T` перегружает оператор `<<` или `>>`, тип первого операнда должен быть `T`, а тип второго — `int`.</span><span class="sxs-lookup"><span data-stu-id="47b28-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="47b28-179">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="47b28-179">C# language specification</span></span>

<span data-ttu-id="47b28-180">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="47b28-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="47b28-181">Оператор побитового дополнения</span><span class="sxs-lookup"><span data-stu-id="47b28-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="47b28-182">Операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="47b28-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="47b28-183">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="47b28-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="47b28-184">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="47b28-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="47b28-185">Числовые повышения уровня</span><span class="sxs-lookup"><span data-stu-id="47b28-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="47b28-186">См. также</span><span class="sxs-lookup"><span data-stu-id="47b28-186">See also</span></span>

- [<span data-ttu-id="47b28-187">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="47b28-187">C# reference</span></span>](../index.md)
- [<span data-ttu-id="47b28-188">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="47b28-188">C# operators</span></span>](index.md)
- [<span data-ttu-id="47b28-189">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="47b28-189">Boolean logical operators</span></span>](boolean-logical-operators.md)
