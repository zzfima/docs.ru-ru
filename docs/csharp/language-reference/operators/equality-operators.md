---
title: Операторы равенства — справочник по C#
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 98b96f5b4c6d6ea70687a97c849e89573c67c37e
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545899"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="2e468-102">Операторы равенства (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2e468-102">Equality operators (C# Reference)</span></span>

<span data-ttu-id="2e468-103">Операторы [`==` (равенство)](#equality-operator-) и [`!=` (неравенство)](#inequality-operator-) проверяют равенство или неравенство своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2e468-103">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="2e468-104">Оператор равенства ==</span><span class="sxs-lookup"><span data-stu-id="2e468-104">Equality operator ==</span></span>

<span data-ttu-id="2e468-105">Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2e468-105">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="2e468-106">Равенство типов значений</span><span class="sxs-lookup"><span data-stu-id="2e468-106">Value types equality</span></span>

<span data-ttu-id="2e468-107">Операнды [встроенных типов значений](../keywords/value-types-table.md) равны, если равны их значения.</span><span class="sxs-lookup"><span data-stu-id="2e468-107">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="2e468-108">Если для операторов равенства и отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2e468-108">For equality and relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="2e468-109">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`.</span><span class="sxs-lookup"><span data-stu-id="2e468-109">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="2e468-110">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e468-110">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="2e468-111">Два операнда одного типа [enum](../keywords/enum.md) равны, если равны соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="2e468-111">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="2e468-112">По умолчанию пользовательские типы [struct](../keywords/struct.md) не поддерживают оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="2e468-112">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="2e468-113">Чтобы поддерживать оператор `==`, пользовательская структура должна [перегружать](#operator-overloadability) его.</span><span class="sxs-lookup"><span data-stu-id="2e468-113">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="2e468-114">Начиная с версии C# 7.3 операторы `==` и `!=` поддерживаются [кортежами](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="2e468-114">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="2e468-115">Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="2e468-115">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="2e468-116">Равенство строк</span><span class="sxs-lookup"><span data-stu-id="2e468-116">String equality</span></span>

<span data-ttu-id="2e468-117">Два операнда [string](../keywords/string.md) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.</span><span class="sxs-lookup"><span data-stu-id="2e468-117">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="2e468-118">Это порядковое сравнение, учитывающее регистр.</span><span class="sxs-lookup"><span data-stu-id="2e468-118">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="2e468-119">Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="2e468-119">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="2e468-120">Равенство ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="2e468-120">Reference types equality</span></span>

<span data-ttu-id="2e468-121">Два операнда, отличных от операндов ссылочного типа `string`, являются равными, если они ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="2e468-121">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="2e468-122">Как показано в примере, определяемые пользователем ссылочные типы поддерживают оператор `==` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e468-122">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="2e468-123">Однако определяемый пользователем ссылочный тип может перегружать оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="2e468-123">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="2e468-124">Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="2e468-124">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="2e468-125">Оператор неравенства !=</span><span class="sxs-lookup"><span data-stu-id="2e468-125">Inequality operator !=</span></span>

<span data-ttu-id="2e468-126">Оператор неравенства `!=` возвращает значение `true`, если его операнды не равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2e468-126">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="2e468-127">Для операндов [встроенных типов](../keywords/built-in-types-table.md) выражение `x != y` дает тот же результат, что и выражение `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="2e468-127">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="2e468-128">Дополнительные сведения о равенстве типов см. в разделе [Оператор равенства](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="2e468-128">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="2e468-129">В следующем примере иллюстрируется использование оператора `!=`.</span><span class="sxs-lookup"><span data-stu-id="2e468-129">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="2e468-130">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="2e468-130">Operator overloadability</span></span>

<span data-ttu-id="2e468-131">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) операторы `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="2e468-131">User-defined types can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="2e468-132">Если тип перегружает один из двух операторов, он должен также перегружать и другой.</span><span class="sxs-lookup"><span data-stu-id="2e468-132">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2e468-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2e468-133">C# language specification</span></span>

<span data-ttu-id="2e468-134">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2e468-134">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e468-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2e468-135">See also</span></span>

- [<span data-ttu-id="2e468-136">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2e468-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2e468-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2e468-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2e468-138">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2e468-138">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2e468-139">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="2e468-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
