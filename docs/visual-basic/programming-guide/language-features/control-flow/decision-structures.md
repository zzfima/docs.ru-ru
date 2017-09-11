---
title: "Структуры (Visual Basic) критериев | Документы Microsoft"
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
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
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
ms.openlocfilehash: dcbfb4bc3318d5f79870d04e606fab8bfa2dafb9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="39e5c-102">Структуры решений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39e5c-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="39e5c-103">позволяет проверять условия и выполнять различные операции в зависимости от результатов такой проверки.</span><span class="sxs-lookup"><span data-stu-id="39e5c-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="39e5c-104">Можно проверить условие true или false для различных значений выражений или исключений, выдаваемых при выполнении последовательности инструкций.</span><span class="sxs-lookup"><span data-stu-id="39e5c-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="39e5c-105">На следующем рисунке структуру решений, которая проверяет условие и выполняет различные действия в зависимости от того, является ли true или false.</span><span class="sxs-lookup"><span data-stu-id="39e5c-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="39e5c-106">![Таблица потока конструкции If... Затем... Конструкции else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="39e5c-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="39e5c-107">Выполняет различные действия, если условие имеет значение true, а если он имеет значение false</span><span class="sxs-lookup"><span data-stu-id="39e5c-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="39e5c-108">If... Затем... Конструкции else</span><span class="sxs-lookup"><span data-stu-id="39e5c-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="39e5c-109">`If...Then...Else`позволяют проверить одно или несколько условий и выполнить один или несколько операторов для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="39e5c-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="39e5c-110">Можно проверить условия и выполнить действия следующими способами:</span><span class="sxs-lookup"><span data-stu-id="39e5c-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="39e5c-111">Выполните один или несколько операторов, если условие равно`True`</span><span class="sxs-lookup"><span data-stu-id="39e5c-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="39e5c-112">Выполните один или несколько операторов, если условие равно`False`</span><span class="sxs-lookup"><span data-stu-id="39e5c-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="39e5c-113">Выполнить некоторые операторы, если условие равно `True` и другие — если`False`</span><span class="sxs-lookup"><span data-stu-id="39e5c-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="39e5c-114">Проверить дополнительное условие, если предыдущее условие`False`</span><span class="sxs-lookup"><span data-stu-id="39e5c-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="39e5c-115">Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="39e5c-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="39e5c-116">Можно использовать простую версию при наличии только одного условия и одного оператора для выполнения.</span><span class="sxs-lookup"><span data-stu-id="39e5c-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="39e5c-117">Если имеется более сложный набор условий и действий, можно использовать составную версию.</span><span class="sxs-lookup"><span data-stu-id="39e5c-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="39e5c-118">Выберите... Конструкции case</span><span class="sxs-lookup"><span data-stu-id="39e5c-118">Select...Case Construction</span></span>  
 <span data-ttu-id="39e5c-119">`Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений.</span><span class="sxs-lookup"><span data-stu-id="39e5c-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="39e5c-120">Дополнительные сведения см. в разделе [выберите... Case-оператор](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="39e5c-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="39e5c-121">Конструкция TRY... CATCH... Наконец построения</span><span class="sxs-lookup"><span data-stu-id="39e5c-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="39e5c-122">`Try...Catch...Finally`позволяют выполнять набор инструкций в среде, которая сохраняет управление, если какой-либо из операторов вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="39e5c-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="39e5c-123">Можно выполнять различные действия для различных исключений.</span><span class="sxs-lookup"><span data-stu-id="39e5c-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="39e5c-124">Можно указать блок кода, который выполняется перед выходом из всей `Try...Catch...Finally` конструкции, независимо от того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="39e5c-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="39e5c-125">Дополнительные сведения см. в разделе [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="39e5c-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39e5c-126">Для многих структур управления что при щелчке ключевого слова, все ключевые слова в структуре выделяются.</span><span class="sxs-lookup"><span data-stu-id="39e5c-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="39e5c-127">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` при построении выделяются.</span><span class="sxs-lookup"><span data-stu-id="39e5c-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="39e5c-128">Чтобы переместить выделенные следующего или предыдущего ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="39e5c-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e5c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="39e5c-129">See Also</span></span>  
 <span data-ttu-id="39e5c-130">[Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="39e5c-130">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="39e5c-131"> [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="39e5c-131"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="39e5c-132"> [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="39e5c-132"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="39e5c-133"> [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="39e5c-133"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="39e5c-134"> [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)</span><span class="sxs-lookup"><span data-stu-id="39e5c-134"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span></span>
