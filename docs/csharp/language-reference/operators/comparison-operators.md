---
title: Операторы сравнения — справочник по C#
description: Дополнительные сведения об операторах сравнения C#, которые можно использовать для проверки очередности числовых значений.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: ea8d8ab5ac14ec94c647ed33cca6f949a90737bd
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431613"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="4a906-103">Операторы сравнения (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4a906-103">Comparison operators (C# Reference)</span></span>

<span data-ttu-id="4a906-104">Операторы сравнения [`<` (меньше чем)](#less-than-operator-), [`>` (больше чем)](#greater-than-operator-), [`<=` (меньше или равно)](#less-than-or-equal-operator-) и [`>=` (больше или равно)](#greater-than-or-equal-operator-) (или реляционные операторы) сравнивают операнды.</span><span class="sxs-lookup"><span data-stu-id="4a906-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="4a906-105">Эти операторы поддерживают все [целочисленные](../keywords/integral-types-table.md) типы и типы с [плавающей запятой](../keywords/floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="4a906-105">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="4a906-106">Если какой-то из операндов операторов `==`, `<`, `>`, `<=` и `>=` не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результатом операции будет `false`.</span><span class="sxs-lookup"><span data-stu-id="4a906-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="4a906-107">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`.</span><span class="sxs-lookup"><span data-stu-id="4a906-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="4a906-108">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a906-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="4a906-109">Типы перечисления также поддерживают операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="4a906-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="4a906-110">Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="4a906-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="4a906-111">Операторы [`==` и `!=`](equality-operators.md) проверяют равенство или неравенство своих операндов.</span><span class="sxs-lookup"><span data-stu-id="4a906-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="4a906-112">Оператор "меньше чем" \<</span><span class="sxs-lookup"><span data-stu-id="4a906-112">Less than operator \<</span></span>

<span data-ttu-id="4a906-113">Оператор `<` возвращает `true`, если его первый операнд меньше второго. В противном случае возвращается `false`:</span><span class="sxs-lookup"><span data-stu-id="4a906-113">The `<` operator returns `true` if its first operand is less than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="4a906-114">Оператор "больше чем" ></span><span class="sxs-lookup"><span data-stu-id="4a906-114">Greater than operator ></span></span>

<span data-ttu-id="4a906-115">Оператор `>` возвращает `true`, если его первый операнд больше второго. В противном случае возвращается `false`:</span><span class="sxs-lookup"><span data-stu-id="4a906-115">The `>` operator returns `true` if its first operand is greater than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="4a906-116">Оператор "меньше или равно" \<=</span><span class="sxs-lookup"><span data-stu-id="4a906-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="4a906-117">Оператор `<=` возвращает `true`, если его первый операнд меньше второго или они равны. В противном случае возвращается `false`:</span><span class="sxs-lookup"><span data-stu-id="4a906-117">The `<=` operator returns `true` if its first operand is less than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="4a906-118">Оператор "больше или равно" >=</span><span class="sxs-lookup"><span data-stu-id="4a906-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="4a906-119">Оператор `>=` возвращает `true`, если его первый операнд больше второго или они равны. В противном случае возвращается `false`:</span><span class="sxs-lookup"><span data-stu-id="4a906-119">The `>=` operator returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="4a906-120">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="4a906-120">Operator overloadability</span></span>

<span data-ttu-id="4a906-121">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `<`, `>`, `<=` и `>=`.</span><span class="sxs-lookup"><span data-stu-id="4a906-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="4a906-122">Если тип перегружает один из операторов `<` и `>`, он должен также перегружать операторы `<` и `>`.</span><span class="sxs-lookup"><span data-stu-id="4a906-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="4a906-123">Если тип перегружает один из операторов `<=` и `>=`, он должен также перегружать операторы `<=` и `>=`.</span><span class="sxs-lookup"><span data-stu-id="4a906-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4a906-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4a906-124">C# language specification</span></span>

<span data-ttu-id="4a906-125">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4a906-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a906-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4a906-126">See also</span></span>

- [<span data-ttu-id="4a906-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4a906-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4a906-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4a906-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4a906-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4a906-129">C# Operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="4a906-130">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="4a906-130">Equality operators</span></span>](equality-operators.md)
