---
title: Практическое руководство. Проверка совпадения двух объектов же (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864381"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="971d5-102">Практическое руководство. Проверка совпадения двух объектов же (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="971d5-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="971d5-103">Если у вас есть две переменные, которые ссылаются на объекты, можно использовать либо `Is` или `IsNot` оператора, или оба, чтобы определить, ссылаются ли они на один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="971d5-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="971d5-104">Для проверки совпадения двух объектов</span><span class="sxs-lookup"><span data-stu-id="971d5-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="971d5-105">Используйте [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) или [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="971d5-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="971d5-106">Может потребоваться выполнить определенные действия в зависимости от того, ссылаются ли два объекта на тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="971d5-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="971d5-107">В предыдущем примере сравнивается управления `c` с активным элементом управления в форме `f`.</span><span class="sxs-lookup"><span data-stu-id="971d5-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="971d5-108">Если отсутствует активный элемент управления отсутствует, или нет, но он является не тем же экземпляром `c`, а затем `If` инструкция завершается ошибкой и процедура возвращает без дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="971d5-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="971d5-109">Использование `Is` или `IsNot` в зависимости от предпочтений пользователя.</span><span class="sxs-lookup"><span data-stu-id="971d5-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="971d5-110">Одной может быть более удобным для чтения, чем-то в заданном выражении.</span><span class="sxs-lookup"><span data-stu-id="971d5-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971d5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="971d5-111">See also</span></span>

- [<span data-ttu-id="971d5-112">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="971d5-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
