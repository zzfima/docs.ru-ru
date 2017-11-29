---
title: "Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="bcbc6-102">Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcbc6-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="bcbc6-103">Существует несколько случаев, когда важно, что приложение свести использование памяти.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="bcbc6-104">Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="bcbc6-105">По умолчанию когда класс объявляет событие, компилятор выделяет память для поля для хранения информации о событиях.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="bcbc6-106">Если класс имеет много неиспользуемых событий, они занимают много памяти.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="bcbc6-107">Вместо использования реализации событий, которые предоставляет Visual Basic по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcbc6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="bcbc6-108">Example</span></span>  
 <span data-ttu-id="bcbc6-109">В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList> класса, хранящиеся в `Events` поле для хранения сведений о событиях использования.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="bcbc6-110"><xref:System.ComponentModel.EventHandlerList> Класс — это класс оптимизированного списка, созданным для хранения делегатов.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="bcbc6-111">Все события класса используют `Events` поля для отслеживания какие методы являются обработчиками каждого события.</span><span class="sxs-lookup"><span data-stu-id="bcbc6-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bcbc6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bcbc6-112">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList>  
 [<span data-ttu-id="bcbc6-113">События</span><span class="sxs-lookup"><span data-stu-id="bcbc6-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="bcbc6-114">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки</span><span class="sxs-lookup"><span data-stu-id="bcbc6-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
