---
title: Справочник по C#. Оператор &amp;&amp;
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 82442f50275f21e0a0748951dc50628a8d7e11bb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243601"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="8f6d1-102">Оператор &amp;&amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8f6d1-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="8f6d1-103">Условный логический оператор И `&&`, также известный как "сокращенный" логический оператор И, вычисляет логическое И операндов типа [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="8f6d1-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="8f6d1-104">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="8f6d1-105">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="8f6d1-106">Если результатом первого операнда является значение `false`, второй операнд не вычисляется, и результат принимает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="8f6d1-107">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="8f6d1-108">[Логический оператор И](and-operator.md) `&` также вычисляет логическое И операндов типа `bool`, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8f6d1-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="8f6d1-109">Operator overloadability</span></span>

<span data-ttu-id="8f6d1-110">Определяемый пользователем тип не может перегружать условный логический оператор И.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="8f6d1-111">Тем не менее, если определяемый пользователем тип каким-либо образом перегружает операторы [логическое AND](and-operator.md), [true и false](../keywords/true-false-operators.md), то операция `&&` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="8f6d1-111">However, if a user-defined type overloads the [logical AND](and-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="8f6d1-112">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f6d1-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8f6d1-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8f6d1-113">C# language specification</span></span>

<span data-ttu-id="8f6d1-114">Дополнительные сведения см. в разделе [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f6d1-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f6d1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8f6d1-115">See also</span></span>

- [<span data-ttu-id="8f6d1-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8f6d1-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8f6d1-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8f6d1-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8f6d1-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8f6d1-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="8f6d1-119">Оператор ||</span><span class="sxs-lookup"><span data-stu-id="8f6d1-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="8f6d1-120">Оператор \!</span><span class="sxs-lookup"><span data-stu-id="8f6d1-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="8f6d1-121">Оператор &</span><span class="sxs-lookup"><span data-stu-id="8f6d1-121">& operator</span></span>](and-operator.md)
