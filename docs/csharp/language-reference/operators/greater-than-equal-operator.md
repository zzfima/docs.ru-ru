---
title: Оператор &gt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 8749d1dc0670a5a76bda5ee0d69a4a142671c1e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481766"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="63f6d-102">Оператор &gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="63f6d-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="63f6d-103">Все числовые типы и типы перечисления определяют оператор отношения "больше или равно" (`>=`), который возвращает `true`, если первый операнд больше второго или равен ему. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="63f6d-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63f6d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="63f6d-104">Remarks</span></span>  
 <span data-ttu-id="63f6d-105">Определяемые пользователем типы могут перегружать оператор `>=`.</span><span class="sxs-lookup"><span data-stu-id="63f6d-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="63f6d-106">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="63f6d-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="63f6d-107">В случае перегрузки `>=` также необходимо перегружать [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="63f6d-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="63f6d-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="63f6d-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f6d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="63f6d-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="63f6d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="63f6d-110">See Also</span></span>

- [<span data-ttu-id="63f6d-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="63f6d-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="63f6d-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="63f6d-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="63f6d-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="63f6d-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
