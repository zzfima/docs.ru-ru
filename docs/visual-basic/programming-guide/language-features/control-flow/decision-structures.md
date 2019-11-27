---
title: Структуры решений
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353965"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="08002-102">Структуры решений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08002-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="08002-103">Visual Basic позволяет тестировать условия и выполнять различные операции в зависимости от результатов этого теста.</span><span class="sxs-lookup"><span data-stu-id="08002-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="08002-104">Можно проверить наличие условия, которое имеет значение true или false, для различных значений выражения или для различных исключений, создаваемых при выполнении последовательности инструкций.</span><span class="sxs-lookup"><span data-stu-id="08002-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="08002-105">На следующем рисунке показана структура принятия решений, которая проверяет истинность условия и принимает различные действия в зависимости от того, имеет ли оно значение true или false.</span><span class="sxs-lookup"><span data-stu-id="08002-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Блок-схема If...Then...Else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="08002-107">If...Then...Else, конструкция</span><span class="sxs-lookup"><span data-stu-id="08002-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="08002-108">`If...Then...Else`ные конструкции позволяют проверить одно или несколько условий и выполнить одну или несколько инструкций в зависимости от каждого условия.</span><span class="sxs-lookup"><span data-stu-id="08002-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="08002-109">Проверить условия и выполнить действия можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="08002-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="08002-110">Выполнить одну или несколько инструкций, если условие имеет значение `True`</span><span class="sxs-lookup"><span data-stu-id="08002-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="08002-111">Выполнить одну или несколько инструкций, если условие имеет значение `False`</span><span class="sxs-lookup"><span data-stu-id="08002-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="08002-112">Выполните некоторые инструкции, если условие `True` и другие, если это `False`</span><span class="sxs-lookup"><span data-stu-id="08002-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="08002-113">Протестируйте дополнительное условие, если предыдущие условия `False`</span><span class="sxs-lookup"><span data-stu-id="08002-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="08002-114">Структура элемента управления, которая предоставляет все эти возможности, — это [If... Затем... Else, инструкция](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08002-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="08002-115">Можно использовать однострочную версию, если имеется только один тест и один оператор для выполнения.</span><span class="sxs-lookup"><span data-stu-id="08002-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="08002-116">При наличии более сложного набора условий и действий можно использовать версию из нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="08002-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="08002-117">Select...Case Конструкция</span><span class="sxs-lookup"><span data-stu-id="08002-117">Select...Case Construction</span></span>  
 <span data-ttu-id="08002-118">Конструкция `Select...Case` позволяет оценивать выражение один раз и выполнять разные наборы инструкций на основе различных возможных значений.</span><span class="sxs-lookup"><span data-stu-id="08002-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="08002-119">Дополнительные сведения см. в разделе [SELECT... Case, инструкция](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08002-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="08002-120">Try...Catch...Finally, создание</span><span class="sxs-lookup"><span data-stu-id="08002-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="08002-121">`Try...Catch...Finally`ные конструкции позволяют запускать набор инструкций в среде, сохраняющей управление, если какая-либо из инструкций вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="08002-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="08002-122">Для разных исключений можно выполнять различные действия.</span><span class="sxs-lookup"><span data-stu-id="08002-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="08002-123">При необходимости можно указать блок кода, который будет выполняться перед выходом из всей `Try...Catch...Finally` построения, независимо от того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="08002-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="08002-124">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08002-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08002-125">Для многих структур управления при щелчке ключевого слова все ключевые слова в структуре выделяются.</span><span class="sxs-lookup"><span data-stu-id="08002-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="08002-126">Например, если щелкнуть `If` в конструкции `If...Then...Else`, будут выделены все экземпляры `If`, `Then`, `ElseIf`, `Else`и `End If` в конструкции.</span><span class="sxs-lookup"><span data-stu-id="08002-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="08002-127">Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите клавиши CTRL + SHIFT + стрелка вниз или CTRL + SHIFT + стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="08002-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08002-128">См. также</span><span class="sxs-lookup"><span data-stu-id="08002-128">See also</span></span>

- [<span data-ttu-id="08002-129">Поток управления</span><span class="sxs-lookup"><span data-stu-id="08002-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="08002-130">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="08002-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="08002-131">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="08002-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="08002-132">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="08002-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="08002-133">Оператор If</span><span class="sxs-lookup"><span data-stu-id="08002-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
