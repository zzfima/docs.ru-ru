---
title: "Оператор -= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
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
ms.openlocfilehash: d7f26ae1fce54eb0d03a314a83ce523baeb3f348
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="--operator-c-reference"></a><span data-ttu-id="44d3b-102">Оператор -= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="44d3b-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="44d3b-103">Оператор присваивания вычитания.</span><span class="sxs-lookup"><span data-stu-id="44d3b-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d3b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="44d3b-104">Remarks</span></span>  
 <span data-ttu-id="44d3b-105">Выражение, использующее оператор присваивания `-=`, такое как</span><span class="sxs-lookup"><span data-stu-id="44d3b-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```  
x -= y  
```  
  
 <span data-ttu-id="44d3b-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="44d3b-106">is equivalent to</span></span>  
  
```  
x = x - y  
```  
  
 <span data-ttu-id="44d3b-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="44d3b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="44d3b-108">Значение [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="44d3b-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="44d3b-109">Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="44d3b-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="44d3b-110">Оператор -= также используется в C# для отмены подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="44d3b-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="44d3b-111">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="44d3b-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44d3b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="44d3b-112">Example</span></span>  
 <span data-ttu-id="44d3b-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="44d3b-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d3b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="44d3b-114">See Also</span></span>  
 <span data-ttu-id="44d3b-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="44d3b-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="44d3b-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="44d3b-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="44d3b-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="44d3b-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

