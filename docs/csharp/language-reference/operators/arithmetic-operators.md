---
title: Арифметические операторы. Справочник по C#
description: Сведения об операторах C#, выполняющих операции умножения, деления, вычисления остатка, сложения и вычитания с числовыми типами.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: ca2513a0f865fd7da728f7d3247bdb7b50a2f48a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036431"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="0c27e-103">Арифметические операторы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0c27e-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="0c27e-104">Следующие операторы выполняют арифметические операции с операндами числовых типов:</span><span class="sxs-lookup"><span data-stu-id="0c27e-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="0c27e-105">унарные — [`++` (приращение)](#increment-operator-), [`--` (уменьшение)](#decrement-operator---), [`+` (плюс)](#unary-plus-and-minus-operators) и [`-` (минус)](#unary-plus-and-minus-operators);</span><span class="sxs-lookup"><span data-stu-id="0c27e-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="0c27e-106">бинарные — [`*` (умножение)](#multiplication-operator-), [`/` (деление)](#division-operator-), [`%` (остаток от деления)](#remainder-operator-), [`+` (сложение)](#addition-operator-) и [`-` (вычитание)](#subtraction-operator--).</span><span class="sxs-lookup"><span data-stu-id="0c27e-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="0c27e-107">Эти операторы поддерживаются всеми [целочисленными](../builtin-types/integral-numeric-types.md) типами и типами с [плавающей запятой](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="0c27e-108">Оператор инкремента ++</span><span class="sxs-lookup"><span data-stu-id="0c27e-108">Increment operator ++</span></span>

<span data-ttu-id="0c27e-109">Оператор инкремента `++` увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="0c27e-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="0c27e-110">Операндом должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="0c27e-111">Оператор инкремента поддерживается в двух формах: постфиксный оператор инкремента (`x++`) и префиксный оператор инкремента (`++x`).</span><span class="sxs-lookup"><span data-stu-id="0c27e-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="0c27e-112">Постфиксный оператор приращения</span><span class="sxs-lookup"><span data-stu-id="0c27e-112">Postfix increment operator</span></span>

<span data-ttu-id="0c27e-113">Результатом `x++` является значение `x` *перед* выполнением операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c27e-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="0c27e-114">Префиксный оператор инкремента</span><span class="sxs-lookup"><span data-stu-id="0c27e-114">Prefix increment operator</span></span>

<span data-ttu-id="0c27e-115">Результатом `++x` является значение `x` *после* выполнения операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c27e-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="0c27e-116">Оператор декремента --</span><span class="sxs-lookup"><span data-stu-id="0c27e-116">Decrement operator --</span></span>

<span data-ttu-id="0c27e-117">Унарный оператор декремента `--` уменьшает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="0c27e-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="0c27e-118">Операндом должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="0c27e-119">Оператор декремента поддерживается в двух формах: постфиксный оператор декремента (`x--`) и префиксный оператор декремента (`--x`).</span><span class="sxs-lookup"><span data-stu-id="0c27e-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="0c27e-120">Постфиксный оператор уменьшения</span><span class="sxs-lookup"><span data-stu-id="0c27e-120">Postfix decrement operator</span></span>

<span data-ttu-id="0c27e-121">Результатом `x--` является значение `x` *перед* выполнением операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c27e-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="0c27e-122">Префиксный оператор декремента</span><span class="sxs-lookup"><span data-stu-id="0c27e-122">Prefix decrement operator</span></span>

<span data-ttu-id="0c27e-123">Результатом `--x` является значение `x` *после* выполнения операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c27e-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="0c27e-124">Операторы унарного плюса и минуса</span><span class="sxs-lookup"><span data-stu-id="0c27e-124">Unary plus and minus operators</span></span>

<span data-ttu-id="0c27e-125">Унарный оператор `+` возвращает значение полученного операнда.</span><span class="sxs-lookup"><span data-stu-id="0c27e-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="0c27e-126">Унарный оператор `-` изменяет знак операнда на противоположный.</span><span class="sxs-lookup"><span data-stu-id="0c27e-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="0c27e-127">Тип [ulong](../builtin-types/integral-numeric-types.md) не поддерживает унарный оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="0c27e-127">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="0c27e-128">Оператор умножения \*</span><span class="sxs-lookup"><span data-stu-id="0c27e-128">Multiplication operator \*</span></span>

<span data-ttu-id="0c27e-129">Оператор умножения `*` вычисляет произведение операндов:</span><span class="sxs-lookup"><span data-stu-id="0c27e-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="0c27e-130">Унарный оператор `*` представляет собой [оператор косвенного обращения к указателю](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="0c27e-130">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="0c27e-131">Оператор деления /</span><span class="sxs-lookup"><span data-stu-id="0c27e-131">Division operator /</span></span>

<span data-ttu-id="0c27e-132">Оператор деления `/` делит левый операнд на правый.</span><span class="sxs-lookup"><span data-stu-id="0c27e-132">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="0c27e-133">Деление целых чисел</span><span class="sxs-lookup"><span data-stu-id="0c27e-133">Integer division</span></span>

<span data-ttu-id="0c27e-134">Для операндов цельночисленных типов результат оператора `/` является целочисленным типом, который равен частному двух операндов, округленному в сторону нуля:</span><span class="sxs-lookup"><span data-stu-id="0c27e-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="0c27e-135">Чтобы получить частное двух операндов в виде числа с плавающей запятой, используйте тип `float`, `double` или `decimal`:</span><span class="sxs-lookup"><span data-stu-id="0c27e-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="0c27e-136">Деление чисел с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="0c27e-136">Floating-point division</span></span>

<span data-ttu-id="0c27e-137">Для типов `float`, `double` и `decimal` результатом оператора `/` является частное двух операндов:</span><span class="sxs-lookup"><span data-stu-id="0c27e-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="0c27e-138">Если один из операндов — это `decimal`, второй операнд не может быть ни `float`, ни `double`, так как ни `float`, ни `double` не преобразуется неявно в тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0c27e-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="0c27e-139">Необходимо явным образом преобразовать операнд `float` или `double` в тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0c27e-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="0c27e-140">Дополнительные сведения о числовых преобразованиях см. в разделе [Встроенные числовые преобразования](../builtin-types/numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-140">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="0c27e-141">Оператор остатка %</span><span class="sxs-lookup"><span data-stu-id="0c27e-141">Remainder operator %</span></span>

<span data-ttu-id="0c27e-142">Оператор остатка `%` вычисляет остаток от деления левого операнда на правый.</span><span class="sxs-lookup"><span data-stu-id="0c27e-142">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="0c27e-143">Целочисленный остаток</span><span class="sxs-lookup"><span data-stu-id="0c27e-143">Integer remainder</span></span>

<span data-ttu-id="0c27e-144">Для целочисленных операндов результатом `a % b` является значение, произведенное `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="0c27e-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="0c27e-145">Знак ненулевого остатка такой же, как и у левого операнда, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c27e-145">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="0c27e-146">Используйте метод <xref:System.Math.DivRem%2A?displayProperty=nameWithType> для вычисления результатов как целочисленного деления, так и определения остатка.</span><span class="sxs-lookup"><span data-stu-id="0c27e-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="0c27e-147">Остаток с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="0c27e-147">Floating-point remainder</span></span>

<span data-ttu-id="0c27e-148">Для операндов типа `float` и `double` результатом `x % y` для конечных `x` и `y` будет значение `z`, так что:</span><span class="sxs-lookup"><span data-stu-id="0c27e-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="0c27e-149">знак `z`, если отлично от нуля, совпадает со знаком `x`;</span><span class="sxs-lookup"><span data-stu-id="0c27e-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="0c27e-150">абсолютное значение `z` является значением, произведенным `|x| - n * |y|`, где `n` — это наибольшее возможное целое число, которое меньше или равно `|x| / |y|`, а `|x|` и `|y|` являются абсолютными значениями `x` и `y`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="0c27e-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="0c27e-151">Этот метод вычисления остатка аналогичен тому, который использовался для целочисленных операндов, но отличается от спецификации IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="0c27e-151">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="0c27e-152">Если вам нужна операция вычисления остатка, которая соответствует спецификации IEEE 754, используйте метод <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c27e-152">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="0c27e-153">Сведения о поведение оператора `%` в случае неконечных операндов см. в разделе [Оператор остатка](~/_csharplang/spec/expressions.md#remainder-operator) [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0c27e-154">Для операндов `decimal` оператор остатка `%` эквивалентен [оператору остатка](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) типа <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c27e-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="0c27e-155">В следующем примере показано поведение оператора остатка для операндов с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="0c27e-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="0c27e-156">Оператор сложения +</span><span class="sxs-lookup"><span data-stu-id="0c27e-156">Addition operator +</span></span>

<span data-ttu-id="0c27e-157">Оператор сложения `+` вычисляет сумму своих операндов:</span><span class="sxs-lookup"><span data-stu-id="0c27e-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="0c27e-158">Кроме того, оператор `+` можно использовать для объединения строк и делегатов.</span><span class="sxs-lookup"><span data-stu-id="0c27e-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="0c27e-159">Дополнительные сведения см. в статье [Операторы `+` и `+=`](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-159">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="0c27e-160">Оператор вычитания -</span><span class="sxs-lookup"><span data-stu-id="0c27e-160">Subtraction operator -</span></span>

<span data-ttu-id="0c27e-161">Оператор вычитания `-` вычитает правый операнд из левого:</span><span class="sxs-lookup"><span data-stu-id="0c27e-161">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="0c27e-162">Кроме того, оператор `-` можно использовать для удаления делегатов.</span><span class="sxs-lookup"><span data-stu-id="0c27e-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="0c27e-163">Дополнительные сведения см. в статье [Операторы `-` и `-=`](subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-163">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="0c27e-164">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="0c27e-164">Compound assignment</span></span>

<span data-ttu-id="0c27e-165">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="0c27e-165">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="0c27e-166">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="0c27e-166">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="0c27e-167">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="0c27e-167">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="0c27e-168">Следующий пример иллюстрирует использование составного присваивания с арифметическими операторами:</span><span class="sxs-lookup"><span data-stu-id="0c27e-168">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="0c27e-169">Из-за [восходящих приведений](~/_csharplang/spec/expressions.md#numeric-promotions) результат операции `op` может быть невозможно неявно преобразовать в тип `T` из `x`.</span><span class="sxs-lookup"><span data-stu-id="0c27e-169">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="0c27e-170">В этом случае, если `op` является предопределенным оператором, и результат операции является явно преобразуемым в тип `T` `x`, выражение составного присваивания формы `x op= y` эквивалентно `x = (T)(x op y)`, за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="0c27e-170">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="0c27e-171">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="0c27e-171">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="0c27e-172">Вы также можете использовать операторы `+=` и `-=` для подписки и отмены подписки на [события](../keywords/event.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="0c27e-172">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="0c27e-173">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-173">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="0c27e-174">Приоритет и ассоциативность операторов</span><span class="sxs-lookup"><span data-stu-id="0c27e-174">Operator precedence and associativity</span></span>

<span data-ttu-id="0c27e-175">В следующем списке перечислены арифметические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="0c27e-175">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="0c27e-176">Постфиксный инкремент `x++` и декремент `x--`</span><span class="sxs-lookup"><span data-stu-id="0c27e-176">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="0c27e-177">Префиксный инкремент `++x` и декремент `--x`, унарные операторы `+` и `-`</span><span class="sxs-lookup"><span data-stu-id="0c27e-177">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="0c27e-178">Мультипликативные операторы `*`, `/`, и `%`</span><span class="sxs-lookup"><span data-stu-id="0c27e-178">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="0c27e-179">Аддитивные операторы `+` и `-`</span><span class="sxs-lookup"><span data-stu-id="0c27e-179">Additive `+` and `-` operators</span></span>

<span data-ttu-id="0c27e-180">Бинарные арифметические операторы имеют левую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="0c27e-180">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="0c27e-181">То есть операторы с одинаковым приоритетом вычисляются в направлении слева направо.</span><span class="sxs-lookup"><span data-stu-id="0c27e-181">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="0c27e-182">Порядок вычисления, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="0c27e-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="0c27e-183">Полный список операторов C#, упорядоченный по уровню приоритета, можно найти в разделе [Приоритет операторов](index.md#operator-precedence) статьи [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="0c27e-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="0c27e-184">Арифметическое переполнение и деление на нуль</span><span class="sxs-lookup"><span data-stu-id="0c27e-184">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="0c27e-185">Если результат арифметической операции выходит за пределы диапазона возможных конечных значений соответствующего числового типа, поведение арифметического оператора зависит от типа его операндов.</span><span class="sxs-lookup"><span data-stu-id="0c27e-185">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="0c27e-186">Целочисленное арифметическое переполнение</span><span class="sxs-lookup"><span data-stu-id="0c27e-186">Integer arithmetic overflow</span></span>

<span data-ttu-id="0c27e-187">Деление целого числа на ноль всегда вызывает исключение <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="0c27e-187">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="0c27e-188">В случае целочисленного арифметического переполнения итоговое поведение определяется контекстом проверки переполнения, который может быть [проверяемым или непроверяемым](../keywords/checked-and-unchecked.md):</span><span class="sxs-lookup"><span data-stu-id="0c27e-188">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="0c27e-189">Если в проверяемом контексте переполнение возникает в константном выражении, происходит ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="0c27e-189">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="0c27e-190">В противном случае, если операция производится во время выполнения, возникает исключение <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="0c27e-190">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="0c27e-191">В непроверяемом контексте результат усекается путем удаления старших разрядов, которые не помещаются в целевой тип данных.</span><span class="sxs-lookup"><span data-stu-id="0c27e-191">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="0c27e-192">Вместе с [проверяемыми и непроверяемыми](../keywords/checked-and-unchecked.md) операторами вы можете использовать операторы `checked` и `unchecked`, чтобы управлять контекстом проверки переполнения, в котором вычисляется выражение:</span><span class="sxs-lookup"><span data-stu-id="0c27e-192">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="0c27e-193">По умолчанию арифметические операции выполняются в *непроверяемом* контексте.</span><span class="sxs-lookup"><span data-stu-id="0c27e-193">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="0c27e-194">Арифметическое переполнение с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="0c27e-194">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="0c27e-195">Арифметические операции с типами `float` и `double` никогда не вызывают исключение.</span><span class="sxs-lookup"><span data-stu-id="0c27e-195">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="0c27e-196">Результатом арифметических операций с этими типами может быть одно из специальных значений, представляющих бесконечность и объект, не являющийся числовым:</span><span class="sxs-lookup"><span data-stu-id="0c27e-196">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="0c27e-197">Для операндов типа `decimal` арифметическое переполнение всегда вызывает исключение <xref:System.OverflowException>, а деление на нуль всегда вызывает исключение <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="0c27e-197">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="0c27e-198">Ошибки округления</span><span class="sxs-lookup"><span data-stu-id="0c27e-198">Round-off errors</span></span>

<span data-ttu-id="0c27e-199">Из-за общих ограничений, касающихся представления вещественных чисел в форме с плавающей запятой и арифметических операций с плавающей запятой, при вычислениях с использованием типов с плавающей запятой могут возникать ошибки округления.</span><span class="sxs-lookup"><span data-stu-id="0c27e-199">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="0c27e-200">То есть полученный результат выражения может отличаться от ожидаемого математического результата.</span><span class="sxs-lookup"><span data-stu-id="0c27e-200">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="0c27e-201">В следующем примере показано несколько таких случаев:</span><span class="sxs-lookup"><span data-stu-id="0c27e-201">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="0c27e-202">См. заметки в справочной документации по [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) и [System.Decimal](/dotnet/api/system.decimal#remarks).</span><span class="sxs-lookup"><span data-stu-id="0c27e-202">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0c27e-203">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="0c27e-203">Operator overloadability</span></span>

<span data-ttu-id="0c27e-204">Определяемый пользователем тип может [перегружать](operator-overloading.md) унарные (`++`, `--`, `+` и `-`) и бинарные (`*`, `/`, `%`, `+` и `-`) арифметические операторы.</span><span class="sxs-lookup"><span data-stu-id="0c27e-204">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="0c27e-205">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="0c27e-205">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="0c27e-206">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="0c27e-206">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c27e-207">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0c27e-207">C# language specification</span></span>

<span data-ttu-id="0c27e-208">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0c27e-208">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0c27e-209">Постфиксные операторы инкремента и декремента</span><span class="sxs-lookup"><span data-stu-id="0c27e-209">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="0c27e-210">Префиксные операторы инкремента и декремента</span><span class="sxs-lookup"><span data-stu-id="0c27e-210">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="0c27e-211">Оператор унарного плюса</span><span class="sxs-lookup"><span data-stu-id="0c27e-211">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="0c27e-212">Оператор унарного минуса</span><span class="sxs-lookup"><span data-stu-id="0c27e-212">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="0c27e-213">Оператор умножения</span><span class="sxs-lookup"><span data-stu-id="0c27e-213">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="0c27e-214">Оператор деления</span><span class="sxs-lookup"><span data-stu-id="0c27e-214">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="0c27e-215">Оператор остатка</span><span class="sxs-lookup"><span data-stu-id="0c27e-215">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="0c27e-216">Оператор сложения</span><span class="sxs-lookup"><span data-stu-id="0c27e-216">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="0c27e-217">Оператор вычитания</span><span class="sxs-lookup"><span data-stu-id="0c27e-217">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="0c27e-218">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="0c27e-218">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="0c27e-219">Операторы checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="0c27e-219">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="0c27e-220">Восходящие приведения числовых типов</span><span class="sxs-lookup"><span data-stu-id="0c27e-220">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="0c27e-221">См. также</span><span class="sxs-lookup"><span data-stu-id="0c27e-221">See also</span></span>

- [<span data-ttu-id="0c27e-222">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0c27e-222">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c27e-223">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0c27e-223">C# operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="0c27e-224">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="0c27e-224">Numerics in .NET</span></span>](../../../standard/numerics.md)
