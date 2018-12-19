---
title: Справочник по C#. Оператор /
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286537"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c9ba6-102">Оператор / (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c9ba6-102">/ Operator (C# Reference)</span></span>

<span data-ttu-id="c9ba6-103">Оператор деления `/` делит первый операнд на второй.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-103">The division operator `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="c9ba6-104">Все числовые типы поддерживают оператор деления.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-104">All numeric types support the division operator.</span></span>

## <a name="integer-division"></a><span data-ttu-id="c9ba6-105">Деление целых чисел</span><span class="sxs-lookup"><span data-stu-id="c9ba6-105">Integer division</span></span>

<span data-ttu-id="c9ba6-106">Для операндов цельночисленных типов результат оператора `/` является целочисленным типом, который равен частному двух операндов, округленному в сторону нуля:</span><span class="sxs-lookup"><span data-stu-id="c9ba6-106">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

<span data-ttu-id="c9ba6-107">Чтобы получить частное двух операндов в виде числа с плавающей запятой, используйте тип `float`, `double` или `decimal`:</span><span class="sxs-lookup"><span data-stu-id="c9ba6-107">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a><span data-ttu-id="c9ba6-108">Деление чисел с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="c9ba6-108">Floating-point division</span></span>

<span data-ttu-id="c9ba6-109">Для типов `float`, `double` и `decimal` результатом оператора `/` является частное двух операндов:</span><span class="sxs-lookup"><span data-stu-id="c9ba6-109">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

<span data-ttu-id="c9ba6-110">Если один из операндов — это `decimal`, второй операнд не может быть ни `float`, ни `double`, так как ни `float`, ни `double` не преобразуется неявно в тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-110">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="c9ba6-111">Необходимо явным образом преобразовать операнд `float` или `double` в тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-111">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="c9ba6-112">Дополнительные сведения о неявных числовых преобразованиях см. в [таблице неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba6-112">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c9ba6-113">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="c9ba6-113">Operator overloadability</span></span>

<span data-ttu-id="c9ba6-114">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `/`.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-114">User-defined types can [overload](../keywords/operator.md) the `/` operator.</span></span> <span data-ttu-id="c9ba6-115">При перегрузке оператора `/` неявно перегружается и соответствующий [оператор присваивания деления](division-assignment-operator.md) `/=`.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-115">When the `/` operator is overloaded, the [division assignment operator](division-assignment-operator.md) `/=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c9ba6-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c9ba6-116">C# language specification</span></span>

<span data-ttu-id="c9ba6-117">Дополнительные сведения см. в разделе [Оператор деления](~/_csharplang/spec/expressions.md#division-operator) [спецификация языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba6-117">For more information, see the [Division operator](~/_csharplang/spec/expressions.md#division-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9ba6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c9ba6-118">See also</span></span>

- [<span data-ttu-id="c9ba6-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c9ba6-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c9ba6-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c9ba6-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c9ba6-121">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="c9ba6-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c9ba6-122">Оператор %</span><span class="sxs-lookup"><span data-stu-id="c9ba6-122">% Operator</span></span>](remainder-operator.md)
