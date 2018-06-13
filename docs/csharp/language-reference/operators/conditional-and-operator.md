---
title: Оператор &amp;&amp; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 15bb3e9702f04cc805af63767c7ecbfc68160368
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171919"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="f85dd-102">Оператор &amp;&amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f85dd-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="f85dd-103">Условный оператор И (`&&`) выполняет логическую операцию И применительно к своим операндам типа `bool`, но вычисляет только второй операнд при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f85dd-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f85dd-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f85dd-104">Remarks</span></span>  
 <span data-ttu-id="f85dd-105">Операция</span><span class="sxs-lookup"><span data-stu-id="f85dd-105">The operation</span></span>  
  
```csharp  
x && y  
```  
  
 <span data-ttu-id="f85dd-106">соответствует операции</span><span class="sxs-lookup"><span data-stu-id="f85dd-106">corresponds to the operation</span></span>  
  
```csharp  
x & y  
```  
  
 <span data-ttu-id="f85dd-107">за исключением того, что если `x` имеет значение `false`, `y` не вычисляется, так как результат операции И — `false` независимо от того, какое значение имеет `y`.</span><span class="sxs-lookup"><span data-stu-id="f85dd-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="f85dd-108">Это называется сокращенным вычислением.</span><span class="sxs-lookup"><span data-stu-id="f85dd-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="f85dd-109">Оператор условного И не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.</span><span class="sxs-lookup"><span data-stu-id="f85dd-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f85dd-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f85dd-110">Example</span></span>  
 <span data-ttu-id="f85dd-111">В приведенном ниже примере условное выражение во втором операторе `if` вычисляет только первый операнд, так как операнд возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="f85dd-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f85dd-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f85dd-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f85dd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f85dd-113">See Also</span></span>  
 [<span data-ttu-id="f85dd-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f85dd-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f85dd-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f85dd-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f85dd-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f85dd-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
