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
ms.openlocfilehash: 6ed6f3d4fd77d714ab554d641c0c0fc4f403bbf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715107"
---
# <a name="addhandler-statement"></a><span data-ttu-id="ade94-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="ade94-102">AddHandler Statement</span></span>
<span data-ttu-id="ade94-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ade94-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ade94-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="ade94-105">Части</span><span class="sxs-lookup"><span data-stu-id="ade94-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="ade94-106">событие</span><span class="sxs-lookup"><span data-stu-id="ade94-106">event</span></span>|<span data-ttu-id="ade94-107">Имя события для обработки.</span><span class="sxs-lookup"><span data-stu-id="ade94-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="ade94-108">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="ade94-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="ade94-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ade94-109">Remarks</span></span>  
 <span data-ttu-id="ade94-110">`AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий в любое время, во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="ade94-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="ade94-111">Подпись `eventhandler` процедура должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="ade94-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="ade94-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="ade94-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="ade94-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ade94-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="ade94-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="ade94-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="ade94-115">Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ade94-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ade94-116">Для пользовательских событий `AddHandler` инструкция вызывает события `AddHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="ade94-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="ade94-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ade94-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade94-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ade94-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ade94-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ade94-119">See also</span></span>
- [<span data-ttu-id="ade94-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="ade94-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="ade94-121">Handles</span><span class="sxs-lookup"><span data-stu-id="ade94-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="ade94-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="ade94-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="ade94-123">События</span><span class="sxs-lookup"><span data-stu-id="ade94-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
