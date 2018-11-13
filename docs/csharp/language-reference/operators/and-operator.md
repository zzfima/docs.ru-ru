---
title: Оператор &amp; (справочник по C#)
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: a8f76ded0ef9f8e8099838a903d90f1695324991
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "43510982"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="a53a0-102">Оператор &amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a53a0-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="a53a0-103">Оператор `&` поддерживается в двух формах: унарный оператор address-of или бинарный логический оператор.</span><span class="sxs-lookup"><span data-stu-id="a53a0-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="a53a0-104">Унарный оператор address-of</span><span class="sxs-lookup"><span data-stu-id="a53a0-104">Unary address-of operator</span></span>

<span data-ttu-id="a53a0-105">Унарный оператор `&` возвращает адрес полученного операнда.</span><span class="sxs-lookup"><span data-stu-id="a53a0-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="a53a0-106">Дополнительные сведения см. в статье [Практическое руководство. Получение адреса переменной](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="a53a0-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="a53a0-107">Для оператора получения адреса `&` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="a53a0-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="a53a0-108">Целочисленная побитовая логическая операция И</span><span class="sxs-lookup"><span data-stu-id="a53a0-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="a53a0-109">Для целочисленных типов оператор `&` выполняет побитовую логическую операцию И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="a53a0-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="a53a0-110">В предыдущем примере используются двоичные литералы, [впервые появившиеся в C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) и [улучшенные в C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="a53a0-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="a53a0-111">Так как операции с целочисленными типами обычно разрешены для типов перечисления, оператор `&` также поддерживает операнды [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="a53a0-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="a53a0-112">Логический оператор И</span><span class="sxs-lookup"><span data-stu-id="a53a0-112">Boolean logical AND operator</span></span>

<span data-ttu-id="a53a0-113">Для операндов типа [bool](../keywords/bool.md) оператор `&` вычисляет логическое И всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="a53a0-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="a53a0-114">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a53a0-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="a53a0-115">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="a53a0-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="a53a0-116">Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.</span><span class="sxs-lookup"><span data-stu-id="a53a0-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="a53a0-117">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="a53a0-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="a53a0-118">[Условный оператор И](conditional-and-operator.md) `&&` также вычисляет логическое И своих операндов, но он вычисляет второй операнд только в том случае, если первый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a53a0-118">The [conditional AND operator](conditional-and-operator.md) `&&` also computes the logical AND of its operands, but evaluates the second operand only if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="a53a0-119">Для логических операндов, допускающих значение NULL, поведение оператора `&` согласуется с троичной логикой SQL.</span><span class="sxs-lookup"><span data-stu-id="a53a0-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="a53a0-120">Дополнительные сведения см. в разделе [Тип bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) статьи [Использование допускающих значение NULL типов](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a53a0-120">For more information, see the [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a53a0-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="a53a0-121">Operator overloadability</span></span>

<span data-ttu-id="a53a0-122">Определяемые пользователем типы могут вызвать [перегрузку](../keywords/operator.md) бинарного оператора `&`.</span><span class="sxs-lookup"><span data-stu-id="a53a0-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="a53a0-123">При перегрузке бинарного оператора `&` неявно перегружается и соответствующий [Оператор присваивания И](and-assignment-operator.md) `&=`.</span><span class="sxs-lookup"><span data-stu-id="a53a0-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a53a0-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a53a0-124">C# language specification</span></span>

<span data-ttu-id="a53a0-125">Дополнительные сведения см. в разделах [Оператор address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) и [Логические операторы](~/_csharplang/spec/expressions.md#logical-operators) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a53a0-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a53a0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a53a0-126">See also</span></span>

- [<span data-ttu-id="a53a0-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a53a0-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a53a0-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a53a0-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a53a0-129">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a53a0-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="a53a0-130">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="a53a0-130">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="a53a0-131">Оператор |</span><span class="sxs-lookup"><span data-stu-id="a53a0-131">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="a53a0-132">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="a53a0-132">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="a53a0-133">Оператор ~</span><span class="sxs-lookup"><span data-stu-id="a53a0-133">~ operator</span></span>](bitwise-complement-operator.md)
- [<span data-ttu-id="a53a0-134">Оператор &&</span><span class="sxs-lookup"><span data-stu-id="a53a0-134">&& operator</span></span>](conditional-and-operator.md)
