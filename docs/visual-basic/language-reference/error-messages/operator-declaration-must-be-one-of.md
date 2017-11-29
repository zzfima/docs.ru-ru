---
title: "Объявлением оператора должен быть одним из: +,-, *,-, -, ^, &amp;, как и остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords: BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="08a6f-102">Объявлением оператора должен быть один из: +,-, *,\,/, ^, &amp;, такие как остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="08a6f-102">Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="08a6f-103">Можно объявить только оператор, который подходит для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="08a6f-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="08a6f-104">В следующей таблице перечислены операторы, которые могут быть объявлены.</span><span class="sxs-lookup"><span data-stu-id="08a6f-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="08a6f-105">Тип</span><span class="sxs-lookup"><span data-stu-id="08a6f-105">Type</span></span>|<span data-ttu-id="08a6f-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="08a6f-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="08a6f-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="08a6f-107">Unary</span></span>|<span data-ttu-id="08a6f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="08a6f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="08a6f-109">Binary</span><span class="sxs-lookup"><span data-stu-id="08a6f-109">Binary</span></span>|<span data-ttu-id="08a6f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="08a6f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="08a6f-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="08a6f-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="08a6f-112">Обратите внимание, что `=` в списке бинарных является оператором сравнения, не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="08a6f-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="08a6f-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="08a6f-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08a6f-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="08a6f-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="08a6f-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="08a6f-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="08a6f-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="08a6f-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a6f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="08a6f-117">See Also</span></span>  
 [<span data-ttu-id="08a6f-118">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="08a6f-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="08a6f-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="08a6f-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="08a6f-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="08a6f-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="08a6f-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="08a6f-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="08a6f-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="08a6f-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
