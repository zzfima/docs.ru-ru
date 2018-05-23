---
title: Оператор &amp;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="4b6c5-102">Оператор &amp;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4b6c5-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="4b6c5-103">Оператор присваивания И.</span><span class="sxs-lookup"><span data-stu-id="4b6c5-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b6c5-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b6c5-104">Remarks</span></span>  
 <span data-ttu-id="4b6c5-105">Выражение, использующее оператор присваивания `&=`, такое как</span><span class="sxs-lookup"><span data-stu-id="4b6c5-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="4b6c5-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="4b6c5-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="4b6c5-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="4b6c5-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="4b6c5-108">[Оператор &](../../../csharp/language-reference/operators/and-operator.md) выполняет побитовую логическую операцию И в отношении целочисленных операндов и логическую операцию И в отношении операндов типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="4b6c5-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="4b6c5-109">Оператор `&=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать бинарный [оператор &](../../../csharp/language-reference/operators/and-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="4b6c5-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b6c5-110">Пример</span><span class="sxs-lookup"><span data-stu-id="4b6c5-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4b6c5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4b6c5-111">See Also</span></span>  
 [<span data-ttu-id="4b6c5-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4b6c5-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4b6c5-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4b6c5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4b6c5-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4b6c5-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
