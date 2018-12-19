---
title: Справочник по C#. Оператор ||
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: f4bb7ada12fbcebcb90fb7cd22d6e6bccad5fb57
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244574"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4fdc1-102">Оператор || (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4fdc1-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="4fdc1-103">Условный логический оператор ИЛИ `||`, также известный как "сокращенный" логический оператор ИЛИ, вычисляет логическое ИЛИ операндов типа [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="4fdc1-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="4fdc1-104">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="4fdc1-105">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="4fdc1-106">Если результатом первого операнда является значение `true`, второй операнд не вычисляется, и результат принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="4fdc1-107">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="4fdc1-108">[Логический оператор ИЛИ](or-operator.md) `|` также вычисляет логическое ИЛИ операндов типа `bool`, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4fdc1-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="4fdc1-109">Operator overloadability</span></span>

<span data-ttu-id="4fdc1-110">Определяемый пользователем тип не может перегружать условный логический оператор ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="4fdc1-111">Тем не менее, если определяемый пользователем тип каким-либо образом перегружает операторы [логическое OR](or-operator.md), [true и false](../keywords/true-false-operators.md), то операция `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="4fdc1-111">However, if a user-defined type overloads the [logical OR](or-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="4fdc1-112">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4fdc1-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4fdc1-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4fdc1-113">C# language specification</span></span>

<span data-ttu-id="4fdc1-114">Дополнительные сведения см. в разделе [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4fdc1-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fdc1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4fdc1-115">See also</span></span>

- [<span data-ttu-id="4fdc1-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4fdc1-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4fdc1-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4fdc1-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4fdc1-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4fdc1-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="4fdc1-119">Оператор &&</span><span class="sxs-lookup"><span data-stu-id="4fdc1-119">&& operator</span></span>](conditional-and-operator.md)
- [<span data-ttu-id="4fdc1-120">Оператор !</span><span class="sxs-lookup"><span data-stu-id="4fdc1-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="4fdc1-121">Оператор |</span><span class="sxs-lookup"><span data-stu-id="4fdc1-121">| operator</span></span>](or-operator.md)
