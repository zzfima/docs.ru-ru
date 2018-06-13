---
title: Оператор == (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: f8356320817771cb559192c1ce720a80bf33bbf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273391"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fc7df-102">Оператор == (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fc7df-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="fc7df-103">Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="fc7df-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="fc7df-104">Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="fc7df-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="fc7df-105">Для типа `string` оператор `==` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="fc7df-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc7df-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc7df-106">Remarks</span></span>  
 <span data-ttu-id="fc7df-107">Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fc7df-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="fc7df-108">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="fc7df-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="fc7df-109">В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fc7df-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="fc7df-110">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="fc7df-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7df-111">Пример</span><span class="sxs-lookup"><span data-stu-id="fc7df-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fc7df-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fc7df-112">See Also</span></span>  
 [<span data-ttu-id="fc7df-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fc7df-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fc7df-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fc7df-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fc7df-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="fc7df-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
