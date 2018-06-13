---
title: 'Оператор ?: (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 68e7daac63a5f7d9bd1f48adfdee973bd695a13e
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457220"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ac726-102">Оператор ?: (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ac726-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="ac726-103">Условный оператор (`?:`), известный как тернарный условный оператор, возвращает одно из двух значений в зависимости от значения логического выражения.</span><span class="sxs-lookup"><span data-stu-id="ac726-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="ac726-104">Для условного оператора используется следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="ac726-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="ac726-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac726-105">Remarks</span></span>  
 <span data-ttu-id="ac726-106">Параметр `condition` должен иметь значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="ac726-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="ac726-107">Если параметр `condition` имеет значение `true`, вычисляется выражение `first_expression` и итог этого вычисления становится результатом.</span><span class="sxs-lookup"><span data-stu-id="ac726-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="ac726-108">Если параметр `condition` имеет значение `false`, вычисляется выражение `second_expression` и итог этого вычисления становится результатом.</span><span class="sxs-lookup"><span data-stu-id="ac726-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="ac726-109">В любом случае вычисляется только одно из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="ac726-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="ac726-110">Параметры `first_expression` и `second_expression` должны быть одинакового типа или должно существовать неявное преобразование из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="ac726-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="ac726-111">Расчеты, которые в другом случае требовали бы уточнения конструкции `if-else`, можно выражать с помощью условного оператора.</span><span class="sxs-lookup"><span data-stu-id="ac726-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="ac726-112">Например, в следующем коде сначала используется оператор `if`, а затем — условный оператор для классификации целого числа как положительного или отрицательного.</span><span class="sxs-lookup"><span data-stu-id="ac726-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="ac726-113">Условный оператор имеет правую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="ac726-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="ac726-114">Выражение `a ? b : c ? d : e` вычисляется как `a ? b : (c ? d : e)`, а не как `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="ac726-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="ac726-115">Условный оператор не может быть перегружен.</span><span class="sxs-lookup"><span data-stu-id="ac726-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac726-116">Пример</span><span class="sxs-lookup"><span data-stu-id="ac726-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ac726-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ac726-117">See Also</span></span>  
 [<span data-ttu-id="ac726-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ac726-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ac726-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ac726-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ac726-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ac726-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="ac726-121">if-else</span><span class="sxs-lookup"><span data-stu-id="ac726-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 <span data-ttu-id="ac726-122">[Операторы ?. и ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="ac726-122">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
 [<span data-ttu-id="ac726-123">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="ac726-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
