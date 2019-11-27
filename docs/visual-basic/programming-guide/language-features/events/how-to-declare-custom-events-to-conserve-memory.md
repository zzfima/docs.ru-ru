---
title: Практическое руководство. Объявление пользовательских событий для экономии памяти
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345127"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="3447a-102">Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3447a-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="3447a-103">Существует несколько ситуаций, когда важно, чтобы приложение продолжало использовать память в низком объеме.</span><span class="sxs-lookup"><span data-stu-id="3447a-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="3447a-104">Пользовательские события позволяют приложению использовать память только для обрабатываемых событий.</span><span class="sxs-lookup"><span data-stu-id="3447a-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="3447a-105">По умолчанию, когда класс объявляет событие, компилятор выделяет память для поля, в котором хранятся сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="3447a-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="3447a-106">Если класс содержит много неиспользуемых событий, они не занимают память.</span><span class="sxs-lookup"><span data-stu-id="3447a-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="3447a-107">Вместо использования реализации по умолчанию событий, предоставляемых Visual Basic, можно использовать пользовательские события для более тщательного управления использованием памяти.</span><span class="sxs-lookup"><span data-stu-id="3447a-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3447a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3447a-108">Example</span></span>  
 <span data-ttu-id="3447a-109">В этом примере класс использует один экземпляр класса <xref:System.ComponentModel.EventHandlerList>, хранящийся в поле `Events`, для хранения сведений об используемых событиях.</span><span class="sxs-lookup"><span data-stu-id="3447a-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="3447a-110">Класс <xref:System.ComponentModel.EventHandlerList> является оптимизированным классом списка, предназначенным для хранения делегатов.</span><span class="sxs-lookup"><span data-stu-id="3447a-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="3447a-111">Все события в классе используют поле `Events` для наблюдения за тем, какие методы обрабатывают каждое событие.</span><span class="sxs-lookup"><span data-stu-id="3447a-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="3447a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3447a-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="3447a-113">События</span><span class="sxs-lookup"><span data-stu-id="3447a-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="3447a-114">Практическое руководство. Объявление пользовательских событий для предотвращения блокировки</span><span class="sxs-lookup"><span data-stu-id="3447a-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
