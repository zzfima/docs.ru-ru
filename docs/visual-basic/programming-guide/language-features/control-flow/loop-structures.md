---
title: Циклические структуры
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 0a75205a7d52c332094d624d082e5db3e89447f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353919"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="8917b-102">Циклические структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8917b-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="8917b-103">Структуры циклов Visual Basic позволяют многократно выполнять одну или несколько строк кода.</span><span class="sxs-lookup"><span data-stu-id="8917b-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="8917b-104">Можно повторять операторы в структуре цикла, пока условие не будет `True`, пока условие не будет `False`, указанное число раз или один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8917b-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="8917b-105">На следующем рисунке показана структура цикла, выполняющая набор инструкций, пока условие не примет значение true:</span><span class="sxs-lookup"><span data-stu-id="8917b-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Блок-схема, на которой показано действие Do... Цикл Until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="8917b-107">Циклы while</span><span class="sxs-lookup"><span data-stu-id="8917b-107">While Loops</span></span>  
 <span data-ttu-id="8917b-108">Конструкция `While`...`End While` запускает набор инструкций, если условие, указанное в инструкции `While`, имеет `True`.</span><span class="sxs-lookup"><span data-stu-id="8917b-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="8917b-109">Дополнительные сведения см. в разделе [while... Конец оператора while](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8917b-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="8917b-110">Do Loops</span><span class="sxs-lookup"><span data-stu-id="8917b-110">Do Loops</span></span>  
 <span data-ttu-id="8917b-111">Конструкция `Do`...`Loop` позволяет проверить условие либо в начале, либо в конце структуры цикла.</span><span class="sxs-lookup"><span data-stu-id="8917b-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="8917b-112">Можно также указать, следует ли повторять цикл, пока условие остается `True` или пока оно не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="8917b-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="8917b-113">Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8917b-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="8917b-114">Циклы for</span><span class="sxs-lookup"><span data-stu-id="8917b-114">For Loops</span></span>  
 <span data-ttu-id="8917b-115">Конструкция `For`...`Next` выполняет цикл в заданное число раз.</span><span class="sxs-lookup"><span data-stu-id="8917b-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="8917b-116">Для наблюдения за повторениями используется управляющая переменная цикла, также называемая *счетчиком*.</span><span class="sxs-lookup"><span data-stu-id="8917b-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="8917b-117">Вы указываете начальное и конечное значения для этого счетчика, а также можете указать величину, на которую увеличивается от одного повтора до следующего.</span><span class="sxs-lookup"><span data-stu-id="8917b-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="8917b-118">Дополнительные сведения см. в разделе [for... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8917b-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="8917b-119">Циклы for each</span><span class="sxs-lookup"><span data-stu-id="8917b-119">For Each Loops</span></span>  
 <span data-ttu-id="8917b-120">Конструкция `For Each`...`Next` запускает набор инструкций один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8917b-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="8917b-121">Вы указываете управляющую переменную цикла, но не нужно определять начальные или конечные значения для нее.</span><span class="sxs-lookup"><span data-stu-id="8917b-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="8917b-122">Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8917b-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8917b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8917b-123">See also</span></span>

- [<span data-ttu-id="8917b-124">Поток управления</span><span class="sxs-lookup"><span data-stu-id="8917b-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="8917b-125">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="8917b-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="8917b-126">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="8917b-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="8917b-127">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="8917b-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
