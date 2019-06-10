---
title: Операторы равенства — справочник по C#
description: Дополнительные сведения об операторах сравнения на равенство в C#.
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 3b2aeceae8371f0728da2bcebbbe597ee135f256
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758268"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="e1d0f-103">Операторы равенства (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e1d0f-103">Equality operators (C# Reference)</span></span>

<span data-ttu-id="e1d0f-104">Операторы [`==` (равенство)](#equality-operator-) и [`!=` (неравенство)](#inequality-operator-) проверяют равенство или неравенство своих операндов.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="e1d0f-105">Оператор равенства ==</span><span class="sxs-lookup"><span data-stu-id="e1d0f-105">Equality operator ==</span></span>

<span data-ttu-id="e1d0f-106">Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="e1d0f-107">Равенство типов значений</span><span class="sxs-lookup"><span data-stu-id="e1d0f-107">Value types equality</span></span>

<span data-ttu-id="e1d0f-108">Операнды [встроенных типов значений](../keywords/value-types-table.md) равны, если равны их значения.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-108">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="e1d0f-109">У операторов `==`, [`<`, `>`, `<=` и `>=`](comparison-operators.md), если какой-то из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результатом операции является `false`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="e1d0f-110">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="e1d0f-111">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="e1d0f-112">Два операнда одного типа [enum](../keywords/enum.md) равны, если равны соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-112">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="e1d0f-113">По умолчанию пользовательские типы [struct](../keywords/struct.md) не поддерживают оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="e1d0f-114">Чтобы поддерживать оператор `==`, пользовательская структура должна [перегружать](#operator-overloadability) его.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-114">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="e1d0f-115">Начиная с версии C# 7.3 операторы `==` и `!=` поддерживаются [кортежами](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="e1d0f-116">Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="e1d0f-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="e1d0f-117">Равенство строк</span><span class="sxs-lookup"><span data-stu-id="e1d0f-117">String equality</span></span>

<span data-ttu-id="e1d0f-118">Два операнда [string](../keywords/string.md) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-118">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="e1d0f-119">Это порядковое сравнение, учитывающее регистр.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-119">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="e1d0f-120">Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="e1d0f-120">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="e1d0f-121">Равенство ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="e1d0f-121">Reference types equality</span></span>

<span data-ttu-id="e1d0f-122">Два операнда, отличных от операндов ссылочного типа `string`, являются равными, если они ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-122">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="e1d0f-123">Как показано в примере, определяемые пользователем ссылочные типы поддерживают оператор `==` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-123">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="e1d0f-124">Однако определяемый пользователем ссылочный тип может перегружать оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-124">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="e1d0f-125">Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-125">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="e1d0f-126">Оператор неравенства !=</span><span class="sxs-lookup"><span data-stu-id="e1d0f-126">Inequality operator !=</span></span>

<span data-ttu-id="e1d0f-127">Оператор неравенства `!=` возвращает значение `true`, если его операнды не равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-127">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="e1d0f-128">Для операндов [встроенных типов](../keywords/built-in-types-table.md) выражение `x != y` дает тот же результат, что и выражение `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-128">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="e1d0f-129">Дополнительные сведения о равенстве типов см. в разделе [Оператор равенства](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="e1d0f-129">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="e1d0f-130">В следующем примере иллюстрируется использование оператора `!=`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-130">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="e1d0f-131">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="e1d0f-131">Operator overloadability</span></span>

<span data-ttu-id="e1d0f-132">Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-132">A user-defined type can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="e1d0f-133">Если тип перегружает один из двух операторов, он должен также перегружать и другой.</span><span class="sxs-lookup"><span data-stu-id="e1d0f-133">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e1d0f-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e1d0f-134">C# language specification</span></span>

<span data-ttu-id="e1d0f-135">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e1d0f-135">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1d0f-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e1d0f-136">See also</span></span>

- [<span data-ttu-id="e1d0f-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e1d0f-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e1d0f-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e1d0f-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e1d0f-139">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e1d0f-139">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e1d0f-140">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="e1d0f-140">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="e1d0f-141">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="e1d0f-141">Comparison operators</span></span>](comparison-operators.md)
