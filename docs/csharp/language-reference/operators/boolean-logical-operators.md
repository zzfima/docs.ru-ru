---
title: Логические операторы. Справочник по C#
description: Узнайте об операторах C#, которые выполняют такие логические операции, как отрицание, конъюнкция (И), а также инклюзивная и эксклюзивная дизъюнкция (ИЛИ), с использованием соответствующих операндов.
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: 60907eb1bbfeb1daa9d9a74733387c4771accb45
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423977"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="2cd2a-103">Логические операторы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2cd2a-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="2cd2a-104">Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="2cd2a-105">Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="2cd2a-106">Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="2cd2a-107">Эти операторы всегда обрабатывают оба операнда.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="2cd2a-108">Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="2cd2a-109">Эти операторы вычисляют правый операнд, только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="2cd2a-110">Для операндов [целочисленных](../builtin-types/integral-numeric-types.md) типов операторы `&`, `|` и `^` выполняют побитовые логические операции.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="2cd2a-111">Дополнительные сведения см. в разделе [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="2cd2a-112">Оператор логического отрицания !</span><span class="sxs-lookup"><span data-stu-id="2cd2a-112">Logical negation operator !</span></span>

<span data-ttu-id="2cd2a-113">Оператор `!` выполняет логическое отрицание операнда,</span><span class="sxs-lookup"><span data-stu-id="2cd2a-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="2cd2a-114">возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

## <a name="logical-and-operator-"></a> <span data-ttu-id="2cd2a-115">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="2cd2a-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="2cd2a-116">Оператор `&` вычисляет логическое И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="2cd2a-117">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="2cd2a-118">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="2cd2a-119">Оператор `&` вычисляет оба операнда, даже если левый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения правого операнда.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-119">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="2cd2a-120">В следующем примере правый операнд оператора `&` является вызовом метода, который выполняется независимо от значения левого операнда:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-120">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="2cd2a-121">[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="2cd2a-122">Для операндов целочисленного типа оператор `&` вычисляет [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="2cd2a-123">Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="2cd2a-124">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="2cd2a-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="2cd2a-125">Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов,</span><span class="sxs-lookup"><span data-stu-id="2cd2a-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="2cd2a-126">возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="2cd2a-127">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="2cd2a-128">То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="2cd2a-129">Для операндов целочисленного типа оператор `^` вычисляет [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="2cd2a-130">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="2cd2a-130">Logical OR operator |</span></span>

<span data-ttu-id="2cd2a-131">Оператор `|` вычисляет логическое ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="2cd2a-132">Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="2cd2a-133">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="2cd2a-134">Оператор `|` вычисляет оба операнда, даже если левый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения правого операнда.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-134">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="2cd2a-135">В следующем примере правый операнд оператора `|` является вызовом метода, который выполняется независимо от значения левого операнда:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-135">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="2cd2a-136">[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="2cd2a-137">Для операндов целочисленного типа оператор `|` вычисляет [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="2cd2a-138">Условный оператор логического И &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="2cd2a-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="2cd2a-139">Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="2cd2a-140">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="2cd2a-141">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="2cd2a-142">Если `x` имеет значение `false`, `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-142">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="2cd2a-143">В следующем примере правый операнд оператора `&&` является вызовом метода, который не выполняется, если левый операнд имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-143">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="2cd2a-144">[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="2cd2a-145">Условный оператор логического ИЛИ ||</span><span class="sxs-lookup"><span data-stu-id="2cd2a-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="2cd2a-146">Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="2cd2a-147">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="2cd2a-148">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="2cd2a-149">Если `x` имеет значение `true`, `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-149">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="2cd2a-150">В следующем примере правый операнд оператора `||` является вызовом метода, который не выполняется, если левый операнд имеет значение `true`:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-150">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="2cd2a-151">[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="2cd2a-152">Операторы, допускающие логическое значение NULL</span><span class="sxs-lookup"><span data-stu-id="2cd2a-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="2cd2a-153">Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="2cd2a-154">Семантика этих операторов определяется по следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="2cd2a-155">x</span><span class="sxs-lookup"><span data-stu-id="2cd2a-155">x</span></span>|<span data-ttu-id="2cd2a-156">y</span><span class="sxs-lookup"><span data-stu-id="2cd2a-156">y</span></span>|<span data-ttu-id="2cd2a-157">x&y</span><span class="sxs-lookup"><span data-stu-id="2cd2a-157">x&y</span></span>|<span data-ttu-id="2cd2a-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="2cd2a-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="2cd2a-159">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-159">true</span></span>|<span data-ttu-id="2cd2a-160">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-160">true</span></span>|<span data-ttu-id="2cd2a-161">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-161">true</span></span>|<span data-ttu-id="2cd2a-162">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-162">true</span></span>|  
|<span data-ttu-id="2cd2a-163">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-163">true</span></span>|<span data-ttu-id="2cd2a-164">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-164">false</span></span>|<span data-ttu-id="2cd2a-165">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-165">false</span></span>|<span data-ttu-id="2cd2a-166">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-166">true</span></span>|  
|<span data-ttu-id="2cd2a-167">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-167">true</span></span>|<span data-ttu-id="2cd2a-168">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-168">null</span></span>|<span data-ttu-id="2cd2a-169">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-169">null</span></span>|<span data-ttu-id="2cd2a-170">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-170">true</span></span>|  
|<span data-ttu-id="2cd2a-171">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-171">false</span></span>|<span data-ttu-id="2cd2a-172">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-172">true</span></span>|<span data-ttu-id="2cd2a-173">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-173">false</span></span>|<span data-ttu-id="2cd2a-174">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-174">true</span></span>|  
|<span data-ttu-id="2cd2a-175">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-175">false</span></span>|<span data-ttu-id="2cd2a-176">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-176">false</span></span>|<span data-ttu-id="2cd2a-177">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-177">false</span></span>|<span data-ttu-id="2cd2a-178">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-178">false</span></span>|  
|<span data-ttu-id="2cd2a-179">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-179">false</span></span>|<span data-ttu-id="2cd2a-180">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-180">null</span></span>|<span data-ttu-id="2cd2a-181">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-181">false</span></span>|<span data-ttu-id="2cd2a-182">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-182">null</span></span>|  
|<span data-ttu-id="2cd2a-183">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-183">null</span></span>|<span data-ttu-id="2cd2a-184">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-184">true</span></span>|<span data-ttu-id="2cd2a-185">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-185">null</span></span>|<span data-ttu-id="2cd2a-186">true</span><span class="sxs-lookup"><span data-stu-id="2cd2a-186">true</span></span>|  
|<span data-ttu-id="2cd2a-187">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-187">null</span></span>|<span data-ttu-id="2cd2a-188">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-188">false</span></span>|<span data-ttu-id="2cd2a-189">false</span><span class="sxs-lookup"><span data-stu-id="2cd2a-189">false</span></span>|<span data-ttu-id="2cd2a-190">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-190">null</span></span>|  
|<span data-ttu-id="2cd2a-191">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-191">null</span></span>|<span data-ttu-id="2cd2a-192">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-192">null</span></span>|<span data-ttu-id="2cd2a-193">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-193">null</span></span>|<span data-ttu-id="2cd2a-194">null</span><span class="sxs-lookup"><span data-stu-id="2cd2a-194">null</span></span>|  

<span data-ttu-id="2cd2a-195">Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="2cd2a-196">Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="2cd2a-197">Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="2cd2a-198">При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="2cd2a-199">См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="2cd2a-200">Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="2cd2a-201">Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="2cd2a-202">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="2cd2a-202">Compound assignment</span></span>

<span data-ttu-id="2cd2a-203">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="2cd2a-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="2cd2a-204">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="2cd2a-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="2cd2a-205">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="2cd2a-206">Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="2cd2a-207">Условные логические операторы `&&` и `||` не поддерживают составное присваивание.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="2cd2a-208">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="2cd2a-208">Operator precedence</span></span>

<span data-ttu-id="2cd2a-209">В следующем списке перечислены логические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="2cd2a-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="2cd2a-210">Оператор логического отрицания `!`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="2cd2a-211">Оператор логического И `&`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="2cd2a-212">Оператор логического исключающего ИЛИ `^`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="2cd2a-213">Оператор логического ИЛИ `|`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="2cd2a-214">Условный оператор логического И `&&`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="2cd2a-215">Условный оператор логического ИЛИ `||`</span><span class="sxs-lookup"><span data-stu-id="2cd2a-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="2cd2a-216">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="2cd2a-217">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="2cd2a-218">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="2cd2a-218">Operator overloadability</span></span>

<span data-ttu-id="2cd2a-219">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `!`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="2cd2a-220">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="2cd2a-221">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="2cd2a-222">Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="2cd2a-223">При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="2cd2a-223">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="2cd2a-224">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2a-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2cd2a-225">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2cd2a-225">C# language specification</span></span>

<span data-ttu-id="2cd2a-226">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="2cd2a-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="2cd2a-227">Оператор логического отрицания</span><span class="sxs-lookup"><span data-stu-id="2cd2a-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="2cd2a-228">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="2cd2a-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="2cd2a-229">Условные логические операторы</span><span class="sxs-lookup"><span data-stu-id="2cd2a-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="2cd2a-230">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="2cd2a-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="2cd2a-231">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd2a-231">See also</span></span>

- [<span data-ttu-id="2cd2a-232">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2cd2a-232">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2cd2a-233">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2cd2a-233">C# operators</span></span>](index.md)
- [<span data-ttu-id="2cd2a-234">Побитовые операторы и операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="2cd2a-234">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
