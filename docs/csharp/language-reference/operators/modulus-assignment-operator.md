---
title: "Оператор %= (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%=_CSharpKeyword'
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9bafd0078153e29fbf923948d9b380d4795c3d35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2fad0-102">Оператор %= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2fad0-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="2fad0-103">Оператор присваивания остатка.</span><span class="sxs-lookup"><span data-stu-id="2fad0-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fad0-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fad0-104">Remarks</span></span>  
 <span data-ttu-id="2fad0-105">Выражение, использующее оператор присваивания `%=`, такое как</span><span class="sxs-lookup"><span data-stu-id="2fad0-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="2fad0-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="2fad0-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="2fad0-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="2fad0-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="2fad0-108">В числовых типах предварительно определенный [оператор %](../../../csharp/language-reference/operators/modulus-operator.md) используется для вычисления остатка от деления.</span><span class="sxs-lookup"><span data-stu-id="2fad0-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="2fad0-109">Оператор `%=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор %](../../../csharp/language-reference/operators/modulus-operator.md) (см. [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="2fad0-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fad0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2fad0-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2fad0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2fad0-111">See Also</span></span>  
 [<span data-ttu-id="2fad0-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2fad0-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2fad0-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2fad0-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2fad0-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2fad0-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
