---
title: Структуры решений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 4aabb1eef717b06222696980d4cbce7a781fb567
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735251"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="c8e73-102">Структуры решений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e73-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="c8e73-103">Visual Basic позволяет проверять условия и выполнять различные операции в зависимости от результата этого теста.</span><span class="sxs-lookup"><span data-stu-id="c8e73-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="c8e73-104">Можно проверить условие true или false, для различных значений выражения, или для различных исключений, сформированных при выполнении последовательности инструкций.</span><span class="sxs-lookup"><span data-stu-id="c8e73-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="c8e73-105">На следующем рисунке структуру выбора, который проверяет условие и выполняет различные действия в зависимости от того, является ли это значение true или false.</span><span class="sxs-lookup"><span data-stu-id="c8e73-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="c8e73-106">![Блок-схема If... Затем... Else конструкции](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="c8e73-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="c8e73-107">Выполняет различные действия, если условие имеет значение true, а также если он имеет значение false</span><span class="sxs-lookup"><span data-stu-id="c8e73-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="c8e73-108">If... Затем... Else построения</span><span class="sxs-lookup"><span data-stu-id="c8e73-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="c8e73-109">`If...Then...Else` позволяют проверить одно или несколько условий и запустить один или несколько операторов для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="c8e73-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="c8e73-110">Можно проверить условия и действий одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c8e73-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="c8e73-111">Выполните один или несколько операторов, если условие равно `True`</span><span class="sxs-lookup"><span data-stu-id="c8e73-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="c8e73-112">Выполните один или несколько операторов, если условие равно `False`</span><span class="sxs-lookup"><span data-stu-id="c8e73-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="c8e73-113">Выполнить некоторые операторы, если условие равно `True` и другие — если `False`</span><span class="sxs-lookup"><span data-stu-id="c8e73-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="c8e73-114">Проверить дополнительное условие, если предыдущее условие `False`</span><span class="sxs-lookup"><span data-stu-id="c8e73-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="c8e73-115">Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8e73-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="c8e73-116">Если у вас есть только один тест и один оператор для запуска, можно использовать простую версию.</span><span class="sxs-lookup"><span data-stu-id="c8e73-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="c8e73-117">При наличии более сложного набора условий и действий, можно использовать несколько строк версии.</span><span class="sxs-lookup"><span data-stu-id="c8e73-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="c8e73-118">Выберите... Конструкции case</span><span class="sxs-lookup"><span data-stu-id="c8e73-118">Select...Case Construction</span></span>  
 <span data-ttu-id="c8e73-119">`Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений.</span><span class="sxs-lookup"><span data-stu-id="c8e73-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="c8e73-120">Дополнительные сведения см. в разделе [выберите... Оператор выбора](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8e73-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="c8e73-121">Try... CATCH... Наконец, создание</span><span class="sxs-lookup"><span data-stu-id="c8e73-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="c8e73-122">`Try...Catch...Finally` позволяют выполнять набор инструкций в среде, которая сохраняет контроль, если какой-либо инструкций вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="c8e73-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="c8e73-123">Можно выполнять разные действия для различных исключений.</span><span class="sxs-lookup"><span data-stu-id="c8e73-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="c8e73-124">При необходимости можно указать блок кода, который выполняется перед выходом из целого `Try...Catch...Finally` конструкции, независимо от того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="c8e73-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="c8e73-125">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8e73-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8e73-126">Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются.</span><span class="sxs-lookup"><span data-stu-id="c8e73-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="c8e73-127">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении.</span><span class="sxs-lookup"><span data-stu-id="c8e73-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="c8e73-128">Чтобы перейти к следующему или предыдущему выделенный ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="c8e73-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e73-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c8e73-129">See also</span></span>
- [<span data-ttu-id="c8e73-130">Поток управления</span><span class="sxs-lookup"><span data-stu-id="c8e73-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="c8e73-131">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="c8e73-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c8e73-132">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="c8e73-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="c8e73-133">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="c8e73-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="c8e73-134">Оператор If</span><span class="sxs-lookup"><span data-stu-id="c8e73-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
