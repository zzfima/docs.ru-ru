---
title: "Практическое руководство. Вызов обработчика событий в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52b4b6ca8b03d8301535d6aeedc3bd0190d8527f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="4b723-102">Практическое руководство. Вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b723-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="4b723-103">*Событий* — это действие или условие — например мыши щелчок или кредитный лимит превышение, которое распознается некоторым компонентом программы и для которого можно написать код для ответа.</span><span class="sxs-lookup"><span data-stu-id="4b723-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="4b723-104">*Обработчик событий* — это код, предназначенный для обработки события.</span><span class="sxs-lookup"><span data-stu-id="4b723-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="4b723-105">Обработчик событий в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] — `Sub` процедура.</span><span class="sxs-lookup"><span data-stu-id="4b723-105">An event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="4b723-106">Тем не менее, не вызывается обычно его же, как другие `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4b723-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="4b723-107">Вместо этого необходимо определить процедуру в качестве обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="4b723-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="4b723-108">Это можно сделать с помощью [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение и [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) переменной, или с [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4b723-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4b723-109">С помощью `Handles` предложение является по умолчанию способ объявления обработчика событий в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b723-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="4b723-110">Это способ записи обработчиков событий в конструкторах при программировании в интегрированной среде разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="4b723-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="4b723-111">`AddHandler` Инструкция подходит для динамического создания событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b723-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="4b723-112">При возникновении события, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] автоматически вызывает процедуру обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4b723-112">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="4b723-113">Любой код, который имеет доступ к событию может привести к его выполнения, выполнив [оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4b723-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="4b723-114">С одним событием можно связать несколько обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="4b723-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="4b723-115">В некоторых случаях можно отменить привязку обработчика события.</span><span class="sxs-lookup"><span data-stu-id="4b723-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="4b723-116">Дополнительные сведения см. в статье [Events (Visual Basic)](../../../../visual-basic/programming-guide/language-features/events/index.md) (События в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4b723-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="4b723-117">Для вызова обработчика событий с помощью WithEvents и дескрипторов</span><span class="sxs-lookup"><span data-stu-id="4b723-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="4b723-118">Убедитесь, что событие объявляется с [оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4b723-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="4b723-119">Объявите переменную объекта на уровне модуля или класса уровня, с помощью [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4b723-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="4b723-120">`As` Предложение для этой переменной необходимо указать класс, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="4b723-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="4b723-121">В объявлении обработки событий `Sub` процедуру, добавьте [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение, определяющее `WithEvents` переменной и имя события.</span><span class="sxs-lookup"><span data-stu-id="4b723-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="4b723-122">При возникновении события, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] автоматически вызывает `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4b723-122">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4b723-123">Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.</span><span class="sxs-lookup"><span data-stu-id="4b723-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4b723-124">В следующем примере определяется событие и `WithEvents` переменную, которая ссылается на класс, который инициирует событие.</span><span class="sxs-lookup"><span data-stu-id="4b723-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="4b723-125">Обработка событий `Sub` процедуры используется `Handles` предложений, чтобы указать класс и обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="4b723-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="4b723-126">Для вызова обработчика событий с помощью AddHandler</span><span class="sxs-lookup"><span data-stu-id="4b723-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="4b723-127">Убедитесь, что событие объявляется с `Event` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4b723-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="4b723-128">Выполнение [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для динамического связывания обработки события `Sub` процедуры с событием.</span><span class="sxs-lookup"><span data-stu-id="4b723-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="4b723-129">При возникновении события, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] автоматически вызывает `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4b723-129">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4b723-130">Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.</span><span class="sxs-lookup"><span data-stu-id="4b723-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4b723-131">В следующем примере определяется `Sub` процедура будет обрабатывать <xref:System.Windows.Forms.Form.Closing> события формы.</span><span class="sxs-lookup"><span data-stu-id="4b723-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="4b723-132">Затем он использует [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) связываемый `catchClose` процедуры в качестве обработчика событий для <xref:System.Windows.Forms.Form.Closing>.</span><span class="sxs-lookup"><span data-stu-id="4b723-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="4b723-133">Можно отменить привязку обработчика событий из события, выполнив [оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4b723-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b723-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4b723-134">See Also</span></span>  
 [<span data-ttu-id="4b723-135">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4b723-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4b723-136">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="4b723-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="4b723-137">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="4b723-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="4b723-138">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="4b723-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="4b723-139">Практическое руководство. Создание процедуры</span><span class="sxs-lookup"><span data-stu-id="4b723-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="4b723-140">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="4b723-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
