---
title: Справочник по C#. Оператор !=
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610181"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="77cc8-102">Оператор != (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="77cc8-102">!= Operator (C# Reference)</span></span>

<span data-ttu-id="77cc8-103">Оператор неравенства `!=` возвращает значение `true`, если его операнды не равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="77cc8-103">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="77cc8-104">Для операндов [встроенных типов](../keywords/built-in-types-table.md) выражение `x != y` дает тот же результат, что и выражение `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="77cc8-104">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="77cc8-105">Дополнительные сведения см. в статье [Оператор ==](equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="77cc8-105">For more information, see the [== Operator](equality-comparison-operator.md) article.</span></span>

<span data-ttu-id="77cc8-106">В следующем примере иллюстрируется использование оператора `!=`.</span><span class="sxs-lookup"><span data-stu-id="77cc8-106">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="77cc8-107">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="77cc8-107">Operator overloadability</span></span>

<span data-ttu-id="77cc8-108">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `!=`.</span><span class="sxs-lookup"><span data-stu-id="77cc8-108">User-defined types can [overload](../keywords/operator.md) the `!=` operator.</span></span> <span data-ttu-id="77cc8-109">Если тип перегружает оператор неравенства `!=`, он также должен перегружать [оператор равенства](equality-comparison-operator.md) `==`.</span><span class="sxs-lookup"><span data-stu-id="77cc8-109">If a type overloads the inequality operator `!=`, it must also overload the [equality operator](equality-comparison-operator.md) `==`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="77cc8-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="77cc8-110">C# language specification</span></span>

<span data-ttu-id="77cc8-111">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="77cc8-111">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77cc8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="77cc8-112">See also</span></span>

- [<span data-ttu-id="77cc8-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="77cc8-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="77cc8-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="77cc8-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="77cc8-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="77cc8-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="77cc8-116">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="77cc8-116">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
