---
title: Оператор AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: a9913cd682e52562422ba140e27187d37c592684
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928942"
---
# <a name="addhandler-statement"></a><span data-ttu-id="a6c2e-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="a6c2e-102">AddHandler Statement</span></span>
<span data-ttu-id="a6c2e-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6c2e-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a6c2e-105">Части</span><span class="sxs-lookup"><span data-stu-id="a6c2e-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="a6c2e-106">event</span><span class="sxs-lookup"><span data-stu-id="a6c2e-106">event</span></span>|<span data-ttu-id="a6c2e-107">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="a6c2e-108">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a6c2e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6c2e-109">Remarks</span></span>  
 <span data-ttu-id="a6c2e-110">Инструкции `AddHandler` и`RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a6c2e-111">Сигнатура `eventhandler` процедуры должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a6c2e-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a6c2e-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a6c2e-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a6c2e-115">Дополнительные сведения см. в разделе [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a6c2e-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6c2e-116">Для пользовательских событий `AddHandler` оператор вызывает `AddHandler` метод доступа события.</span><span class="sxs-lookup"><span data-stu-id="a6c2e-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a6c2e-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6c2e-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c2e-118">Пример</span><span class="sxs-lookup"><span data-stu-id="a6c2e-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a6c2e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a6c2e-119">See also</span></span>

- [<span data-ttu-id="a6c2e-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="a6c2e-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="a6c2e-121">Handles</span><span class="sxs-lookup"><span data-stu-id="a6c2e-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="a6c2e-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="a6c2e-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a6c2e-123">События</span><span class="sxs-lookup"><span data-stu-id="a6c2e-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
