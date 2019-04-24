---
title: Оператор &amp;. Справочник по C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310048"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="5a144-102">Оператор &amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5a144-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="5a144-103">Оператор `&` поддерживается в двух формах: унарный оператор address-of или бинарный логический оператор.</span><span class="sxs-lookup"><span data-stu-id="5a144-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="5a144-104">Унарный оператор address-of</span><span class="sxs-lookup"><span data-stu-id="5a144-104">Unary address-of operator</span></span>

<span data-ttu-id="5a144-105">Унарный оператор `&` возвращает адрес полученного операнда.</span><span class="sxs-lookup"><span data-stu-id="5a144-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="5a144-106">Дополнительные сведения см. в статье [Практическое руководство. Получение адреса переменной](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5a144-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="5a144-107">Для оператора получения адреса `&` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="5a144-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="5a144-108">Целочисленная побитовая логическая операция И</span><span class="sxs-lookup"><span data-stu-id="5a144-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="5a144-109">Для целочисленных типов оператор `&` выполняет побитовую логическую операцию И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="5a144-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="5a144-110">В предыдущем примере используются двоичные литералы, [впервые появившиеся в C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) и [улучшенные в C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="5a144-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="5a144-111">Так как операции с целочисленными типами обычно разрешены для типов перечисления, оператор `&` также поддерживает операнды [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="5a144-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="5a144-112">Логический оператор И</span><span class="sxs-lookup"><span data-stu-id="5a144-112">Boolean logical AND operator</span></span>

<span data-ttu-id="5a144-113">Для операндов типа [bool](../keywords/bool.md) оператор `&` вычисляет логическое И всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="5a144-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="5a144-114">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5a144-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="5a144-115">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="5a144-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5a144-116">Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="5a144-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="5a144-117">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="5a144-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="5a144-118">[Условный оператор логического И](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но он не вычисляет второй операнд, если первый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="5a144-118">The [conditional AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="5a144-119">Для логических операндов, допускающих значение NULL, поведение оператора `&` согласуется с троичной логикой SQL.</span><span class="sxs-lookup"><span data-stu-id="5a144-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="5a144-120">См. подробнее о [логических операторах, поддерживающих значение NULL](boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5a144-120">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5a144-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="5a144-121">Operator overloadability</span></span>

<span data-ttu-id="5a144-122">Определяемые пользователем типы могут вызвать [перегрузку](../keywords/operator.md) бинарного оператора `&`.</span><span class="sxs-lookup"><span data-stu-id="5a144-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="5a144-123">При перегрузке бинарного оператора `&` неявно перегружается и соответствующий [Оператор присваивания И](and-assignment-operator.md) `&=`.</span><span class="sxs-lookup"><span data-stu-id="5a144-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5a144-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5a144-124">C# language specification</span></span>

<span data-ttu-id="5a144-125">Дополнительные сведения см. в разделах [Оператор address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) и [Логические операторы](~/_csharplang/spec/expressions.md#logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5a144-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a144-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5a144-126">See also</span></span>

- [<span data-ttu-id="5a144-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5a144-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a144-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5a144-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a144-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5a144-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5a144-130">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="5a144-130">Boolean logical operators</span></span>](boolean-logical-operators.md)
- [<span data-ttu-id="5a144-131">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="5a144-131">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="5a144-132">Оператор |</span><span class="sxs-lookup"><span data-stu-id="5a144-132">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="5a144-133">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="5a144-133">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="5a144-134">Оператор ~</span><span class="sxs-lookup"><span data-stu-id="5a144-134">~ operator</span></span>](bitwise-complement-operator.md)
