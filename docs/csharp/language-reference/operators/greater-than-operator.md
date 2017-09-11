---
title: "Оператор &gt; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
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
ms.openlocfilehash: 5b4eb1f6fcca311fc772e4dbe0ce0391201af3de
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="da5d4-102">Оператор &gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="da5d4-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="da5d4-103">Все числовые типы и типы перечисления определяют оператор отношения "больше" (`>`), который возвращает `true`, если первый операнд больше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="da5d4-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da5d4-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="da5d4-104">Remarks</span></span>  
 <span data-ttu-id="da5d4-105">Определяемые пользователем типы могут вызвать перегрузку оператора `>` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="da5d4-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="da5d4-106">В случае перегрузки `>` также необходимо перегружать [<](../../../csharp/language-reference/operators/less-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="da5d4-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="da5d4-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="da5d4-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da5d4-108">Пример</span><span class="sxs-lookup"><span data-stu-id="da5d4-108">Example</span></span>  
 <span data-ttu-id="da5d4-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="da5d4-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5d4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="da5d4-110">See Also</span></span>  
 <span data-ttu-id="da5d4-111">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="da5d4-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="da5d4-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="da5d4-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="da5d4-113">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="da5d4-113">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="da5d4-114">explicit</span><span class="sxs-lookup"><span data-stu-id="da5d4-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

