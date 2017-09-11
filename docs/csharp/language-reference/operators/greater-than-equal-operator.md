---
title: "Оператор &gt;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
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
ms.openlocfilehash: 59b134ce1e1169b0a5f4583374148d39ceb8326a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="592b3-102">Оператор &gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="592b3-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="592b3-103">Все числовые типы и типы перечисления определяют оператор отношения "больше или равно" (`>=`), который возвращает `true`, если первый операнд больше второго или равен ему. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="592b3-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="592b3-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="592b3-104">Remarks</span></span>  
 <span data-ttu-id="592b3-105">Определяемые пользователем типы могут перегружать оператор `>=`.</span><span class="sxs-lookup"><span data-stu-id="592b3-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="592b3-106">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="592b3-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="592b3-107">В случае перегрузки `>=` также необходимо перегружать [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="592b3-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="592b3-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="592b3-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="592b3-109">Пример</span><span class="sxs-lookup"><span data-stu-id="592b3-109">Example</span></span>  
 <span data-ttu-id="592b3-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="592b3-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592b3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="592b3-111">See Also</span></span>  
 <span data-ttu-id="592b3-112">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="592b3-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="592b3-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="592b3-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="592b3-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="592b3-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

