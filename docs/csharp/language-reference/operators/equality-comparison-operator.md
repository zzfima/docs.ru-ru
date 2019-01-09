---
title: Справочник по C#. Оператор ==
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655963"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ad9ff-102">Оператор == (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ad9ff-102">== Operator (C# Reference)</span></span>

<span data-ttu-id="ad9ff-103">Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-103">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

## <a name="value-types-equality"></a><span data-ttu-id="ad9ff-104">Равенство типов значений</span><span class="sxs-lookup"><span data-stu-id="ad9ff-104">Value types equality</span></span>

<span data-ttu-id="ad9ff-105">Операнды [встроенных типов значений](../keywords/value-types-table.md) равны, если равны их значения.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-105">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="ad9ff-106">Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="ad9ff-107">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="ad9ff-108">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="ad9ff-109">Два операнда одного типа [enum](../keywords/enum.md) равны, если равны соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-109">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="ad9ff-110">По умолчанию оператор `==` не определен для пользовательского типа [struct](../keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-110">By default, the `==` operator is not defined for a user-defined [struct](../keywords/struct.md) type.</span></span> <span data-ttu-id="ad9ff-111">Определяемый пользователем тип может [перегружать](#operator-overloadability) оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-111">A user-defined type can [overload](#operator-overloadability) the `==` operator.</span></span>

<span data-ttu-id="ad9ff-112">Начиная с версии C# 7.3 операторы `==` и [`!=`](not-equal-operator.md) поддерживаются [кортежами](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-112">Beginning with C# 7.3, the `==` and [`!=`](not-equal-operator.md) operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="ad9ff-113">Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-113">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

## <a name="string-equality"></a><span data-ttu-id="ad9ff-114">Равенство строк</span><span class="sxs-lookup"><span data-stu-id="ad9ff-114">String equality</span></span>

<span data-ttu-id="ad9ff-115">Два операнда [string](../keywords/string.md) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-115">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="ad9ff-116">Это порядковое сравнение, учитывающее регистр.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-116">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="ad9ff-117">Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-117">For more information about how to compare strings, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

## <a name="reference-types-equality"></a><span data-ttu-id="ad9ff-118">Равенство ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="ad9ff-118">Reference types equality</span></span>

<span data-ttu-id="ad9ff-119">Два операнда, отличных от операндов ссылочного типа `string`, являются равными, если они ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-119">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="ad9ff-120">В этом примере показано, что оператор `==` поддерживается определяемыми пользователем ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-120">The example shows that the `==` operator is supported by user-defined reference types.</span></span> <span data-ttu-id="ad9ff-121">Однако определяемый пользователем ссылочный тип может перегружать оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-121">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="ad9ff-122">Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-122">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ad9ff-123">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="ad9ff-123">Operator overloadability</span></span>

<span data-ttu-id="ad9ff-124">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `==`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-124">User-defined types can [overload](../keywords/operator.md) the `==` operator.</span></span> <span data-ttu-id="ad9ff-125">Если тип перегружает оператор равенства `==`, он также должен перегружать [оператор неравенства](not-equal-operator.md) `!=`.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-125">If a type overloads the equality operator `==`, it must also overload the [inequality operator](not-equal-operator.md) `!=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ad9ff-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ad9ff-126">C# language specification</span></span>

<span data-ttu-id="ad9ff-127">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad9ff-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ad9ff-128">See also</span></span>

- [<span data-ttu-id="ad9ff-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ad9ff-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ad9ff-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ad9ff-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ad9ff-131">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ad9ff-131">C# Operators</span></span>](index.md)
- [<span data-ttu-id="ad9ff-132">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="ad9ff-132">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
