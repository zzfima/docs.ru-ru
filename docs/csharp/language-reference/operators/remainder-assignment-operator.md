---
title: Оператор %= (Справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998660"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="14d6e-102">Оператор %= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="14d6e-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="14d6e-103">Оператор присваивания остатка.</span><span class="sxs-lookup"><span data-stu-id="14d6e-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14d6e-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="14d6e-104">Remarks</span></span>  
 <span data-ttu-id="14d6e-105">Выражение, использующее оператор присваивания `%=`, такое как</span><span class="sxs-lookup"><span data-stu-id="14d6e-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="14d6e-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="14d6e-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="14d6e-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="14d6e-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="14d6e-108">В числовых типах предварительно определенный [оператор %](../../../csharp/language-reference/operators/remainder-operator.md) используется для вычисления остатка от деления.</span><span class="sxs-lookup"><span data-stu-id="14d6e-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="14d6e-109">Оператор `%=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор %](../../../csharp/language-reference/operators/remainder-operator.md) (см. [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="14d6e-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14d6e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="14d6e-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="14d6e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="14d6e-111">See Also</span></span>

- [<span data-ttu-id="14d6e-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="14d6e-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="14d6e-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="14d6e-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="14d6e-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="14d6e-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
