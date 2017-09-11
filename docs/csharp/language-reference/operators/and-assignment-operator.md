---
title: "Оператор &amp;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="92ffa-102">Оператор &amp;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="92ffa-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="92ffa-103">Оператор присваивания И.</span><span class="sxs-lookup"><span data-stu-id="92ffa-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ffa-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="92ffa-104">Remarks</span></span>  
 <span data-ttu-id="92ffa-105">Выражение, использующее оператор присваивания `&=`, такое как</span><span class="sxs-lookup"><span data-stu-id="92ffa-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```  
x &= y  
```  
  
 <span data-ttu-id="92ffa-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="92ffa-106">is equivalent to</span></span>  
  
```  
x = x & y  
```  
  
 <span data-ttu-id="92ffa-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="92ffa-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="92ffa-108">[Оператор &](../../../csharp/language-reference/operators/and-operator.md) выполняет побитовую логическую операцию И в отношении целочисленных операндов и логическую операцию И в отношении операндов типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="92ffa-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="92ffa-109">Оператор `&=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать бинарный [оператор &](../../../csharp/language-reference/operators/and-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="92ffa-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92ffa-110">Пример</span><span class="sxs-lookup"><span data-stu-id="92ffa-110">Example</span></span>  
 <span data-ttu-id="92ffa-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="92ffa-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ffa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="92ffa-112">See Also</span></span>  
 <span data-ttu-id="92ffa-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="92ffa-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="92ffa-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="92ffa-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="92ffa-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="92ffa-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

