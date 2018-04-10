---
title: Оператор &lt;= (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a74af852451a193aaee70fea2a68ca8ff29cc215
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="59b8c-102">Оператор &lt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="59b8c-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="59b8c-103">Все числовые типы и типы перечисления определяют оператор отношения "меньше или равно" (`<=`), который возвращает `true`, если первый операнд меньше второго или равен ему. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="59b8c-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b8c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="59b8c-104">Remarks</span></span>  
 <span data-ttu-id="59b8c-105">Определяемые пользователем типы могут перегружать оператор `<=`.</span><span class="sxs-lookup"><span data-stu-id="59b8c-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="59b8c-106">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="59b8c-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="59b8c-107">В случае перегрузки `<=` также необходимо перегружать [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="59b8c-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="59b8c-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="59b8c-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b8c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="59b8c-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="59b8c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="59b8c-110">See Also</span></span>  
 [<span data-ttu-id="59b8c-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="59b8c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="59b8c-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="59b8c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="59b8c-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="59b8c-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="59b8c-114">explicit</span><span class="sxs-lookup"><span data-stu-id="59b8c-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
