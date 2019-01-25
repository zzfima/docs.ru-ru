---
title: Как выполнить Объявление пользовательских событий для экономии памяти (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: bf22c2029671588ab0ebaefd2554fcb2a5a1131c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719525"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="d74ce-102">Как выполнить Объявление пользовательских событий для экономии памяти (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d74ce-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="d74ce-103">Существует несколько случаев, когда важно, что приложение усложнять использования памяти.</span><span class="sxs-lookup"><span data-stu-id="d74ce-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="d74ce-104">Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="d74ce-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="d74ce-105">По умолчанию когда класс объявляет событие, компилятор выделяет память для поля для хранения сведений о событии.</span><span class="sxs-lookup"><span data-stu-id="d74ce-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="d74ce-106">Если у класса имеется много неиспользуемых событий, они занимают много памяти.</span><span class="sxs-lookup"><span data-stu-id="d74ce-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="d74ce-107">Вместо того чтобы использовать реализацию по умолчанию события, предоставляемые Visual Basic, можно использовать пользовательские события для более тщательного управления памятью.</span><span class="sxs-lookup"><span data-stu-id="d74ce-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d74ce-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d74ce-108">Example</span></span>  
 <span data-ttu-id="d74ce-109">В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList> классов, хранящихся в `Events` поле для хранения сведений о событиях использования.</span><span class="sxs-lookup"><span data-stu-id="d74ce-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="d74ce-110"><xref:System.ComponentModel.EventHandlerList> — Класс оптимизированного списка предназначены для хранения делегатов.</span><span class="sxs-lookup"><span data-stu-id="d74ce-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="d74ce-111">Все события класса используют `Events` поля для отслеживания какие методы являются обработчиками каждого события.</span><span class="sxs-lookup"><span data-stu-id="d74ce-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d74ce-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d74ce-112">See also</span></span>
- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="d74ce-113">События</span><span class="sxs-lookup"><span data-stu-id="d74ce-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="d74ce-114">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки</span><span class="sxs-lookup"><span data-stu-id="d74ce-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
