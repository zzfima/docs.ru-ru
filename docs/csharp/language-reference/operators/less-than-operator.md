---
title: Оператор &lt; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: eceb6214e4e625aa71e12788d5dd5e8324c75443
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270235"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="f081d-102">Оператор &lt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f081d-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="f081d-103">Все числовые типы и типы перечисления определяют оператор отношения "меньше" (`<`), который возвращает `true`, если первый операнд меньше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="f081d-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f081d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f081d-104">Remarks</span></span>  
 <span data-ttu-id="f081d-105">Определяемые пользователем типы могут вызвать перегрузку оператора `<` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="f081d-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="f081d-106">В случае перегрузки `<` также необходимо перегружать [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f081d-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="f081d-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="f081d-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f081d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f081d-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f081d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f081d-109">See Also</span></span>  
 [<span data-ttu-id="f081d-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f081d-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f081d-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f081d-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f081d-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f081d-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
