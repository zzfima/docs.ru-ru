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
ms.openlocfilehash: b666c915506872930b16c1c5890de24e9cbe4f7a
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880570"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="d0d5e-103">Справочник по C#. Логические операторы</span><span class="sxs-lookup"><span data-stu-id="d0d5e-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="d0d5e-104">Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="d0d5e-105">Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="d0d5e-106">Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="d0d5e-107">Эти операторы всегда обрабатывают оба операнда.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="d0d5e-108">Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="d0d5e-109">Эти операторы вычисляют второй операнд, только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="d0d5e-110">Для операндов [целочисленных](../keywords/integral-types-table.md) типов операторы `&`, `|` и `^` выполняют побитовые логические операции.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-110">For the operands of the [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="d0d5e-111">Дополнительные сведения см. в разделе [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="d0d5e-112">Оператор логического отрицания !</span><span class="sxs-lookup"><span data-stu-id="d0d5e-112">Logical negation operator !</span></span>

<span data-ttu-id="d0d5e-113">Оператор `!` выполняет логическое отрицание операнда,</span><span class="sxs-lookup"><span data-stu-id="d0d5e-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="d0d5e-114">возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="d0d5e-115">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="d0d5e-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="d0d5e-116">Оператор `&` вычисляет логическое И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="d0d5e-117">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="d0d5e-118">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="d0d5e-119">Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-119">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="d0d5e-120">В следующем примере второй операнд оператора `&` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-120">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="d0d5e-121">[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но он не вычисляет второй операнд, если первый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="d0d5e-122">Для операндов целочисленного типа оператор `&` вычисляет [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="d0d5e-123">Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="d0d5e-124">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="d0d5e-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="d0d5e-125">Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов,</span><span class="sxs-lookup"><span data-stu-id="d0d5e-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="d0d5e-126">возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="d0d5e-127">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="d0d5e-128">То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="d0d5e-129">Для операндов целочисленного типа оператор `^` вычисляет [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="d0d5e-130">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="d0d5e-130">Logical OR operator |</span></span>

<span data-ttu-id="d0d5e-131">Оператор `|` вычисляет логическое ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="d0d5e-132">Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="d0d5e-133">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="d0d5e-134">Оператор `|` вычисляет оба операнда, даже если первый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-134">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="d0d5e-135">В следующем примере второй операнд оператора `|` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-135">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="d0d5e-136">[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет второй операнд, если первый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="d0d5e-137">Для операндов целочисленного типа оператор `|` вычисляет [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="d0d5e-138">Условный оператор логического И &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="d0d5e-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="d0d5e-139">Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="d0d5e-140">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="d0d5e-141">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="d0d5e-142">Если результатом первого операнда является значение `false`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-142">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="d0d5e-143">В следующем примере второй операнд оператора `&&` является вызовом метода, который не выполняется, если первый операнд имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-143">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="d0d5e-144">[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="d0d5e-145">Условный оператор логического ИЛИ ||</span><span class="sxs-lookup"><span data-stu-id="d0d5e-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="d0d5e-146">Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="d0d5e-147">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="d0d5e-148">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="d0d5e-149">Если результатом первого операнда является значение `true`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-149">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="d0d5e-150">В следующем примере второй операнд оператора `||` является вызовом метода, который не выполняется, если первый операнд имеет значение `true`:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-150">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="d0d5e-151">[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="d0d5e-152">Операторы, допускающие логическое значение NULL</span><span class="sxs-lookup"><span data-stu-id="d0d5e-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="d0d5e-153">Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="d0d5e-154">Семантика этих операторов определяется по следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="d0d5e-155">x</span><span class="sxs-lookup"><span data-stu-id="d0d5e-155">x</span></span>|<span data-ttu-id="d0d5e-156">y</span><span class="sxs-lookup"><span data-stu-id="d0d5e-156">y</span></span>|<span data-ttu-id="d0d5e-157">x&y</span><span class="sxs-lookup"><span data-stu-id="d0d5e-157">x&y</span></span>|<span data-ttu-id="d0d5e-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="d0d5e-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="d0d5e-159">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-159">true</span></span>|<span data-ttu-id="d0d5e-160">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-160">true</span></span>|<span data-ttu-id="d0d5e-161">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-161">true</span></span>|<span data-ttu-id="d0d5e-162">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-162">true</span></span>|  
|<span data-ttu-id="d0d5e-163">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-163">true</span></span>|<span data-ttu-id="d0d5e-164">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-164">false</span></span>|<span data-ttu-id="d0d5e-165">false</span><span class="sxs-lookup"><span data-stu-id="d0d5e-165">false</span></span>|<span data-ttu-id="d0d5e-166">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-166">true</span></span>|  
|<span data-ttu-id="d0d5e-167">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-167">true</span></span>|<span data-ttu-id="d0d5e-168">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-168">null</span></span>|<span data-ttu-id="d0d5e-169">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-169">null</span></span>|<span data-ttu-id="d0d5e-170">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-170">true</span></span>|  
|<span data-ttu-id="d0d5e-171">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-171">false</span></span>|<span data-ttu-id="d0d5e-172">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-172">true</span></span>|<span data-ttu-id="d0d5e-173">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-173">false</span></span>|<span data-ttu-id="d0d5e-174">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-174">true</span></span>|  
|<span data-ttu-id="d0d5e-175">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-175">false</span></span>|<span data-ttu-id="d0d5e-176">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-176">false</span></span>|<span data-ttu-id="d0d5e-177">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-177">false</span></span>|<span data-ttu-id="d0d5e-178">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-178">false</span></span>|  
|<span data-ttu-id="d0d5e-179">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-179">false</span></span>|<span data-ttu-id="d0d5e-180">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-180">null</span></span>|<span data-ttu-id="d0d5e-181">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-181">false</span></span>|<span data-ttu-id="d0d5e-182">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-182">null</span></span>|  
|<span data-ttu-id="d0d5e-183">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-183">null</span></span>|<span data-ttu-id="d0d5e-184">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-184">true</span></span>|<span data-ttu-id="d0d5e-185">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-185">null</span></span>|<span data-ttu-id="d0d5e-186">true</span><span class="sxs-lookup"><span data-stu-id="d0d5e-186">true</span></span>|  
|<span data-ttu-id="d0d5e-187">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-187">null</span></span>|<span data-ttu-id="d0d5e-188">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-188">false</span></span>|<span data-ttu-id="d0d5e-189">False</span><span class="sxs-lookup"><span data-stu-id="d0d5e-189">false</span></span>|<span data-ttu-id="d0d5e-190">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-190">null</span></span>|  
|<span data-ttu-id="d0d5e-191">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-191">null</span></span>|<span data-ttu-id="d0d5e-192">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-192">null</span></span>|<span data-ttu-id="d0d5e-193">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-193">null</span></span>|<span data-ttu-id="d0d5e-194">null</span><span class="sxs-lookup"><span data-stu-id="d0d5e-194">null</span></span>|  

<span data-ttu-id="d0d5e-195">Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="d0d5e-196">Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="d0d5e-197">Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="d0d5e-198">При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="d0d5e-199">См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="d0d5e-200">Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="d0d5e-201">Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="d0d5e-202">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="d0d5e-202">Compound assignment</span></span>

<span data-ttu-id="d0d5e-203">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="d0d5e-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="d0d5e-204">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="d0d5e-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="d0d5e-205">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="d0d5e-206">Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="d0d5e-207">Условные логические операторы `&&` и `||` не поддерживают составное присваивание.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="d0d5e-208">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="d0d5e-208">Operator precedence</span></span>

<span data-ttu-id="d0d5e-209">В следующем списке перечислены логические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="d0d5e-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="d0d5e-210">Оператор логического отрицания `!`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="d0d5e-211">Оператор логического И `&`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="d0d5e-212">Оператор логического исключающего ИЛИ `^`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="d0d5e-213">Оператор логического ИЛИ `|`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="d0d5e-214">Условный оператор логического И `&&`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="d0d5e-215">Условный оператор логического ИЛИ `||`</span><span class="sxs-lookup"><span data-stu-id="d0d5e-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="d0d5e-216">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="d0d5e-217">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d0d5e-218">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="d0d5e-218">Operator overloadability</span></span>

<span data-ttu-id="d0d5e-219">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `!`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="d0d5e-220">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="d0d5e-221">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="d0d5e-222">Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="d0d5e-223">При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](../keywords/true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="d0d5e-223">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="d0d5e-224">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5e-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d0d5e-225">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d0d5e-225">C# language specification</span></span>

<span data-ttu-id="d0d5e-226">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="d0d5e-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="d0d5e-227">Оператор логического отрицания</span><span class="sxs-lookup"><span data-stu-id="d0d5e-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="d0d5e-228">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="d0d5e-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="d0d5e-229">Условные логические операторы</span><span class="sxs-lookup"><span data-stu-id="d0d5e-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="d0d5e-230">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="d0d5e-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="d0d5e-231">См. также</span><span class="sxs-lookup"><span data-stu-id="d0d5e-231">See also</span></span>

- [<span data-ttu-id="d0d5e-232">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d0d5e-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d0d5e-233">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d0d5e-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d0d5e-234">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d0d5e-234">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d0d5e-235">Побитовые операторы и операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="d0d5e-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
