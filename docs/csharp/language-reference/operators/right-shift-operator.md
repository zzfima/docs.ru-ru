---
title: "Оператор &gt;&gt; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7c2eddf06d7b8417c9fcb0fed395b2bf51e07144
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="7956e-102">Оператор &gt;&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7956e-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="7956e-103">Оператор сдвига вправо (`>>`) сдвигает первый операнд вправо на число битов, задаваемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="7956e-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7956e-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="7956e-104">Remarks</span></span>  
 <span data-ttu-id="7956e-105">Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда (второй операнд и 0x1f).</span><span class="sxs-lookup"><span data-stu-id="7956e-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="7956e-106">Если первый операнд имеет тип [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда (второй операнд и 0x3f).</span><span class="sxs-lookup"><span data-stu-id="7956e-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="7956e-107">Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [long](../../../csharp/language-reference/keywords/long.md), величина сдвига вправо определяется арифметическим сдвигом (пустые старшие разряды используются для бита знака).</span><span class="sxs-lookup"><span data-stu-id="7956e-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="7956e-108">Если первый операнд имеет тип [uint](../../../csharp/language-reference/keywords/uint.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md), величина сдвига вправо определяется логическим сдвигом (старшие разряды заполняются нулями).</span><span class="sxs-lookup"><span data-stu-id="7956e-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="7956e-109">Определяемые пользователем типы могут перегружать оператор `>>`. В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип [int](../../../csharp/language-reference/keywords/int.md). Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="7956e-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="7956e-110">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="7956e-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7956e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7956e-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7956e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7956e-112">See Also</span></span>  
 [<span data-ttu-id="7956e-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7956e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7956e-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7956e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7956e-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="7956e-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
