---
title: "Практическое руководство: объявление пользовательских событий для экономии памяти (Visual Basic) | Документы Microsoft"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
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
ms.openlocfilehash: 130cbda875d6a56f826aefea341d233ea4b3731d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="81450-102">Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81450-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="81450-103">Существует несколько случаев, когда важно, что приложение небольшое использование памяти.</span><span class="sxs-lookup"><span data-stu-id="81450-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="81450-104">Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="81450-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="81450-105">По умолчанию когда класс объявляет событие, компилятор выделяет память под поле для хранения сведений о событии.</span><span class="sxs-lookup"><span data-stu-id="81450-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="81450-106">Если класс имеет много неиспользуемых событий, они занимают много памяти.</span><span class="sxs-lookup"><span data-stu-id="81450-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="81450-107">Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.</span><span class="sxs-lookup"><span data-stu-id="81450-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81450-108">Пример</span><span class="sxs-lookup"><span data-stu-id="81450-108">Example</span></span>  
 <span data-ttu-id="81450-109">В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList>классов, хранящихся в `Events` поле для хранения информации о событиях, используется.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="81450-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="81450-110"><xref:System.ComponentModel.EventHandlerList>— Это класс оптимизированного список, созданным для хранения делегатов.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="81450-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="81450-111">Все события класса используют `Events` поля для отслеживания того, какие методы являются обработчиками каждого события.</span><span class="sxs-lookup"><span data-stu-id="81450-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 <span data-ttu-id="81450-112">[!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="81450-112">[!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81450-113">См. также</span><span class="sxs-lookup"><span data-stu-id="81450-113">See Also</span></span>  
 <span data-ttu-id="81450-114"><xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="81450-114"><xref:System.ComponentModel.EventHandlerList></span></span>   
<span data-ttu-id="81450-115"> [События](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="81450-115"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="81450-116"> [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="81450-116"> [How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span></span>
