---
title: "Практическое руководство. Проверка совпадения двух объектов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="09fab-102">Практическое руководство. Проверка совпадения двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09fab-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="09fab-103">Если у вас есть две переменные, которые ссылаются на объекты, можно использовать любой `Is` или `IsNot` оператор, или оба, чтобы определить, ссылаются ли они на один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="09fab-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="09fab-104">Чтобы проверить ли два объекта совпадают</span><span class="sxs-lookup"><span data-stu-id="09fab-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="09fab-105">Используйте [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) или [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="09fab-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="09fab-106">Может потребоваться выполнить определенные действия в зависимости от того, ссылаются ли два объекта на тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="09fab-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="09fab-107">Предыдущий пример сравнивает управления `c` с активным элементом управления в форме `f`.</span><span class="sxs-lookup"><span data-stu-id="09fab-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="09fab-108">Если нет активный элемент управления, или если имеется один, но он не является тем же экземпляром `c`, то `If` случае инструкция завершается ошибкой, а процедура возвращает без дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="09fab-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="09fab-109">Использование `Is` или `IsNot` в зависимости от предпочтений пользователя.</span><span class="sxs-lookup"><span data-stu-id="09fab-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="09fab-110">Один может оказаться легче другого в заданном выражении.</span><span class="sxs-lookup"><span data-stu-id="09fab-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fab-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09fab-111">See Also</span></span>  
 [<span data-ttu-id="09fab-112">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09fab-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
