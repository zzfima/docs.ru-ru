---
title: "Циклические структуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- control flow, loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures
- statements [Visual Basic], loop
- Do statement, Do loops
- conditional statements, loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eba728d782bb5a6259467fb48f738f35580049c0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="ac6de-102">Циклические структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac6de-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ac6de-103">циклические структуры позволяют выполнять одну или несколько строк кода несколько раз.</span><span class="sxs-lookup"><span data-stu-id="ac6de-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="ac6de-104">Операторы в циклической структуре можно повторять, пока условие `True`, пока условие `False`, указанное число раз или один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ac6de-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="ac6de-105">Ниже показана структура цикла, выполняет набор инструкций, пока условие не станет true.</span><span class="sxs-lookup"><span data-stu-id="ac6de-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="ac6de-106">![Блок-схема Do... Пока цикл](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="ac6de-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="ac6de-107">Выполнение набора инструкций, пока условие не станет true</span><span class="sxs-lookup"><span data-stu-id="ac6de-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="ac6de-108">Циклы while</span><span class="sxs-lookup"><span data-stu-id="ac6de-108">While Loops</span></span>  
 <span data-ttu-id="ac6de-109">The `While`... `End While` выполняет набор инструкций до тех пор, пока условие, заданное в `While` инструкция является `True`.</span><span class="sxs-lookup"><span data-stu-id="ac6de-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="ac6de-110">Дополнительные сведения см. в разделе [во время... Завершить оператор While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ac6de-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="ac6de-111">Do-циклы</span><span class="sxs-lookup"><span data-stu-id="ac6de-111">Do Loops</span></span>  
 <span data-ttu-id="ac6de-112">The `Do`... `Loop` позволяет проверить условие в начале или в конце структуры цикла.</span><span class="sxs-lookup"><span data-stu-id="ac6de-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="ac6de-113">Можно также указать, следует ли повторять цикл, пока значение условия равно `True` или пока она не станет `True`.</span><span class="sxs-lookup"><span data-stu-id="ac6de-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="ac6de-114">Дополнительные сведения см. в разделе [сделать... Цикл инструкции](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ac6de-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="ac6de-115">Циклы for</span><span class="sxs-lookup"><span data-stu-id="ac6de-115">For Loops</span></span>  
 <span data-ttu-id="ac6de-116">The `For`... `Next` выполняет заданное количество раз.</span><span class="sxs-lookup"><span data-stu-id="ac6de-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="ac6de-117">Он использует переменная управления циклом, также называемый *счетчик*, чтобы отслеживать повторений.</span><span class="sxs-lookup"><span data-stu-id="ac6de-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="ac6de-118">Укажите начальное и конечное значения для этого счетчика и при необходимости можно указать сумму, по которому будет увеличен за одно повторение к следующему.</span><span class="sxs-lookup"><span data-stu-id="ac6de-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="ac6de-119">Дополнительные сведения см. в разделе [для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ac6de-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="ac6de-120">Для каждого из циклов</span><span class="sxs-lookup"><span data-stu-id="ac6de-120">For Each Loops</span></span>  
 <span data-ttu-id="ac6de-121">The `For Each`... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ac6de-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="ac6de-122">Укажите переменную цикла, но нет определения ее начального или конечного значения.</span><span class="sxs-lookup"><span data-stu-id="ac6de-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="ac6de-123">Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ac6de-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6de-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ac6de-124">See Also</span></span>  
 <span data-ttu-id="ac6de-125">[Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac6de-125">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="ac6de-126"> [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="ac6de-126"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="ac6de-127"> [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="ac6de-127"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="ac6de-128"> [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="ac6de-128"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span></span>
