---
title: "Практическое руководство: вызов обработчика событий в Visual Basic | Документы Microsoft"
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
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
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
ms.openlocfilehash: dc0174d50c7b5f5cda9d057bce39960b3e563f4e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="c0f9d-102">Практическое руководство. Вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0f9d-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="c0f9d-103">*Событий* — это действие или условие — например мышью, щелчок или кредитный лимит превышение, которое распознается некоторым компонентом программы и для которого можно написать код для ответа.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="c0f9d-104">*Обработчик событий* является код, предназначенный для обработки события.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="c0f9d-105">Обработчик событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] — `Sub` процедура.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-105">An event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="c0f9d-106">Тем не менее, не вызывается обычно он же так, как другие `Sub` процедур.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="c0f9d-107">Вместо этого необходимо определить процедуру в качестве обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="c0f9d-108">Это можно сделать с помощью [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложения и [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) переменной, или с [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="c0f9d-109">С помощью `Handles` предложение — по умолчанию способ объявления обработчика событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0f9d-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="c0f9d-110">Этот способ записи обработчиков событий в конструкторах при программировании в интегрированную среду разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="c0f9d-111">`AddHandler` Инструкция подходит для динамического создания событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="c0f9d-112">При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает процедуру обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-112">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="c0f9d-113">Любой код, который имеет доступ к событию может привести к его выполнения, выполнив [оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="c0f9d-114">Можно связать несколько обработчиков событий с одним событием.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="c0f9d-115">В некоторых случаях можно отменить привязку обработчика события.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="c0f9d-116">Дополнительные сведения см. в разделе [события](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="c0f9d-117">Для вызова обработчика событий с помощью WithEvents и метки</span><span class="sxs-lookup"><span data-stu-id="c0f9d-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="c0f9d-118">Убедитесь, что событие объявляется с [оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="c0f9d-119">Объявите переменную объекта на уровне модуля или класса, уровня, с помощью [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="c0f9d-120">`As` Предложение для этой переменной необходимо указать класс, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="c0f9d-121">В объявлении обработки событий `Sub` процедуры добавления [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение, определяющее `WithEvents` переменной и имя события.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="c0f9d-122">При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-122">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="c0f9d-123">В коде можно использовать `RaiseEvent` инструкцию, чтобы создавать событие.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="c0f9d-124">В следующем примере определяется событие и `WithEvents` переменную, которая ссылается на класс, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="c0f9d-125">Обработка событий `Sub` процедуры используется `Handles` предложение для указания класса и события, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     <span data-ttu-id="c0f9d-126">[!code-vb[VbVbcnProcedures&#4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0f9d-126">[!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span></span>  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="c0f9d-127">Для вызова обработчика событий с помощью AddHandler</span><span class="sxs-lookup"><span data-stu-id="c0f9d-127">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="c0f9d-128">Убедитесь, что событие объявляется с `Event` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-128">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="c0f9d-129">Выполнение [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для динамического связывания обработки события `Sub` процедуры с событием.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-129">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="c0f9d-130">При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-130">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="c0f9d-131">В коде можно использовать `RaiseEvent` инструкцию, чтобы создавать событие.</span><span class="sxs-lookup"><span data-stu-id="c0f9d-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="c0f9d-132">В следующем примере определяется `Sub` процедура для обработки <xref:System.Windows.Forms.Form.Closing>события формы.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="c0f9d-132">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="c0f9d-133">Затем он использует [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для связывания `catchClose` процедуру как обработчик событий <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="c0f9d-133">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     <span data-ttu-id="c0f9d-134">[!code-vb[VbVbcnProcedures&#5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0f9d-134">[!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span></span>  
  
     <span data-ttu-id="c0f9d-135">Обработчик событий из события можно отменить привязку, выполнив [оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c0f9d-135">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f9d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c0f9d-136">See Also</span></span>  
 <span data-ttu-id="c0f9d-137">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9d-137">[Procedures](./index.md) </span></span>  
<span data-ttu-id="c0f9d-138"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9d-138"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="c0f9d-139"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9d-139"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="c0f9d-140"> [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9d-140"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="c0f9d-141"> [Практическое руководство: создание процедуры](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c0f9d-141"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="c0f9d-142"> [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="c0f9d-142"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
