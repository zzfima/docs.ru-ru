---
title: 'Объявление оператора должен быть одним из: +,-, *,-, -, ^, &amp;, например, Mod и, Or, Xor, не так, <<>>,, =, <>, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: dac8613d79e3262e4d1fd6ad1599fd01182e329b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819376"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="95644-102">Объявлении оператора должен быть одним из: +,-, \*,\,/, ^, &amp;, например, Mod и, Or, Xor, не, \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="95644-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="95644-103">Можно объявить только оператор, который подходит для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="95644-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="95644-104">В следующей таблице перечислены операторы, которые можно объявить.</span><span class="sxs-lookup"><span data-stu-id="95644-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="95644-105">Тип</span><span class="sxs-lookup"><span data-stu-id="95644-105">Type</span></span>|<span data-ttu-id="95644-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="95644-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="95644-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="95644-107">Unary</span></span>|<span data-ttu-id="95644-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="95644-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="95644-109">Binary</span><span class="sxs-lookup"><span data-stu-id="95644-109">Binary</span></span>|<span data-ttu-id="95644-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="95644-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="95644-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="95644-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="95644-112">Обратите внимание, что `=` оператор в списке бинарных операторов является оператором сравнения, не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="95644-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="95644-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="95644-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95644-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="95644-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="95644-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="95644-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="95644-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="95644-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95644-117">См. также</span><span class="sxs-lookup"><span data-stu-id="95644-117">See also</span></span>

- [<span data-ttu-id="95644-118">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="95644-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="95644-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="95644-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="95644-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="95644-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="95644-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="95644-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="95644-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="95644-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
