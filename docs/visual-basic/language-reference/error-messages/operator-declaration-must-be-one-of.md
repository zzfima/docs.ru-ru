---
title: 'Объявлении оператора должен быть одним из: +,-, *,-, -, ^, &amp;, например, Mod и, Or, Xor, не, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: f32935dd4aaccd3040655b418badc13c1988c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622277"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="65366-102">Объявлении оператора должен быть одним из: +,-, \*,\,/, ^, &amp;, например, Mod и, Or, Xor, не, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="65366-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="65366-103">Можно объявить только оператор, который подходит для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="65366-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="65366-104">В следующей таблице перечислены операторы, которые можно объявить.</span><span class="sxs-lookup"><span data-stu-id="65366-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="65366-105">Тип</span><span class="sxs-lookup"><span data-stu-id="65366-105">Type</span></span>|<span data-ttu-id="65366-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="65366-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="65366-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="65366-107">Unary</span></span>|<span data-ttu-id="65366-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="65366-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="65366-109">Binary</span><span class="sxs-lookup"><span data-stu-id="65366-109">Binary</span></span>|<span data-ttu-id="65366-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="65366-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="65366-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="65366-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="65366-112">Обратите внимание, что `=` оператор в списке бинарных операторов является оператором сравнения, не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="65366-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="65366-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="65366-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="65366-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="65366-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="65366-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="65366-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="65366-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="65366-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65366-117">См. также</span><span class="sxs-lookup"><span data-stu-id="65366-117">See also</span></span>
- [<span data-ttu-id="65366-118">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="65366-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="65366-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="65366-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="65366-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="65366-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="65366-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="65366-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="65366-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="65366-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
