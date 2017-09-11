---
title: "Оператор || (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
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
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="395dd-102">Оператор || (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="395dd-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="395dd-103">Оператор условного ИЛИ (`||`) выполняет логическую операцию ИЛИ со всеми своими операндами типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="395dd-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="395dd-104">Если результатом первого операнда является значение `true`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="395dd-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="395dd-105">Если первый операнд имеет значение `false`, второй оператор будет определять итоговое значение выражения ИЛИ (`true` или `false`).</span><span class="sxs-lookup"><span data-stu-id="395dd-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="395dd-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="395dd-106">Remarks</span></span>  
 <span data-ttu-id="395dd-107">Операция</span><span class="sxs-lookup"><span data-stu-id="395dd-107">The operation</span></span>  
  
```  
x || y  
```  
  
 <span data-ttu-id="395dd-108">соответствует операции</span><span class="sxs-lookup"><span data-stu-id="395dd-108">corresponds to the operation</span></span>  
  
```  
x | y  
```  
  
 <span data-ttu-id="395dd-109">кроме случаев, когда `x` имеет значение `true`. В таких ситуациях `y` не вычисляется, поскольку операция ИЛИ будет возвращать значение `true` независимо от значения `y`.</span><span class="sxs-lookup"><span data-stu-id="395dd-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="395dd-110">Это называется сокращенным вычислением.</span><span class="sxs-lookup"><span data-stu-id="395dd-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="395dd-111">Оператор условного ИЛИ не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.</span><span class="sxs-lookup"><span data-stu-id="395dd-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="395dd-112">Пример</span><span class="sxs-lookup"><span data-stu-id="395dd-112">Example</span></span>  
 <span data-ttu-id="395dd-113">В следующих примерах в выражении, использующем оператор `||`, вычисляется только первый операнд.</span><span class="sxs-lookup"><span data-stu-id="395dd-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="395dd-114">В выражении с оператором `|` вычисляются оба операнда.</span><span class="sxs-lookup"><span data-stu-id="395dd-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="395dd-115">Во втором примере в случае вычисления обоих операндов возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="395dd-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 <span data-ttu-id="395dd-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="395dd-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="395dd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="395dd-117">See Also</span></span>  
 <span data-ttu-id="395dd-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="395dd-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="395dd-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="395dd-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="395dd-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="395dd-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

