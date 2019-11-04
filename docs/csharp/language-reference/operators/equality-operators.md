---
title: Операторы равенства. Справочник по C#
description: Из этой статьи вы узнаете об операторах сравнения на равенство и типах равенства в C#.
ms.date: 06/26/2019
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
ms.openlocfilehash: 11d2161004af5199d9e501f8ab1e3c0382e6bfe7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039026"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="e5ec2-103">Операторы равенства (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e5ec2-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="e5ec2-104">Операторы [`==` (равенство)](#equality-operator-) и [`!=` (неравенство)](#inequality-operator-) проверяют равенство или неравенство своих операндов.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="e5ec2-105">Оператор равенства ==</span><span class="sxs-lookup"><span data-stu-id="e5ec2-105">Equality operator ==</span></span>

<span data-ttu-id="e5ec2-106">Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="e5ec2-107">Равенство типов значений</span><span class="sxs-lookup"><span data-stu-id="e5ec2-107">Value types equality</span></span>

<span data-ttu-id="e5ec2-108">Операнды [встроенных типов значений](../keywords/value-types-table.md) равны, если равны их значения.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-108">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="e5ec2-109">У операторов `==`, [`<`, `>`, `<=` и `>=`](comparison-operators.md), если какой-то из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результатом операции является `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="e5ec2-110">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="e5ec2-111">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="e5ec2-112">Два операнда одного типа [enum](../keywords/enum.md) равны, если равны соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-112">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="e5ec2-113">По умолчанию пользовательские типы [struct](../keywords/struct.md) не поддерживают оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="e5ec2-114">Чтобы поддерживать оператор `==`, пользовательская структура должна [перегружать](operator-overloading.md) его.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-114">To support the `==` operator, a user-defined struct must [overload](operator-overloading.md) it.</span></span>

<span data-ttu-id="e5ec2-115">Начиная с версии C# 7.3 операторы `==` и `!=` поддерживаются [кортежами](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="e5ec2-116">Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="e5ec2-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="e5ec2-117">Равенство ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="e5ec2-117">Reference types equality</span></span>

<span data-ttu-id="e5ec2-118">По умолчанию два операнда ссылочного типа являются равными, если они ссылаются на один и тот же объект:</span><span class="sxs-lookup"><span data-stu-id="e5ec2-118">By default, two reference-type operands are equal if they refer to the same object:</span></span>

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="e5ec2-119">Как показано в примере, определяемые пользователем ссылочные типы поддерживают оператор `==` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-119">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="e5ec2-120">Однако ссылочный тип может перегружать оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-120">However, a reference type can overload the `==` operator.</span></span> <span data-ttu-id="e5ec2-121">Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-121">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

### <a name="string-equality"></a><span data-ttu-id="e5ec2-122">Равенство строк</span><span class="sxs-lookup"><span data-stu-id="e5ec2-122">String equality</span></span>

<span data-ttu-id="e5ec2-123">Два операнда [string](../builtin-types/reference-types.md#the-string-type) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-123">Two [string](../builtin-types/reference-types.md#the-string-type) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="e5ec2-124">Это порядковое сравнение, учитывающее регистр.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-124">That is a case-sensitive ordinal comparison.</span></span> <span data-ttu-id="e5ec2-125">Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="e5ec2-125">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="delegate-equality"></a><span data-ttu-id="e5ec2-126">Равенство делегатов</span><span class="sxs-lookup"><span data-stu-id="e5ec2-126">Delegate equality</span></span>

<span data-ttu-id="e5ec2-127">Два операнда [delegate](../../programming-guide/delegates/index.md) одного типа среды выполнения равны, если оба из них имеют значение `null` или их списки вызовов имеют одинаковую длину и содержат одинаковые записи в каждой позиции:</span><span class="sxs-lookup"><span data-stu-id="e5ec2-127">Two [delegate](../../programming-guide/delegates/index.md) operands of the same runtime type are equal when both of them are `null` or their invocation lists are of the same length and have equal entries in each position:</span></span>

[!code-csharp-interactive[delegate equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#DelegateEquality)]

<span data-ttu-id="e5ec2-128">Подробные сведения см. в разделе [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) (Операторы равенства делегатов) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e5ec2-128">For more information, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="e5ec2-129">Делегаты, созданные в результате оценки семантически идентичных [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) не будут равны, как показано в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="e5ec2-129">Delegates that are produced from evaluation of semantically identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal, as the following example shows:</span></span>

[!code-csharp-interactive[from identical lambdas](~/samples/csharp/language-reference/operators/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a><span data-ttu-id="e5ec2-130">Оператор неравенства !=</span><span class="sxs-lookup"><span data-stu-id="e5ec2-130">Inequality operator !=</span></span>

<span data-ttu-id="e5ec2-131">Оператор неравенства `!=` возвращает значение `true`, если его операнды не равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-131">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="e5ec2-132">Для операндов [встроенных типов](../keywords/built-in-types-table.md) выражение `x != y` дает тот же результат, что и выражение `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-132">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="e5ec2-133">Дополнительные сведения о равенстве типов см. в разделе [Оператор равенства](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="e5ec2-133">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="e5ec2-134">В следующем примере иллюстрируется использование оператора `!=`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-134">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="e5ec2-135">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="e5ec2-135">Operator overloadability</span></span>

<span data-ttu-id="e5ec2-136">Определяемый пользователем тип может [перегружать](operator-overloading.md) операторы `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-136">A user-defined type can [overload](operator-overloading.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="e5ec2-137">Если тип перегружает один из двух операторов, он должен также перегружать и другой.</span><span class="sxs-lookup"><span data-stu-id="e5ec2-137">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e5ec2-138">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e5ec2-138">C# language specification</span></span>

<span data-ttu-id="e5ec2-139">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e5ec2-139">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ec2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ec2-140">See also</span></span>

- [<span data-ttu-id="e5ec2-141">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e5ec2-141">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e5ec2-142">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e5ec2-142">C# operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e5ec2-143">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="e5ec2-143">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="e5ec2-144">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="e5ec2-144">Comparison operators</span></span>](comparison-operators.md)
