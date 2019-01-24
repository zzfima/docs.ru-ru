---
title: Циклические структуры (Visual Basic)
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
ms.openlocfilehash: b72eef632b4564abc69e6ebef43b940eb0950e9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523393"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="31b3f-102">Циклические структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31b3f-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="31b3f-103">Циклические структуры Visual Basic позволяют выполнять одну или несколько строк кода несколько раз.</span><span class="sxs-lookup"><span data-stu-id="31b3f-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="31b3f-104">Операторы в циклической структуры можно повторить, пока условие `True`, пока условие `False`, указанное число раз или один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="31b3f-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="31b3f-105">Ниже показана структура цикла, выполняет набор инструкций, пока условие не примет значение true.</span><span class="sxs-lookup"><span data-stu-id="31b3f-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="31b3f-106">![Блок-схема Do... Цикл Until](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="31b3f-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="31b3f-107">Выполнение набора операторов, пока условие не станет true</span><span class="sxs-lookup"><span data-stu-id="31b3f-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="31b3f-108">Циклы while</span><span class="sxs-lookup"><span data-stu-id="31b3f-108">While Loops</span></span>  
 <span data-ttu-id="31b3f-109">`While`... `End While` выполняет набор инструкций до тех пор, пока условие, заданное в `While` инструкция является `True`.</span><span class="sxs-lookup"><span data-stu-id="31b3f-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="31b3f-110">Дополнительные сведения см. в разделе [хотя... Завершить оператор While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="31b3f-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="31b3f-111">Do-циклы</span><span class="sxs-lookup"><span data-stu-id="31b3f-111">Do Loops</span></span>  
 <span data-ttu-id="31b3f-112">`Do`... `Loop` позволяет проверить условие в начале или конце циклической структуры.</span><span class="sxs-lookup"><span data-stu-id="31b3f-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="31b3f-113">Можно также указать, следует ли повторять цикл, пока значение условия равно `True` или пока оно не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="31b3f-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="31b3f-114">Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="31b3f-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="31b3f-115">Циклы for</span><span class="sxs-lookup"><span data-stu-id="31b3f-115">For Loops</span></span>  
 <span data-ttu-id="31b3f-116">`For`... `Next` выполняет заданное количество раз.</span><span class="sxs-lookup"><span data-stu-id="31b3f-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="31b3f-117">Она использует переменную управления циклом, также называемый *счетчика*, чтобы отслеживать повторений.</span><span class="sxs-lookup"><span data-stu-id="31b3f-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="31b3f-118">Можно указать начальное и конечное значения для этого счетчика и при необходимости можно указать величину, на который он увеличивает за одно повторение к следующему.</span><span class="sxs-lookup"><span data-stu-id="31b3f-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="31b3f-119">Дополнительные сведения см. в разделе [для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="31b3f-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="31b3f-120">Циклы foreach</span><span class="sxs-lookup"><span data-stu-id="31b3f-120">For Each Loops</span></span>  
 <span data-ttu-id="31b3f-121">`For Each`... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="31b3f-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="31b3f-122">Укажите управляющей переменной цикла, но нет необходимости определения ее начального или конечного значения.</span><span class="sxs-lookup"><span data-stu-id="31b3f-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="31b3f-123">Дополнительные сведения см. в разделе [для каждого... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="31b3f-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b3f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="31b3f-124">See also</span></span>
- [<span data-ttu-id="31b3f-125">Поток управления</span><span class="sxs-lookup"><span data-stu-id="31b3f-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="31b3f-126">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="31b3f-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="31b3f-127">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="31b3f-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="31b3f-128">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="31b3f-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
