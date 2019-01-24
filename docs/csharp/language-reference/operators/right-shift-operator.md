---
title: Справочник по C#. Оператор &gt;&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 80e38d8e75b9ad573b635d544d6381950f107583
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333694"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="e32ff-102">Справочник по C#. Оператор &gt;&gt;</span><span class="sxs-lookup"><span data-stu-id="e32ff-102">&gt;&gt; operator (C# Reference)</span></span>

<span data-ttu-id="e32ff-103">Оператор сдвига вправо (`>>`) сдвигает первый операнд вправо на число битов, задаваемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="e32ff-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="e32ff-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e32ff-104">Remarks</span></span>

<span data-ttu-id="e32ff-105">Если первый операнд имеет тип [int](../keywords/int.md) или [uint](../keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда (второй операнд и 0x1f).</span><span class="sxs-lookup"><span data-stu-id="e32ff-105">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>

<span data-ttu-id="e32ff-106">Если первый операнд имеет тип [long](../keywords/long.md) или [ulong](../keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда (второй операнд и 0x3f).</span><span class="sxs-lookup"><span data-stu-id="e32ff-106">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>

<span data-ttu-id="e32ff-107">Если первый операнд имеет тип [int](../keywords/int.md) или [long](../keywords/long.md), величина сдвига вправо определяется арифметическим сдвигом (пустые старшие разряды используются для бита знака).</span><span class="sxs-lookup"><span data-stu-id="e32ff-107">If the first operand is an [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="e32ff-108">Если первый операнд имеет тип [uint](../keywords/uint.md) или [ulong](../keywords/ulong.md), величина сдвига вправо определяется логическим сдвигом (старшие разряды заполняются нулями).</span><span class="sxs-lookup"><span data-stu-id="e32ff-108">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>

<span data-ttu-id="e32ff-109">Определяемые пользователем типы могут перегружать оператор `>>`. В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип [int](../keywords/int.md). Дополнительные сведения см. в статье [operator](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="e32ff-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../keywords/int.md). For more information, see [operator](../keywords/operator.md).</span></span> <span data-ttu-id="e32ff-110">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="e32ff-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="e32ff-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e32ff-111">Example</span></span>

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a><span data-ttu-id="e32ff-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e32ff-112">See Also</span></span>

- [<span data-ttu-id="e32ff-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e32ff-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e32ff-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e32ff-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e32ff-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e32ff-115">C# operators</span></span>](index.md)