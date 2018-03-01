---
title: "Оператор &amp;= (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bea90651faaafe7b754ce1cf16bddbab997d5f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="255ba-102">Оператор &amp;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="255ba-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="255ba-103">Оператор присваивания И.</span><span class="sxs-lookup"><span data-stu-id="255ba-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="255ba-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="255ba-104">Remarks</span></span>  
 <span data-ttu-id="255ba-105">Выражение, использующее оператор присваивания `&=`, такое как</span><span class="sxs-lookup"><span data-stu-id="255ba-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```  
x &= y  
```  
  
 <span data-ttu-id="255ba-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="255ba-106">is equivalent to</span></span>  
  
```  
x = x & y  
```  
  
 <span data-ttu-id="255ba-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="255ba-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="255ba-108">[Оператор &](../../../csharp/language-reference/operators/and-operator.md) выполняет побитовую логическую операцию И в отношении целочисленных операндов и логическую операцию И в отношении операндов типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="255ba-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="255ba-109">Оператор `&=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать бинарный [оператор &](../../../csharp/language-reference/operators/and-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="255ba-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="255ba-110">Пример</span><span class="sxs-lookup"><span data-stu-id="255ba-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="255ba-111">См. также</span><span class="sxs-lookup"><span data-stu-id="255ba-111">See Also</span></span>  
 [<span data-ttu-id="255ba-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="255ba-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="255ba-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="255ba-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="255ba-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="255ba-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
