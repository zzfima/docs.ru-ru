---
title: '>> Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219728"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2f9dc-102">Оператор >> (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2f9dc-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="2f9dc-103">Оператор сдвига вправо `>>` сдвигает первый операнд вправо на число битов, определяемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-103">The right-shift operator `>>` shifts its first operand right by the number of bits defined by its second operand.</span></span> <span data-ttu-id="2f9dc-104">Оператор `>>` поддерживает все целочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-104">All integer types support the `>>` operator.</span></span> <span data-ttu-id="2f9dc-105">Однако второй операнд должен иметь тип [int](../keywords/int.md) или тип, для которого существует [предварительно определенное неявное числовое преобразование](../keywords/implicit-numeric-conversions-table.md) в `int`.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="2f9dc-106">Операция сдвига вправо отменяет биты низкого порядка.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-106">The right-shift operation discards the low-order bits.</span></span> <span data-ttu-id="2f9dc-107">Позиции пустых битов высокого порядка задаются с учетом типа первого операнда следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-107">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="2f9dc-108">Если первый операнд имеет тип [int](../keywords/int.md) или [long](../keywords/long.md), оператор сдвига вправо выполняет **арифметический** сдвиг. Значение старшего значимого бита (знаковый бит) первого операнда распространяется на пустые битовые позиции высокого разряда.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-108">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an **arithmetic** shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="2f9dc-109">То есть пустые битовые позиции высокого порядка разряда устанавливаются на ноль, если первый операнд неотрицательный, и устанавливаются на единицу, если он отрицательный.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-109">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

- <span data-ttu-id="2f9dc-110">Если первый операнд имеет тип [uint](../keywords/uint.md) или [ulong](../keywords/ulong.md), оператор сдвига вправо выполняет **логический** сдвиг. Пустым битовым позициям высокого порядка всегда присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-110">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a **logical** shift: the high-order empty bit positions are always set to zero.</span></span>

<span data-ttu-id="2f9dc-111">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-111">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a><span data-ttu-id="2f9dc-112">Величина сдвига</span><span class="sxs-lookup"><span data-stu-id="2f9dc-112">Shift count</span></span>

<span data-ttu-id="2f9dc-113">Для выражения `x >> count` фактическая величина сдвига зависит от типа `x` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-113">For the expression `x >> count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="2f9dc-114">Если тип `x` — [int](../keywords/int.md) или [uint](../keywords/uint.md), величина сдвига определяется *пятью* младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-114">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="2f9dc-115">То есть величина сдвига вычисляется на основе `count & 0x1F` (или `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="2f9dc-115">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="2f9dc-116">Если тип `x` — [long](../keywords/long.md) или [ulong](../keywords/ulong.md), величина сдвига определяется *шестью* младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-116">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="2f9dc-117">То есть величина сдвига вычисляется на основе `count & 0x3F` (или `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="2f9dc-117">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="2f9dc-118">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-118">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="2f9dc-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f9dc-119">Remarks</span></span>

<span data-ttu-id="2f9dc-120">Операции сдвига никогда не приводят к переполнению и дают одинаковые результаты в [проверенных и непроверенных](../keywords/checked-and-unchecked.md) контекстах.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-120">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="2f9dc-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="2f9dc-121">Operator overloadability</span></span>

<span data-ttu-id="2f9dc-122">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `>>`.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-122">User-defined types can [overload](../keywords/operator.md) the `>>` operator.</span></span> <span data-ttu-id="2f9dc-123">Если определяемый пользователем тип `T` перегружает оператор `>>`, то в этом случае первый операнд должен иметь `T`, а второй операнд — тип `int`.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-123">If a user-defined type `T` overloads the `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="2f9dc-124">При перегрузке оператора `>>` неявно перегружается и соответствующий [оператор присваивания сдвига вправо](right-shift-assignment-operator.md) `>>=`.</span><span class="sxs-lookup"><span data-stu-id="2f9dc-124">When the `>>` operator is overloaded, the [right-shift assignment operator](right-shift-assignment-operator.md) `>>=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2f9dc-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2f9dc-125">C# language specification</span></span>

<span data-ttu-id="2f9dc-126">Дополнительные сведения см. в разделе [Операторы сдвига](~/_csharplang/spec/expressions.md#shift-operators) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2f9dc-126">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f9dc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2f9dc-127">See also</span></span>

- [<span data-ttu-id="2f9dc-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2f9dc-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2f9dc-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2f9dc-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2f9dc-130">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2f9dc-130">C# operators</span></span>](index.md)
- [<span data-ttu-id="2f9dc-131">Справочник по C#. Оператор <<</span><span class="sxs-lookup"><span data-stu-id="2f9dc-131"><< operator</span></span>](left-shift-operator.md)