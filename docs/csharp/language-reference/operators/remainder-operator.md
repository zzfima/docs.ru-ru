---
title: Справочник по C#. Оператор %
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: a5c12b6683e35cc1ec2d40446dd0ed068c3d2552
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236483"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="900b0-102">Оператор % (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="900b0-102">% Operator (C# Reference)</span></span>

<span data-ttu-id="900b0-103">Оператор остатка `%` вычисляет остаток от деления первого операнда на второй.</span><span class="sxs-lookup"><span data-stu-id="900b0-103">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

<span data-ttu-id="900b0-104">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `%`.</span><span class="sxs-lookup"><span data-stu-id="900b0-104">User-defined types can [overload](../keywords/operator.md) the `%` operator.</span></span> <span data-ttu-id="900b0-105">Когда `%` перегружается, [оператор присваивания остатка](remainder-assignment-operator.md) `%=` также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="900b0-105">When the `%` is overloaded, the [remainder assignment operator](remainder-assignment-operator.md) `%=` is also implicitly overloaded.</span></span>

<span data-ttu-id="900b0-106">Все числовые типы поддерживают оператор остатка.</span><span class="sxs-lookup"><span data-stu-id="900b0-106">All numeric types support the remainder operator.</span></span>

## <a name="integer-remainder"></a><span data-ttu-id="900b0-107">Целочисленный остаток</span><span class="sxs-lookup"><span data-stu-id="900b0-107">Integer remainder</span></span>
  
<span data-ttu-id="900b0-108">Для целочисленных операндов результатом `a % b` является значение, произведенное `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="900b0-108">For the integer operands, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="900b0-109">Знак ненулевого остатка такой же, как и у первого операнда, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="900b0-109">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a><span data-ttu-id="900b0-110">Остаток с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="900b0-110">Floating-point remainder</span></span>

<span data-ttu-id="900b0-111">Для операндов типа [float](../keywords/float.md) и [double](../keywords/double.md) результатом `x % y` для конечных `x` и `y` будет значение `z`, так что:</span><span class="sxs-lookup"><span data-stu-id="900b0-111">For the [float](../keywords/float.md) and [double](../keywords/double.md) operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="900b0-112">знак `z`, если отлично от нуля, совпадает со знаком `x`;</span><span class="sxs-lookup"><span data-stu-id="900b0-112">the sign of `z`, if non-zero, is the same as the sign of `x`;</span></span>
- <span data-ttu-id="900b0-113">абсолютное значение `z` является значением, произведенным `|x| - n * |y|`, где `n` — это наибольшее возможное целое число, которое меньше или равно `|x| / |y|`, а `|x|` и `|y|` являются абсолютными значениями `x` и `y` соответственно.</span><span class="sxs-lookup"><span data-stu-id="900b0-113">the absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

<span data-ttu-id="900b0-114">Сведения о поведение оператора `%` в случае неконечных операндов см. в разделе [Оператор остатка](~/_csharplang/spec/expressions.md#remainder-operator) [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="900b0-114">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="900b0-115">Этот метод вычисления остатка аналогичен тому, который использовался для целочисленных операндов, но отличается от IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="900b0-115">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="900b0-116">Если вам нужна операция остатка, которая соответствует IEEE 754, используйте метод <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="900b0-116">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="900b0-117">В следующем примере показано поведение оператора остатка для операндов `float` и `double`.</span><span class="sxs-lookup"><span data-stu-id="900b0-117">The following example demonstrates the behavior of the remainder operator for `float` and `double` operands:</span></span>

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

<span data-ttu-id="900b0-118">Обратите внимание на ошибки округления, которые могут быть связаны с типами с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="900b0-118">Note the round-off errors that can be associated with the floating-point types.</span></span>

<span data-ttu-id="900b0-119">Для [десятичных](../keywords/decimal.md) операндов оператор остатка `%` эквивалентен [оператору остатка](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) типа <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="900b0-119">For the [decimal](../keywords/decimal.md) operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

## <a name="see-also"></a><span data-ttu-id="900b0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="900b0-120">See also</span></span>

- [<span data-ttu-id="900b0-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="900b0-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="900b0-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="900b0-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="900b0-123">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="900b0-123">C# Operators</span></span>](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
