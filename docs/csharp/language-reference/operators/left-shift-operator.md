---
title: "Оператор &lt;&lt; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 400dbc799c68bb9e1bc00695954115f2eb6af7c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="4f60e-102">Оператор &lt;&lt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4f60e-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="4f60e-103">Оператор сдвига влево (`<<`) сдвигает первый операнд влево на число битов, задаваемое вторым операндом.</span><span class="sxs-lookup"><span data-stu-id="4f60e-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="4f60e-104">Второй операнд должен иметь тип [int](../../../csharp/language-reference/keywords/int.md) или тип, для которого существует предварительно определенное неявное числовое преобразование в `int`.</span><span class="sxs-lookup"><span data-stu-id="4f60e-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f60e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f60e-105">Remarks</span></span>  
 <span data-ttu-id="4f60e-106">Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="4f60e-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="4f60e-107">Фактическая величина сдвига составляет от 0 до 31 бита.</span><span class="sxs-lookup"><span data-stu-id="4f60e-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="4f60e-108">Если первый операнд имеет тип [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда.</span><span class="sxs-lookup"><span data-stu-id="4f60e-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="4f60e-109">Фактическая величина сдвига составляет от 0 до 63 битов.</span><span class="sxs-lookup"><span data-stu-id="4f60e-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="4f60e-110">Любые старшие разряды, не попадающие в диапазон значений типа первого операнда после сдвига, отбрасываются, а пустые младшие разряды заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="4f60e-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="4f60e-111">Операции сдвига никогда не вызывают переполнение.</span><span class="sxs-lookup"><span data-stu-id="4f60e-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="4f60e-112">Определяемые пользователем типы могут перегружать оператор `<<` (см. [operator](../../../csharp/language-reference/keywords/operator.md)). В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип `int`.</span><span class="sxs-lookup"><span data-stu-id="4f60e-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="4f60e-113">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="4f60e-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f60e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4f60e-114">Example</span></span>  
 [!code-csharp[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="4f60e-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4f60e-115">Comments</span></span>  
 <span data-ttu-id="4f60e-116">Обратите внимание, что `i<<1` и `i<<33` дают один и тот же результат, поскольку 1 и 33 имеют одинаковые младшие пять разрядов.</span><span class="sxs-lookup"><span data-stu-id="4f60e-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f60e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4f60e-117">See Also</span></span>  
 [<span data-ttu-id="4f60e-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4f60e-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4f60e-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4f60e-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4f60e-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4f60e-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
