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
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427322"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="7ccca-103">Справочник по C#. Логические операторы</span><span class="sxs-lookup"><span data-stu-id="7ccca-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="7ccca-104">Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:</span><span class="sxs-lookup"><span data-stu-id="7ccca-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="7ccca-105">Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.</span><span class="sxs-lookup"><span data-stu-id="7ccca-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="7ccca-106">Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="7ccca-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="7ccca-107">Эти операторы всегда обрабатывают оба операнда.</span><span class="sxs-lookup"><span data-stu-id="7ccca-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="7ccca-108">Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="7ccca-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="7ccca-109">Эти операторы вычисляют второй операнд, только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="7ccca-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="7ccca-110">Для операндов типа [integral](../keywords/integral-types-table.md) операторы `&`, `|` и `^` выполняют побитовые логические операции.</span><span class="sxs-lookup"><span data-stu-id="7ccca-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="7ccca-111">Оператор логического отрицания !</span><span class="sxs-lookup"><span data-stu-id="7ccca-111">Logical negation operator !</span></span>

<span data-ttu-id="7ccca-112">Оператор `!` выполняет логическое отрицание операнда,</span><span class="sxs-lookup"><span data-stu-id="7ccca-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="7ccca-113">возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="7ccca-114">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="7ccca-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="7ccca-115">Оператор `&` вычисляет логическое И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="7ccca-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="7ccca-116">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="7ccca-117">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="7ccca-118">Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="7ccca-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="7ccca-119">В следующем примере второй операнд оператора `&` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="7ccca-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="7ccca-120">[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но он не вычисляет второй операнд, если первый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="7ccca-121">Для операндов оператор типа integral оператор `&` выполняет [побитовое вычисление логического И](and-operator.md#integer-logical-bitwise-and-operator).</span><span class="sxs-lookup"><span data-stu-id="7ccca-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="7ccca-122">Унарный оператор `&` является оператором [AddressOf](and-operator.md#unary-address-of-operator).</span><span class="sxs-lookup"><span data-stu-id="7ccca-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="7ccca-123">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="7ccca-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="7ccca-124">Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов,</span><span class="sxs-lookup"><span data-stu-id="7ccca-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="7ccca-125">возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="7ccca-126">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="7ccca-127">То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="7ccca-128">Для операндов типа integral оператор `^` выполняет [побитовое вычисление исключающего логического ИЛИ](xor-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ccca-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="7ccca-129">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="7ccca-129">Logical OR operator |</span></span>

<span data-ttu-id="7ccca-130">Оператор `|` вычисляет логическое ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="7ccca-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="7ccca-131">Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="7ccca-132">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="7ccca-133">Оператор `|` вычисляет оба операнда, даже если первый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="7ccca-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="7ccca-134">В следующем примере второй операнд оператора `|` является вызовом метода, который выполняется независимо от значения первого операнда:</span><span class="sxs-lookup"><span data-stu-id="7ccca-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="7ccca-135">[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет второй операнд, если первый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="7ccca-136">Для операндов типа integral оператор `|` выполняет [побитовое вычисление логического ИЛИ](or-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ccca-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="7ccca-137">Условный оператор логического И &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="7ccca-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="7ccca-138">Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="7ccca-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="7ccca-139">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="7ccca-140">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="7ccca-141">Если результатом первого операнда является значение `false`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="7ccca-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="7ccca-142">В следующем примере второй операнд оператора `&&` является вызовом метода, который не выполняется, если первый операнд имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="7ccca-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="7ccca-143">[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="7ccca-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="7ccca-144">Условный оператор логического ИЛИ ||</span><span class="sxs-lookup"><span data-stu-id="7ccca-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="7ccca-145">Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="7ccca-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="7ccca-146">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="7ccca-147">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="7ccca-148">Если результатом первого операнда является значение `true`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="7ccca-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="7ccca-149">В следующем примере второй операнд оператора `||` является вызовом метода, который не выполняется, если первый операнд имеет значение `true`:</span><span class="sxs-lookup"><span data-stu-id="7ccca-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="7ccca-150">[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="7ccca-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="7ccca-151">Операторы, допускающие логическое значение NULL</span><span class="sxs-lookup"><span data-stu-id="7ccca-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="7ccca-152">Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="7ccca-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="7ccca-153">Семантика этих операторов определяется по следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="7ccca-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="7ccca-154">x</span><span class="sxs-lookup"><span data-stu-id="7ccca-154">x</span></span>|<span data-ttu-id="7ccca-155">y</span><span class="sxs-lookup"><span data-stu-id="7ccca-155">y</span></span>|<span data-ttu-id="7ccca-156">x&y</span><span class="sxs-lookup"><span data-stu-id="7ccca-156">x&y</span></span>|<span data-ttu-id="7ccca-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="7ccca-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="7ccca-158">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-158">true</span></span>|<span data-ttu-id="7ccca-159">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-159">true</span></span>|<span data-ttu-id="7ccca-160">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-160">true</span></span>|<span data-ttu-id="7ccca-161">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-161">true</span></span>|  
|<span data-ttu-id="7ccca-162">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-162">true</span></span>|<span data-ttu-id="7ccca-163">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-163">false</span></span>|<span data-ttu-id="7ccca-164">false</span><span class="sxs-lookup"><span data-stu-id="7ccca-164">false</span></span>|<span data-ttu-id="7ccca-165">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-165">true</span></span>|  
|<span data-ttu-id="7ccca-166">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-166">true</span></span>|<span data-ttu-id="7ccca-167">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-167">null</span></span>|<span data-ttu-id="7ccca-168">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-168">null</span></span>|<span data-ttu-id="7ccca-169">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-169">true</span></span>|  
|<span data-ttu-id="7ccca-170">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-170">false</span></span>|<span data-ttu-id="7ccca-171">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-171">true</span></span>|<span data-ttu-id="7ccca-172">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-172">false</span></span>|<span data-ttu-id="7ccca-173">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-173">true</span></span>|  
|<span data-ttu-id="7ccca-174">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-174">false</span></span>|<span data-ttu-id="7ccca-175">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-175">false</span></span>|<span data-ttu-id="7ccca-176">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-176">false</span></span>|<span data-ttu-id="7ccca-177">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-177">false</span></span>|  
|<span data-ttu-id="7ccca-178">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-178">false</span></span>|<span data-ttu-id="7ccca-179">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-179">null</span></span>|<span data-ttu-id="7ccca-180">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-180">false</span></span>|<span data-ttu-id="7ccca-181">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-181">null</span></span>|  
|<span data-ttu-id="7ccca-182">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-182">null</span></span>|<span data-ttu-id="7ccca-183">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-183">true</span></span>|<span data-ttu-id="7ccca-184">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-184">null</span></span>|<span data-ttu-id="7ccca-185">true</span><span class="sxs-lookup"><span data-stu-id="7ccca-185">true</span></span>|  
|<span data-ttu-id="7ccca-186">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-186">null</span></span>|<span data-ttu-id="7ccca-187">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-187">false</span></span>|<span data-ttu-id="7ccca-188">False</span><span class="sxs-lookup"><span data-stu-id="7ccca-188">false</span></span>|<span data-ttu-id="7ccca-189">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-189">null</span></span>|  
|<span data-ttu-id="7ccca-190">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-190">null</span></span>|<span data-ttu-id="7ccca-191">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-191">null</span></span>|<span data-ttu-id="7ccca-192">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-192">null</span></span>|<span data-ttu-id="7ccca-193">null</span><span class="sxs-lookup"><span data-stu-id="7ccca-193">null</span></span>|  

<span data-ttu-id="7ccca-194">Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7ccca-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="7ccca-195">Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7ccca-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="7ccca-196">Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="7ccca-197">При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="7ccca-198">См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="7ccca-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="7ccca-199">Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7ccca-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="7ccca-200">Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="7ccca-201">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="7ccca-201">Compound assignment</span></span>

<span data-ttu-id="7ccca-202">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="7ccca-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="7ccca-203">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="7ccca-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="7ccca-204">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="7ccca-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="7ccca-205">Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7ccca-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="7ccca-206">Условные логические операторы `&&` и `||` не поддерживают составное присваивание.</span><span class="sxs-lookup"><span data-stu-id="7ccca-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="7ccca-207">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="7ccca-207">Operator precedence</span></span>

<span data-ttu-id="7ccca-208">В следующем списке перечислены логические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="7ccca-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="7ccca-209">Оператор логического отрицания:</span><span class="sxs-lookup"><span data-stu-id="7ccca-209">Logical negation operator</span></span> `!`
- <span data-ttu-id="7ccca-210">Логический оператор AND</span><span class="sxs-lookup"><span data-stu-id="7ccca-210">Logical AND operator</span></span> `&`
- <span data-ttu-id="7ccca-211">Оператор исключающего логического ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7ccca-211">Logical exclusive OR operator</span></span> `^`
- <span data-ttu-id="7ccca-212">Логический оператор ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7ccca-212">Logical OR operator</span></span> `|`
- <span data-ttu-id="7ccca-213">Условный оператор логического И</span><span class="sxs-lookup"><span data-stu-id="7ccca-213">Conditional logical AND operator</span></span> `&&`
- <span data-ttu-id="7ccca-214">Условный оператор логического ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7ccca-214">Conditional logical OR operator</span></span> `||`

<span data-ttu-id="7ccca-215">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="7ccca-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="7ccca-216">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="7ccca-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7ccca-217">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="7ccca-217">Operator overloadability</span></span>

<span data-ttu-id="7ccca-218">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `!`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="7ccca-219">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="7ccca-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="7ccca-220">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="7ccca-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="7ccca-221">Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`.</span><span class="sxs-lookup"><span data-stu-id="7ccca-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="7ccca-222">При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](../keywords/true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="7ccca-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="7ccca-223">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7ccca-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7ccca-224">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7ccca-224">C# language specification</span></span>

<span data-ttu-id="7ccca-225">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="7ccca-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="7ccca-226">Оператор логического отрицания:</span><span class="sxs-lookup"><span data-stu-id="7ccca-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="7ccca-227">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="7ccca-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="7ccca-228">Условные логические операторы</span><span class="sxs-lookup"><span data-stu-id="7ccca-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="7ccca-229">См. также</span><span class="sxs-lookup"><span data-stu-id="7ccca-229">See also</span></span>

- [<span data-ttu-id="7ccca-230">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7ccca-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7ccca-231">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7ccca-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7ccca-232">Операторы C#</span><span class="sxs-lookup"><span data-stu-id="7ccca-232">C# Operators</span></span>](index.md)
