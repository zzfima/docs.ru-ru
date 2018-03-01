---
title: "Оператор &lt; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="1b84a-102">Оператор &lt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b84a-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="1b84a-103">Все числовые типы и типы перечисления определяют оператор отношения "меньше" (`<`), который возвращает `true`, если первый операнд меньше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="1b84a-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b84a-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b84a-104">Remarks</span></span>  
 <span data-ttu-id="1b84a-105">Определяемые пользователем типы могут вызвать перегрузку оператора `<` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="1b84a-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="1b84a-106">В случае перегрузки `<` также необходимо перегружать [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1b84a-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="1b84a-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="1b84a-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b84a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1b84a-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1b84a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1b84a-109">See Also</span></span>  
 [<span data-ttu-id="1b84a-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1b84a-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1b84a-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1b84a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1b84a-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1b84a-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
