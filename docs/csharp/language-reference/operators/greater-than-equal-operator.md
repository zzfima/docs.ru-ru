---
title: Оператор &gt;= (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020c2bd8756899908681ab72cac7aa2a203c6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="6d53a-102">Оператор &gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6d53a-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="6d53a-103">Все числовые типы и типы перечисления определяют оператор отношения "больше или равно" (`>=`), который возвращает `true`, если первый операнд больше второго или равен ему. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="6d53a-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d53a-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d53a-104">Remarks</span></span>  
 <span data-ttu-id="6d53a-105">Определяемые пользователем типы могут перегружать оператор `>=`.</span><span class="sxs-lookup"><span data-stu-id="6d53a-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="6d53a-106">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="6d53a-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="6d53a-107">В случае перегрузки `>=` также необходимо перегружать [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6d53a-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="6d53a-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="6d53a-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d53a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6d53a-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6d53a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6d53a-110">See Also</span></span>  
 [<span data-ttu-id="6d53a-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6d53a-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6d53a-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6d53a-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d53a-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="6d53a-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
