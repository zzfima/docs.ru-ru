---
title: Оператор /= (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 26096d9b5dfc565c9933f1ed8ffb241dc900d9ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="97e59-102">Оператор /= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="97e59-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="97e59-103">Оператор присваивания деления.</span><span class="sxs-lookup"><span data-stu-id="97e59-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97e59-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="97e59-104">Remarks</span></span>  
 <span data-ttu-id="97e59-105">Выражение, использующее оператор присваивания `/=`, такое как</span><span class="sxs-lookup"><span data-stu-id="97e59-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="97e59-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="97e59-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="97e59-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="97e59-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="97e59-108">В числовых типах [оператор /](../../../csharp/language-reference/operators/division-operator.md) используется для выполнения операций деления.</span><span class="sxs-lookup"><span data-stu-id="97e59-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="97e59-109">Оператор `/=` нельзя перегрузить напрямую, однако пользовательские типы могут перегрузить [оператор /](../../../csharp/language-reference/operators/division-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="97e59-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="97e59-110">В случае всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.</span><span class="sxs-lookup"><span data-stu-id="97e59-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97e59-111">Пример</span><span class="sxs-lookup"><span data-stu-id="97e59-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="97e59-112">См. также</span><span class="sxs-lookup"><span data-stu-id="97e59-112">See Also</span></span>  
 [<span data-ttu-id="97e59-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="97e59-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="97e59-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="97e59-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="97e59-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="97e59-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
