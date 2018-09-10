---
title: Оператор /= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 8fff048cc441181aa3f0e3c0c638d501aaf9de3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526312"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7a5d3-102">Оператор /= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7a5d3-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="7a5d3-103">Оператор присваивания деления.</span><span class="sxs-lookup"><span data-stu-id="7a5d3-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a5d3-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a5d3-104">Remarks</span></span>  
 <span data-ttu-id="7a5d3-105">Выражение, использующее оператор присваивания `/=`, такое как</span><span class="sxs-lookup"><span data-stu-id="7a5d3-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="7a5d3-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="7a5d3-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="7a5d3-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="7a5d3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="7a5d3-108">В числовых типах [оператор /](../../../csharp/language-reference/operators/division-operator.md) используется для выполнения операций деления.</span><span class="sxs-lookup"><span data-stu-id="7a5d3-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="7a5d3-109">Оператор `/=` нельзя перегрузить напрямую, однако пользовательские типы могут перегрузить [оператор /](../../../csharp/language-reference/operators/division-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7a5d3-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7a5d3-110">В случае всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.</span><span class="sxs-lookup"><span data-stu-id="7a5d3-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a5d3-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7a5d3-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7a5d3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7a5d3-112">See Also</span></span>

- [<span data-ttu-id="7a5d3-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7a5d3-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7a5d3-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7a5d3-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7a5d3-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="7a5d3-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
