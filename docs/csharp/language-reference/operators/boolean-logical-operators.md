---
title: Справочник по C#. Логические операторы
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
ms.openlocfilehash: d94552d9a1acfdd63b9694810e724c4347e615e7
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758275"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="be8e9-103">Справочник по C#. Логические операторы</span><span class="sxs-lookup"><span data-stu-id="be8e9-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="be8e9-104">Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:</span><span class="sxs-lookup"><span data-stu-id="be8e9-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="be8e9-105">Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.</span><span class="sxs-lookup"><span data-stu-id="be8e9-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="be8e9-106">Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="be8e9-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="be8e9-107">Эти операторы всегда обрабатывают оба операнда.</span><span class="sxs-lookup"><span data-stu-id="be8e9-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="be8e9-108">Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="be8e9-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="be8e9-109">Эти операторы вычисляют второй операнд, только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="be8e9-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="be8e9-110">Для операндов [целочисленных](../keywords/integral-types-table.md) типов операторы `&`, `|` и `^` выполняют побитовые логические операции.</span><span class="sxs-lookup"><span data-stu-id="be8e9-110">For the operands of the [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="be8e9-111">Дополнительные сведения см. в разделе [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="be8e9-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="be8e9-112">Оператор логического отрицания !</span><span class="sxs-lookup"><span data-stu-id="be8e9-112">Logical negation operator !</span></span>

<span data-ttu-id="be8e9-113">Оператор `!` выполняет логическое отрицание операнда,</span><span class="sxs-lookup"><span data-stu-id="be8e9-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="be8e9-114">возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="be8e9-115">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="be8e9-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="be8e9-116">Оператор `&` вычисляет логическое И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="be8e9-117">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="be8e9-118">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="be8e9-119">Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="be8e9-119">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="be8e9-120">В следующем примере второй операнд оператора `&` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="be8e9-120">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="be8e9-121">[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но он не вычисляет второй операнд, если первый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="be8e9-122">Для операндов целочисленного типа оператор `&` вычисляет [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="be8e9-123">Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="be8e9-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="be8e9-124">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="be8e9-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="be8e9-125">Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов,</span><span class="sxs-lookup"><span data-stu-id="be8e9-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="be8e9-126">возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="be8e9-127">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="be8e9-128">То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="be8e9-129">Для операндов целочисленного типа оператор `^` вычисляет [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="be8e9-130">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="be8e9-130">Logical OR operator |</span></span>

<span data-ttu-id="be8e9-131">Оператор `|` вычисляет логическое ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="be8e9-132">Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="be8e9-133">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="be8e9-134">Оператор `|` вычисляет оба операнда, даже если первый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="be8e9-134">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="be8e9-135">В следующем примере второй операнд оператора `|` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="be8e9-135">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="be8e9-136">[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет второй операнд, если первый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="be8e9-137">Для операндов целочисленного типа оператор `|` вычисляет [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="be8e9-138">Условный оператор логического И &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="be8e9-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="be8e9-139">Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="be8e9-140">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="be8e9-141">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="be8e9-142">Если результатом первого операнда является значение `false`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="be8e9-142">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="be8e9-143">В следующем примере второй операнд оператора `&&` является вызовом метода, который не выполняется, если первый операнд имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="be8e9-143">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="be8e9-144">[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="be8e9-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="be8e9-145">Условный оператор логического ИЛИ ||</span><span class="sxs-lookup"><span data-stu-id="be8e9-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="be8e9-146">Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="be8e9-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="be8e9-147">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="be8e9-148">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="be8e9-149">Если результатом первого операнда является значение `true`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="be8e9-149">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="be8e9-150">В следующем примере второй операнд оператора `||` является вызовом метода, который не выполняется, если первый операнд имеет значение `true`:</span><span class="sxs-lookup"><span data-stu-id="be8e9-150">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="be8e9-151">[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="be8e9-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="be8e9-152">Операторы, допускающие логическое значение NULL</span><span class="sxs-lookup"><span data-stu-id="be8e9-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="be8e9-153">Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="be8e9-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="be8e9-154">Семантика этих операторов определяется по следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="be8e9-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="be8e9-155">x</span><span class="sxs-lookup"><span data-stu-id="be8e9-155">x</span></span>|<span data-ttu-id="be8e9-156">y</span><span class="sxs-lookup"><span data-stu-id="be8e9-156">y</span></span>|<span data-ttu-id="be8e9-157">x&y</span><span class="sxs-lookup"><span data-stu-id="be8e9-157">x&y</span></span>|<span data-ttu-id="be8e9-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="be8e9-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="be8e9-159">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-159">true</span></span>|<span data-ttu-id="be8e9-160">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-160">true</span></span>|<span data-ttu-id="be8e9-161">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-161">true</span></span>|<span data-ttu-id="be8e9-162">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-162">true</span></span>|  
|<span data-ttu-id="be8e9-163">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-163">true</span></span>|<span data-ttu-id="be8e9-164">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-164">false</span></span>|<span data-ttu-id="be8e9-165">false</span><span class="sxs-lookup"><span data-stu-id="be8e9-165">false</span></span>|<span data-ttu-id="be8e9-166">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-166">true</span></span>|  
|<span data-ttu-id="be8e9-167">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-167">true</span></span>|<span data-ttu-id="be8e9-168">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-168">null</span></span>|<span data-ttu-id="be8e9-169">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-169">null</span></span>|<span data-ttu-id="be8e9-170">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-170">true</span></span>|  
|<span data-ttu-id="be8e9-171">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-171">false</span></span>|<span data-ttu-id="be8e9-172">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-172">true</span></span>|<span data-ttu-id="be8e9-173">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-173">false</span></span>|<span data-ttu-id="be8e9-174">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-174">true</span></span>|  
|<span data-ttu-id="be8e9-175">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-175">false</span></span>|<span data-ttu-id="be8e9-176">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-176">false</span></span>|<span data-ttu-id="be8e9-177">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-177">false</span></span>|<span data-ttu-id="be8e9-178">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-178">false</span></span>|  
|<span data-ttu-id="be8e9-179">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-179">false</span></span>|<span data-ttu-id="be8e9-180">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-180">null</span></span>|<span data-ttu-id="be8e9-181">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-181">false</span></span>|<span data-ttu-id="be8e9-182">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-182">null</span></span>|  
|<span data-ttu-id="be8e9-183">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-183">null</span></span>|<span data-ttu-id="be8e9-184">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-184">true</span></span>|<span data-ttu-id="be8e9-185">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-185">null</span></span>|<span data-ttu-id="be8e9-186">true</span><span class="sxs-lookup"><span data-stu-id="be8e9-186">true</span></span>|  
|<span data-ttu-id="be8e9-187">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-187">null</span></span>|<span data-ttu-id="be8e9-188">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-188">false</span></span>|<span data-ttu-id="be8e9-189">False</span><span class="sxs-lookup"><span data-stu-id="be8e9-189">false</span></span>|<span data-ttu-id="be8e9-190">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-190">null</span></span>|  
|<span data-ttu-id="be8e9-191">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-191">null</span></span>|<span data-ttu-id="be8e9-192">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-192">null</span></span>|<span data-ttu-id="be8e9-193">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-193">null</span></span>|<span data-ttu-id="be8e9-194">null</span><span class="sxs-lookup"><span data-stu-id="be8e9-194">null</span></span>|  

<span data-ttu-id="be8e9-195">Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="be8e9-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="be8e9-196">Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="be8e9-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="be8e9-197">Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="be8e9-198">При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="be8e9-199">См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="be8e9-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="be8e9-200">Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="be8e9-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="be8e9-201">Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="be8e9-202">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="be8e9-202">Compound assignment</span></span>

<span data-ttu-id="be8e9-203">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="be8e9-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="be8e9-204">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="be8e9-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="be8e9-205">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="be8e9-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="be8e9-206">Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="be8e9-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="be8e9-207">Условные логические операторы `&&` и `||` не поддерживают составное присваивание.</span><span class="sxs-lookup"><span data-stu-id="be8e9-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="be8e9-208">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="be8e9-208">Operator precedence</span></span>

<span data-ttu-id="be8e9-209">В следующем списке перечислены логические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="be8e9-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="be8e9-210">Оператор логического отрицания `!`</span><span class="sxs-lookup"><span data-stu-id="be8e9-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="be8e9-211">Оператор логического И `&`</span><span class="sxs-lookup"><span data-stu-id="be8e9-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="be8e9-212">Оператор логического исключающего ИЛИ `^`</span><span class="sxs-lookup"><span data-stu-id="be8e9-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="be8e9-213">Оператор логического ИЛИ `|`</span><span class="sxs-lookup"><span data-stu-id="be8e9-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="be8e9-214">Условный оператор логического И `&&`</span><span class="sxs-lookup"><span data-stu-id="be8e9-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="be8e9-215">Условный оператор логического ИЛИ `||`</span><span class="sxs-lookup"><span data-stu-id="be8e9-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="be8e9-216">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="be8e9-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="be8e9-217">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="be8e9-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="be8e9-218">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="be8e9-218">Operator overloadability</span></span>

<span data-ttu-id="be8e9-219">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `!`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="be8e9-220">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="be8e9-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="be8e9-221">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="be8e9-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="be8e9-222">Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`.</span><span class="sxs-lookup"><span data-stu-id="be8e9-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="be8e9-223">При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="be8e9-223">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="be8e9-224">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="be8e9-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="be8e9-225">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="be8e9-225">C# language specification</span></span>

<span data-ttu-id="be8e9-226">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="be8e9-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="be8e9-227">Оператор логического отрицания</span><span class="sxs-lookup"><span data-stu-id="be8e9-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="be8e9-228">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="be8e9-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="be8e9-229">Условные логические операторы</span><span class="sxs-lookup"><span data-stu-id="be8e9-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="be8e9-230">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="be8e9-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="be8e9-231">См. также</span><span class="sxs-lookup"><span data-stu-id="be8e9-231">See also</span></span>

- [<span data-ttu-id="be8e9-232">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="be8e9-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="be8e9-233">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="be8e9-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="be8e9-234">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="be8e9-234">C# Operators</span></span>](index.md)
- [<span data-ttu-id="be8e9-235">Побитовые операторы и операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="be8e9-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
