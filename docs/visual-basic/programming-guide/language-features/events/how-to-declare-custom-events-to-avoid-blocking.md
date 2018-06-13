---
title: Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646930"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="97eaa-102">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97eaa-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="97eaa-103">Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие.</span><span class="sxs-lookup"><span data-stu-id="97eaa-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="97eaa-104">Пользовательские события позволяют событий для асинхронного вызова соответствующих обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="97eaa-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="97eaa-105">По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, последовательно объединяющим все обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="97eaa-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="97eaa-106">Это означает, что если один обработчик занимает много времени, он блокирует другие обработчики до его завершения.</span><span class="sxs-lookup"><span data-stu-id="97eaa-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="97eaa-107">(Хороший обработчик событий никогда не будет выполнять длинные или потенциально блокирующие операции.)</span><span class="sxs-lookup"><span data-stu-id="97eaa-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="97eaa-108">Вместо использования реализации событий, которые предоставляет Visual Basic по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="97eaa-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97eaa-109">Пример</span><span class="sxs-lookup"><span data-stu-id="97eaa-109">Example</span></span>  
 <span data-ttu-id="97eaa-110">В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событий для <xref:System.Collections.ArrayList> хранятся в `EventHandlerList` поле.</span><span class="sxs-lookup"><span data-stu-id="97eaa-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="97eaa-111">Когда код вызывает `Click` событий, `RaiseEvent` все асинхронно с помощью делегатов обработчиков событий вызывает метод доступа <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="97eaa-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="97eaa-112">Этот метод вызывает каждый обработчик в рабочем потоке и немедленно возвращает, чтобы обработчики не может блокировать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="97eaa-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="97eaa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="97eaa-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="97eaa-114">События</span><span class="sxs-lookup"><span data-stu-id="97eaa-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="97eaa-115">Практическое руководство. Объявление пользовательских событий для экономии памяти</span><span class="sxs-lookup"><span data-stu-id="97eaa-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
