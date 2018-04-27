---
title: Структуры решений (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b89d6f9b27e086b657c29f3353b63cdd855ae19
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="1edb5-102">Структуры решений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1edb5-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="1edb5-103">Visual Basic позволяет проверять условия и выполнять различные операции в зависимости от результатов этой проверки.</span><span class="sxs-lookup"><span data-stu-id="1edb5-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="1edb5-104">Можно проверить условие true или false, для различных значений выражений или исключений, выдаваемых при выполнении ряд инструкций.</span><span class="sxs-lookup"><span data-stu-id="1edb5-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="1edb5-105">На следующем рисунке структуру выбора, который проверяет условие и выполняет различные действия в зависимости от того, является ли значение true или false.</span><span class="sxs-lookup"><span data-stu-id="1edb5-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="1edb5-106">![Блок-схема If... Затем... Else построения](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="1edb5-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="1edb5-107">Выполняет различные действия, если условие имеет значение true, а если он имеет значение false</span><span class="sxs-lookup"><span data-stu-id="1edb5-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="1edb5-108">If... Затем... Else построения</span><span class="sxs-lookup"><span data-stu-id="1edb5-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="1edb5-109">`If...Then...Else` позволяют проверить одно или несколько условий и выполнить один или несколько операторов для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="1edb5-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="1edb5-110">Можно проверить условия и выполнения действий одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="1edb5-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="1edb5-111">Запустить один или несколько операторов, если условие равно `True`</span><span class="sxs-lookup"><span data-stu-id="1edb5-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="1edb5-112">Запустить один или несколько операторов, если условие равно `False`</span><span class="sxs-lookup"><span data-stu-id="1edb5-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="1edb5-113">Выполнить некоторые операторы, если условие равно `True` и другие — если `False`</span><span class="sxs-lookup"><span data-stu-id="1edb5-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="1edb5-114">Проверить дополнительное условие, если предыдущее условие `False`</span><span class="sxs-lookup"><span data-stu-id="1edb5-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="1edb5-115">Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1edb5-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="1edb5-116">Можно использовать простую версию при наличии только одного условия и одного оператора для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1edb5-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="1edb5-117">Если имеется более сложный набор условий и действий, можно использовать версию несколько строк.</span><span class="sxs-lookup"><span data-stu-id="1edb5-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="1edb5-118">Выберите... Case построения</span><span class="sxs-lookup"><span data-stu-id="1edb5-118">Select...Case Construction</span></span>  
 <span data-ttu-id="1edb5-119">`Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений.</span><span class="sxs-lookup"><span data-stu-id="1edb5-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="1edb5-120">Дополнительные сведения см. в разделе [выберите... Оператор выбора](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1edb5-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="1edb5-121">Конструкция TRY... CATCH... Конструкции finally</span><span class="sxs-lookup"><span data-stu-id="1edb5-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="1edb5-122">`Try...Catch...Finally` позволяют выполнять набор инструкций в среде, которая сохраняет управление, если какой-либо из операторов вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="1edb5-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="1edb5-123">Можно выполнять различные действия для различных исключений.</span><span class="sxs-lookup"><span data-stu-id="1edb5-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="1edb5-124">При необходимости можно указать блок кода, который выполняется перед выходом из всей `Try...Catch...Finally` конструкция, независимо от того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="1edb5-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="1edb5-125">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1edb5-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1edb5-126">Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются.</span><span class="sxs-lookup"><span data-stu-id="1edb5-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="1edb5-127">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении.</span><span class="sxs-lookup"><span data-stu-id="1edb5-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="1edb5-128">Чтобы переместить выделенный следующей или предыдущей ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="1edb5-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edb5-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1edb5-129">See Also</span></span>  
 [<span data-ttu-id="1edb5-130">Поток управления</span><span class="sxs-lookup"><span data-stu-id="1edb5-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="1edb5-131">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="1edb5-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="1edb5-132">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="1edb5-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="1edb5-133">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="1edb5-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="1edb5-134">Оператор If</span><span class="sxs-lookup"><span data-stu-id="1edb5-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
