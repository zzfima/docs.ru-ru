---
title: Оператор &amp;&amp; (справочник по C#)
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529239"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="45a91-102">Оператор &amp;&amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="45a91-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="45a91-103">Условный логический оператор И `&&`, также известный как "сокращенный" логический оператор И, вычисляет логическое И операндов типа [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="45a91-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="45a91-104">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="45a91-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="45a91-105">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="45a91-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="45a91-106">Если результатом первого операнда является значение `false`, второй операнд не вычисляется, и результат принимает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="45a91-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="45a91-107">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="45a91-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="45a91-108">[Логический оператор И](and-operator.md) `&` также вычисляет логическое И операндов типа `bool`, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="45a91-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="45a91-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="45a91-109">Operator overloadability</span></span>

<span data-ttu-id="45a91-110">Определяемый пользователем тип не может перегружать условный логический оператор И.</span><span class="sxs-lookup"><span data-stu-id="45a91-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="45a91-111">Тем не менее, если определяемый пользователем тип каким-либо образом перегружает операторы [логическое И](and-operator.md), [true](../keywords/true-operator.md) и [false](../keywords/false-operator.md), то операция `&&` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="45a91-111">However, if a user-defined type overloads the [logical AND](and-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="45a91-112">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="45a91-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="45a91-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="45a91-113">C# language specification</span></span>

<span data-ttu-id="45a91-114">Дополнительные сведения см. в разделе [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="45a91-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45a91-115">См. также</span><span class="sxs-lookup"><span data-stu-id="45a91-115">See also</span></span>

- [<span data-ttu-id="45a91-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="45a91-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="45a91-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="45a91-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="45a91-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="45a91-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="45a91-119">Оператор ||</span><span class="sxs-lookup"><span data-stu-id="45a91-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="45a91-120">Оператор !</span><span class="sxs-lookup"><span data-stu-id="45a91-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="45a91-121">Оператор &</span><span class="sxs-lookup"><span data-stu-id="45a91-121">& operator</span></span>](and-operator.md)
