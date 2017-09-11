---
title: "Оператор &gt;&gt; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd3f077e9bb491cefce7db7c015bde201f6f8207
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="13877-102">Оператор &gt;&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="13877-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="13877-103">Оператор сдвига вправо (`>>`) сдвигает первый операнд вправо на число битов, задаваемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="13877-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13877-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="13877-104">Remarks</span></span>  
 <span data-ttu-id="13877-105">Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда (второй операнд и 0x1f).</span><span class="sxs-lookup"><span data-stu-id="13877-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="13877-106">Если первый операнд имеет тип [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда (второй операнд и 0x3f).</span><span class="sxs-lookup"><span data-stu-id="13877-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="13877-107">Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [long](../../../csharp/language-reference/keywords/long.md), величина сдвига вправо определяется арифметическим сдвигом (пустые старшие разряды используются для бита знака).</span><span class="sxs-lookup"><span data-stu-id="13877-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="13877-108">Если первый операнд имеет тип [uint](../../../csharp/language-reference/keywords/uint.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md), величина сдвига вправо определяется логическим сдвигом (старшие разряды заполняются нулями).</span><span class="sxs-lookup"><span data-stu-id="13877-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="13877-109">Определяемые пользователем типы могут перегружать оператор `>>`. В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="13877-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="13877-110">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="13877-110">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="13877-111">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="13877-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13877-112">Пример</span><span class="sxs-lookup"><span data-stu-id="13877-112">Example</span></span>  
 <span data-ttu-id="13877-113">[!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="13877-113">[!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13877-114">См. также</span><span class="sxs-lookup"><span data-stu-id="13877-114">See Also</span></span>  
 <span data-ttu-id="13877-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="13877-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="13877-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="13877-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="13877-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="13877-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

