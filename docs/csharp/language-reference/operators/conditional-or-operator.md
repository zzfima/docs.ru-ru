---
title: Оператор || (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: d22e57d097edb0fe52b604e9c6431e167c410f0b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171810"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="383ad-102">Оператор || (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="383ad-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="383ad-103">Оператор условного ИЛИ (`||`) выполняет логическую операцию ИЛИ со всеми своими операндами типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="383ad-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="383ad-104">Если результатом первого операнда является значение `true`, второй операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="383ad-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="383ad-105">Если первый операнд имеет значение `false`, второй оператор будет определять итоговое значение выражения ИЛИ (`true` или `false`).</span><span class="sxs-lookup"><span data-stu-id="383ad-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="383ad-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="383ad-106">Remarks</span></span>  
 <span data-ttu-id="383ad-107">Операция</span><span class="sxs-lookup"><span data-stu-id="383ad-107">The operation</span></span>  
  
```csharp  
x || y  
```  
  
 <span data-ttu-id="383ad-108">соответствует операции</span><span class="sxs-lookup"><span data-stu-id="383ad-108">corresponds to the operation</span></span>  
  
```csharp  
x | y  
```  
  
 <span data-ttu-id="383ad-109">кроме случаев, когда `x` имеет значение `true`. В таких ситуациях `y` не вычисляется, поскольку операция ИЛИ будет возвращать значение `true` независимо от значения `y`.</span><span class="sxs-lookup"><span data-stu-id="383ad-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="383ad-110">Это называется сокращенным вычислением.</span><span class="sxs-lookup"><span data-stu-id="383ad-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="383ad-111">Оператор условного ИЛИ не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.</span><span class="sxs-lookup"><span data-stu-id="383ad-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="383ad-112">Пример</span><span class="sxs-lookup"><span data-stu-id="383ad-112">Example</span></span>  
 <span data-ttu-id="383ad-113">В следующих примерах в выражении, использующем оператор `||`, вычисляется только первый операнд.</span><span class="sxs-lookup"><span data-stu-id="383ad-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="383ad-114">В выражении с оператором `|` вычисляются оба операнда.</span><span class="sxs-lookup"><span data-stu-id="383ad-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="383ad-115">Во втором примере в случае вычисления обоих операндов возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="383ad-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="383ad-116">См. также</span><span class="sxs-lookup"><span data-stu-id="383ad-116">See Also</span></span>  
 [<span data-ttu-id="383ad-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="383ad-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="383ad-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="383ad-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="383ad-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="383ad-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
