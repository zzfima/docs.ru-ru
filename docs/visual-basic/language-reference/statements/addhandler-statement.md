---
title: Оператор AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603656"
---
# <a name="addhandler-statement"></a><span data-ttu-id="18258-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="18258-102">AddHandler Statement</span></span>
<span data-ttu-id="18258-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="18258-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18258-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18258-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="18258-105">Части</span><span class="sxs-lookup"><span data-stu-id="18258-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="18258-106">Имя события для обработки.</span><span class="sxs-lookup"><span data-stu-id="18258-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="18258-107">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="18258-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18258-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="18258-108">Remarks</span></span>  
 <span data-ttu-id="18258-109">`AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="18258-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="18258-110">Подпись `eventhandler` процедуры должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="18258-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="18258-111">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="18258-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="18258-112">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="18258-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="18258-113">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="18258-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="18258-114">Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18258-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18258-115">Для пользовательских событий `AddHandler` инструкция вызывает событие `AddHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="18258-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="18258-116">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="18258-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18258-117">Пример</span><span class="sxs-lookup"><span data-stu-id="18258-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="18258-118">См. также</span><span class="sxs-lookup"><span data-stu-id="18258-118">See Also</span></span>  
 [<span data-ttu-id="18258-119">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="18258-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="18258-120">Handles</span><span class="sxs-lookup"><span data-stu-id="18258-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="18258-121">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="18258-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="18258-122">События</span><span class="sxs-lookup"><span data-stu-id="18258-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
