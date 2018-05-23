---
title: Оператор &gt; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="8c463-102">Оператор &gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8c463-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="8c463-103">Все числовые типы и типы перечисления определяют оператор отношения "больше" (`>`), который возвращает `true`, если первый операнд больше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="8c463-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c463-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c463-104">Remarks</span></span>  
 <span data-ttu-id="8c463-105">Определяемые пользователем типы могут вызвать перегрузку оператора `>` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="8c463-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8c463-106">В случае перегрузки `>` также необходимо перегружать [<](../../../csharp/language-reference/operators/less-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8c463-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="8c463-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="8c463-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c463-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8c463-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8c463-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8c463-109">See Also</span></span>  
 [<span data-ttu-id="8c463-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8c463-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8c463-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8c463-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8c463-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8c463-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="8c463-113">explicit</span><span class="sxs-lookup"><span data-stu-id="8c463-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
