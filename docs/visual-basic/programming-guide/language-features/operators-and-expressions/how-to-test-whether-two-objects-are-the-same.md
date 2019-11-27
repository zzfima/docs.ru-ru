---
title: Практическое руководство. Проверка совпадения двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343623"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="00a8a-102">Практическое руководство. Проверка совпадения двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00a8a-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="00a8a-103">При наличии двух переменных, ссылающихся на объекты, можно использовать либо оператор `Is` или `IsNot`, либо и то, и другое, чтобы определить, ссылаются ли они на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="00a8a-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="00a8a-104">Проверка того, совпадают ли два объекта</span><span class="sxs-lookup"><span data-stu-id="00a8a-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="00a8a-105">Используйте [оператор is](../../../../visual-basic/language-reference/operators/is-operator.md) или [IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="00a8a-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="00a8a-106">Может потребоваться выполнить определенное действие в зависимости от того, ссылаются ли два объекта на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="00a8a-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="00a8a-107">Предыдущий пример сравнивает `c` элемента управления с активным элементом управления в `f`формы.</span><span class="sxs-lookup"><span data-stu-id="00a8a-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="00a8a-108">Если нет активного элемента управления или если он существует, но он не является тем же экземпляром элемента управления, что и `c`, то инструкция `If` завершается ошибкой и процедура возвращается без дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="00a8a-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="00a8a-109">Независимо от того, используется ли `Is` или `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="00a8a-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="00a8a-110">Один из них может быть проще читать, чем другой в данном выражении.</span><span class="sxs-lookup"><span data-stu-id="00a8a-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a8a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="00a8a-111">See also</span></span>

- [<span data-ttu-id="00a8a-112">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00a8a-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
