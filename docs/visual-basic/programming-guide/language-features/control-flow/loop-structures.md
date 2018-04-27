---
title: Циклические структуры (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c13f2cc6546a652f0967bd83369d8af5998f7e2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="62847-102">Циклические структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62847-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="62847-103">Циклические структуры Visual Basic позволяют выполнять одну или несколько строк кода несколько раз.</span><span class="sxs-lookup"><span data-stu-id="62847-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="62847-104">Операторы в циклической структуры можно повторять, пока условие `True`, пока условие `False`, указанное число раз или один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="62847-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="62847-105">На следующем рисунке структура цикла, выполняет набор инструкций, пока условие не станет true.</span><span class="sxs-lookup"><span data-stu-id="62847-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="62847-106">![Блок-схема Do... Пока цикл](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="62847-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="62847-107">Выполнение набора инструкций, пока условие не станет true</span><span class="sxs-lookup"><span data-stu-id="62847-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="62847-108">Циклы while</span><span class="sxs-lookup"><span data-stu-id="62847-108">While Loops</span></span>  
 <span data-ttu-id="62847-109">`While`... `End While` выполняет набор инструкций, пока условие, заданное в `While` инструкция является `True`.</span><span class="sxs-lookup"><span data-stu-id="62847-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="62847-110">Дополнительные сведения см. в разделе [во время... Завершить оператор While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62847-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="62847-111">Do-циклы</span><span class="sxs-lookup"><span data-stu-id="62847-111">Do Loops</span></span>  
 <span data-ttu-id="62847-112">`Do`... `Loop` позволяет проверить условие в начале или конце структуры цикла.</span><span class="sxs-lookup"><span data-stu-id="62847-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="62847-113">Можно также указать, следует ли повторять цикл, пока значение условия равно `True` или пока она не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="62847-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="62847-114">Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62847-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="62847-115">Циклы for</span><span class="sxs-lookup"><span data-stu-id="62847-115">For Loops</span></span>  
 <span data-ttu-id="62847-116">`For`... `Next` выполняет заданное количество раз.</span><span class="sxs-lookup"><span data-stu-id="62847-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="62847-117">Она использует переменную управления циклом, также называемый *счетчика*, чтобы отслеживать повторений.</span><span class="sxs-lookup"><span data-stu-id="62847-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="62847-118">Можно указать начальное и конечное значения для этого счетчика и при необходимости можно указать суммы, по которому будет увеличен за одно повторение к следующему.</span><span class="sxs-lookup"><span data-stu-id="62847-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="62847-119">Дополнительные сведения см. в разделе [для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62847-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="62847-120">Для каждого из циклов</span><span class="sxs-lookup"><span data-stu-id="62847-120">For Each Loops</span></span>  
 <span data-ttu-id="62847-121">`For Each`... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="62847-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="62847-122">Укажите управляющей переменной цикла, но нет определения ее начального или конечного значения.</span><span class="sxs-lookup"><span data-stu-id="62847-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="62847-123">Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="62847-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62847-124">См. также</span><span class="sxs-lookup"><span data-stu-id="62847-124">See Also</span></span>  
 [<span data-ttu-id="62847-125">Поток управления</span><span class="sxs-lookup"><span data-stu-id="62847-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="62847-126">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="62847-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="62847-127">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="62847-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="62847-128">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="62847-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
