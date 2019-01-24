---
title: Справочник по C#. Оператор &lt;&lt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333529"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="eca15-102">Справочник по C#. Оператор &lt;&lt;</span><span class="sxs-lookup"><span data-stu-id="eca15-102">&lt;&lt; operator (C# Reference)</span></span>

<span data-ttu-id="eca15-103">Оператор сдвига влево (`<<`) сдвигает первый операнд влево на число битов, задаваемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="eca15-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="eca15-104">Второй операнд должен иметь тип [int](../keywords/int.md) или тип, для которого существует предварительно определенное неявное числовое преобразование в `int`.</span><span class="sxs-lookup"><span data-stu-id="eca15-104">The type of the second operand must be an [int](../keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eca15-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="eca15-105">Remarks</span></span>

<span data-ttu-id="eca15-106">Если первый операнд имеет тип [int](../keywords/int.md) или [uint](../keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="eca15-106">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="eca15-107">Фактическая величина сдвига составляет от 0 до 31 бита.</span><span class="sxs-lookup"><span data-stu-id="eca15-107">That is, the actual shift count is 0 to 31 bits.</span></span>

<span data-ttu-id="eca15-108">Если первый операнд имеет тип [long](../keywords/long.md) или [ulong](../keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="eca15-108">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="eca15-109">Фактическая величина сдвига составляет от 0 до 63 битов.</span><span class="sxs-lookup"><span data-stu-id="eca15-109">That is, the actual shift count is 0 to 63 bits.</span></span>

<span data-ttu-id="eca15-110">Любые старшие разряды, не попадающие в диапазон значений типа первого операнда после сдвига, отбрасываются, а пустые младшие разряды заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="eca15-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="eca15-111">Операции сдвига никогда не вызывают переполнение.</span><span class="sxs-lookup"><span data-stu-id="eca15-111">Shift operations never cause overflows.</span></span>

<span data-ttu-id="eca15-112">Определяемые пользователем типы могут перегружать оператор `<<` (см. [operator](../keywords/operator.md)). В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип `int`.</span><span class="sxs-lookup"><span data-stu-id="eca15-112">User-defined types can overload the `<<` operator (see [operator](../keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="eca15-113">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="eca15-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="eca15-114">Пример</span><span class="sxs-lookup"><span data-stu-id="eca15-114">Example</span></span>

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a><span data-ttu-id="eca15-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="eca15-115">Comments</span></span>

<span data-ttu-id="eca15-116">Обратите внимание, что `i<<1` и `i<<33` дают один и тот же результат, поскольку 1 и 33 имеют одинаковые младшие пять разрядов.</span><span class="sxs-lookup"><span data-stu-id="eca15-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>

## <a name="see-also"></a><span data-ttu-id="eca15-117">См. также</span><span class="sxs-lookup"><span data-stu-id="eca15-117">See also</span></span>

- [<span data-ttu-id="eca15-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="eca15-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eca15-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eca15-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eca15-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="eca15-120">C# Operators</span></span>](index.md)
