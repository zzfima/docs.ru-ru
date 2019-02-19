---
title: Оператор << — справочник по C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219441"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="74ae3-102">Справочник по C#. Оператор \<\<</span><span class="sxs-lookup"><span data-stu-id="74ae3-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="74ae3-103">Оператор сдвига влево `<<` сдвигает первый операнд влево на число битов, определяемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="74ae3-103">The left-shift operator `<<` shifts its first operand left by the number of bits defined by its second operand.</span></span> <span data-ttu-id="74ae3-104">Оператор `<<` поддерживает все целочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="74ae3-104">All integer types support the `<<` operator.</span></span> <span data-ttu-id="74ae3-105">Однако второй операнд должен иметь тип [int](../keywords/int.md) или тип, для которого существует [предварительно определенное неявное числовое преобразование](../keywords/implicit-numeric-conversions-table.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="74ae3-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="74ae3-106">Биты высокого порядка, выходящие за пределы диапазона типа результата, отменяются, а позиции пустого бита низкого порядка устанавливаются на ноль, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="74ae3-106">The high-order bits that are outside the range of the result type are discarded, and the low-order empty bit positions are set to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a><span data-ttu-id="74ae3-107">Величина сдвига</span><span class="sxs-lookup"><span data-stu-id="74ae3-107">Shift count</span></span>

<span data-ttu-id="74ae3-108">Для выражения `x << count` фактическая величина сдвига зависит от типа `x` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="74ae3-108">For the expression `x << count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="74ae3-109">Если тип `x` — [int](../keywords/int.md) или [uint](../keywords/uint.md), величина сдвига определяется *пятью* младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="74ae3-109">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="74ae3-110">То есть величина сдвига вычисляется на основе `count & 0x1F` (или `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="74ae3-110">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="74ae3-111">Если тип `x` — [long](../keywords/long.md) или [ulong](../keywords/ulong.md), величина сдвига определяется *шестью* младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="74ae3-111">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="74ae3-112">То есть величина сдвига вычисляется на основе `count & 0x3F` (или `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="74ae3-112">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="74ae3-113">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="74ae3-113">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="74ae3-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="74ae3-114">Remarks</span></span>

<span data-ttu-id="74ae3-115">Операции сдвига никогда не приводят к переполнению и дают одинаковые результаты в [проверенных и непроверенных](../keywords/checked-and-unchecked.md) контекстах.</span><span class="sxs-lookup"><span data-stu-id="74ae3-115">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="74ae3-116">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="74ae3-116">Operator overloadability</span></span>

<span data-ttu-id="74ae3-117">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `<<`.</span><span class="sxs-lookup"><span data-stu-id="74ae3-117">User-defined types can [overload](../keywords/operator.md) the `<<` operator.</span></span> <span data-ttu-id="74ae3-118">Если определяемый пользователем тип `T` перегружает оператор `<<`, то в этом случае первый операнд должен иметь `T`, а второй операнд — тип `int`.</span><span class="sxs-lookup"><span data-stu-id="74ae3-118">If a user-defined type `T` overloads the `<<` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="74ae3-119">При перегрузке оператора `<<` неявно перегружается и соответствующий [оператор присваивания сдвига влево](left-shift-assignment-operator.md) `<<=`.</span><span class="sxs-lookup"><span data-stu-id="74ae3-119">When the `<<` operator is overloaded, the [left-shift assignment operator](left-shift-assignment-operator.md) `<<=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="74ae3-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="74ae3-120">C# language specification</span></span>

<span data-ttu-id="74ae3-121">Дополнительные сведения см. в разделе [Операторы сдвига](~/_csharplang/spec/expressions.md#shift-operators) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="74ae3-121">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74ae3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="74ae3-122">See also</span></span>

- [<span data-ttu-id="74ae3-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="74ae3-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="74ae3-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="74ae3-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="74ae3-125">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="74ae3-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="74ae3-126">Оператор >> (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="74ae3-126">>> operator</span></span>](right-shift-operator.md)
