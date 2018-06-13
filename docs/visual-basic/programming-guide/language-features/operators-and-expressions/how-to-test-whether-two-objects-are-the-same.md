---
title: Практическое руководство. Проверка совпадения двух объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 005c91e6f4ec556a7e1bf255b47c8276a5d3d185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647609"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="10697-102">Практическое руководство. Проверка совпадения двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10697-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="10697-103">Если у вас есть две переменные, которые ссылаются на объекты, можно использовать любой `Is` или `IsNot` оператор, или оба, чтобы определить, ссылаются ли они на один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="10697-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="10697-104">Чтобы проверить ли два объекта совпадают</span><span class="sxs-lookup"><span data-stu-id="10697-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="10697-105">Используйте [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) или [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="10697-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="10697-106">Может потребоваться выполнить определенные действия в зависимости от того, ссылаются ли два объекта на тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="10697-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="10697-107">Предыдущий пример сравнивает управления `c` с активным элементом управления в форме `f`.</span><span class="sxs-lookup"><span data-stu-id="10697-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="10697-108">Если нет активный элемент управления, или если имеется один, но он не является тем же экземпляром `c`, то `If` случае инструкция завершается ошибкой, а процедура возвращает без дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="10697-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="10697-109">Использование `Is` или `IsNot` в зависимости от предпочтений пользователя.</span><span class="sxs-lookup"><span data-stu-id="10697-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="10697-110">Один может оказаться легче другого в заданном выражении.</span><span class="sxs-lookup"><span data-stu-id="10697-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10697-111">См. также</span><span class="sxs-lookup"><span data-stu-id="10697-111">See Also</span></span>  
 [<span data-ttu-id="10697-112">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="10697-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
