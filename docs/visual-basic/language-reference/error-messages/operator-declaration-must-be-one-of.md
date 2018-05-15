---
title: 'Объявлением оператора должен быть одним из: +,-, *,-, -, ^, &amp;, как и остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: eb1e7e8088ec8661be2469aff043c0f1a96e4d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="053d0-102">Объявлением оператора должен быть один из: +,-, \*,\,/, ^, &amp;, такие как остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="053d0-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="053d0-103">Можно объявить только оператор, который подходит для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="053d0-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="053d0-104">В следующей таблице перечислены операторы, которые могут быть объявлены.</span><span class="sxs-lookup"><span data-stu-id="053d0-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="053d0-105">Тип</span><span class="sxs-lookup"><span data-stu-id="053d0-105">Type</span></span>|<span data-ttu-id="053d0-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="053d0-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="053d0-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="053d0-107">Unary</span></span>|<span data-ttu-id="053d0-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="053d0-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="053d0-109">Binary</span><span class="sxs-lookup"><span data-stu-id="053d0-109">Binary</span></span>|<span data-ttu-id="053d0-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="053d0-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="053d0-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="053d0-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="053d0-112">Обратите внимание, что `=` в списке бинарных является оператором сравнения, не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="053d0-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="053d0-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="053d0-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="053d0-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="053d0-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="053d0-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="053d0-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="053d0-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="053d0-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053d0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="053d0-117">See Also</span></span>  
 [<span data-ttu-id="053d0-118">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="053d0-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="053d0-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="053d0-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="053d0-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="053d0-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="053d0-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="053d0-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="053d0-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="053d0-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
