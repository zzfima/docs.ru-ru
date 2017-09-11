---
title: "Оператор &lt; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
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
ms.openlocfilehash: 5d90a8e549b54fc229ac3ae5bb8f30ce3b55c0d4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="beedf-102">Оператор &lt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="beedf-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="beedf-103">Все числовые типы и типы перечисления определяют оператор отношения "меньше" (`<`), который возвращает `true`, если первый операнд меньше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="beedf-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beedf-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="beedf-104">Remarks</span></span>  
 <span data-ttu-id="beedf-105">Определяемые пользователем типы могут вызвать перегрузку оператора `<` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="beedf-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="beedf-106">В случае перегрузки `<` также необходимо перегружать [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="beedf-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="beedf-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="beedf-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beedf-108">Пример</span><span class="sxs-lookup"><span data-stu-id="beedf-108">Example</span></span>  
 <span data-ttu-id="beedf-109">[!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="beedf-109">[!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beedf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="beedf-110">See Also</span></span>  
 <span data-ttu-id="beedf-111">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="beedf-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="beedf-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="beedf-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="beedf-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="beedf-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

