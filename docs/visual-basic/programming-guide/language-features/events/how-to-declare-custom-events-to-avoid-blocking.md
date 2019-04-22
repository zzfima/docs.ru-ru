---
title: Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821261"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="91281-102">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91281-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="91281-103">Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие.</span><span class="sxs-lookup"><span data-stu-id="91281-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="91281-104">Пользовательские события позволяют событие асинхронный вызов соответствующих обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="91281-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="91281-105">По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, который последовательно объединяет все обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="91281-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="91281-106">Это означает, что если один обработчик занимает много времени для завершения, он блокирует другие обработчики до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="91281-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="91281-107">(Хороший обработчик событий не должны выполнять длительных или потенциально блокирующих операций.)</span><span class="sxs-lookup"><span data-stu-id="91281-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="91281-108">Вместо реализации событий, предоставляемых Visual Basic по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="91281-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91281-109">Пример</span><span class="sxs-lookup"><span data-stu-id="91281-109">Example</span></span>  
 <span data-ttu-id="91281-110">В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событие <xref:System.Collections.ArrayList> хранятся в `EventHandlerList` поля.</span><span class="sxs-lookup"><span data-stu-id="91281-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="91281-111">Когда код вызывает `Click` событий, `RaiseEvent` все асинхронно с помощью делегатов обработчиков событий вызывает метод доступа <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="91281-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="91281-112">Этот метод вызывает каждый обработчик в рабочем потоке и немедленно возвращает, чтобы обработчики не блокируют друг друга.</span><span class="sxs-lookup"><span data-stu-id="91281-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="91281-113">См. также</span><span class="sxs-lookup"><span data-stu-id="91281-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="91281-114">События</span><span class="sxs-lookup"><span data-stu-id="91281-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="91281-115">Практическое руководство. Объявление пользовательских событий для экономии памяти</span><span class="sxs-lookup"><span data-stu-id="91281-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
