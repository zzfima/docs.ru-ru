---
title: Оператор |= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: 18246d013275c8d6c8ad7e05409387457afc3442
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="13c74-102">Оператор |= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="13c74-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="13c74-103">Оператор присваивания ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="13c74-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13c74-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="13c74-104">Remarks</span></span>  
 <span data-ttu-id="13c74-105">Выражение, использующее оператор присваивания `|=`, такое как</span><span class="sxs-lookup"><span data-stu-id="13c74-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="13c74-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="13c74-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="13c74-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="13c74-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="13c74-108">[Оператор &#124;](../../../csharp/language-reference/operators/or-operator.md) выполняет побитовую операцию ИЛИ в отношении целочисленных операндов и логическую операцию ИЛИ в отношении операндов типа bool.</span><span class="sxs-lookup"><span data-stu-id="13c74-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="13c74-109">Оператор `|=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор &#124;](../../../csharp/language-reference/operators/or-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="13c74-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c74-110">Пример</span><span class="sxs-lookup"><span data-stu-id="13c74-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="13c74-111">См. также</span><span class="sxs-lookup"><span data-stu-id="13c74-111">See Also</span></span>  
 [<span data-ttu-id="13c74-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="13c74-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="13c74-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="13c74-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="13c74-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="13c74-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
