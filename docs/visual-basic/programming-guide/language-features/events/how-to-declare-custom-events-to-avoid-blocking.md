---
title: "Практическое руководство: объявление пользовательских событий для предотвращения блокировки (Visual Basic) | Документы Microsoft"
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
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
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
ms.openlocfilehash: 52181d1c307e4e312f4511719e540fd6d5bfcfa8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="127bf-102">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="127bf-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="127bf-103">Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие.</span><span class="sxs-lookup"><span data-stu-id="127bf-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="127bf-104">Пользовательские события позволяют событию асинхронный вызов обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="127bf-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="127bf-105">По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, последовательно объединяющим все обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="127bf-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="127bf-106">Это означает, что если одного обработчика занимает много времени, он блокирует другие обработчики до завершения.</span><span class="sxs-lookup"><span data-stu-id="127bf-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="127bf-107">(Хороший обработчик событий никогда не будет выполнять длинные или потенциально блокирующие операции.)</span><span class="sxs-lookup"><span data-stu-id="127bf-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="127bf-108">Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="127bf-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="127bf-109">Пример</span><span class="sxs-lookup"><span data-stu-id="127bf-109">Example</span></span>  
 <span data-ttu-id="127bf-110">В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событие <xref:System.Collections.ArrayList>хранятся в `EventHandlerList` поле.</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="127bf-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="127bf-111">Когда код вызывает `Click` событий, `RaiseEvent` доступа вызывает все асинхронно с помощью делегатов обработчиков событий <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>метод.</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="127bf-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="127bf-112">Этот метод вызывает каждый обработчик на рабочем потоке и немедленно возвращает, чтобы обработчики не могли блокировать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="127bf-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 <span data-ttu-id="127bf-113">[!code-vb[VbVbalrEvents&#27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="127bf-113">[!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127bf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="127bf-114">See Also</span></span>  
 <span data-ttu-id="127bf-115"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="127bf-115"><xref:System.Collections.ArrayList></span></span>   
 <span data-ttu-id="127bf-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="127bf-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span></span>   
<span data-ttu-id="127bf-117"> [События](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="127bf-117"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="127bf-118"> [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span><span class="sxs-lookup"><span data-stu-id="127bf-118"> [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span></span>
