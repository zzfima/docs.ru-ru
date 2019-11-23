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
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350191"
---
# <a name="addhandler-statement"></a><span data-ttu-id="00454-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="00454-102">AddHandler Statement</span></span>
<span data-ttu-id="00454-103">Associates an event with an event handler at run time.</span><span class="sxs-lookup"><span data-stu-id="00454-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00454-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00454-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="00454-105">Части</span><span class="sxs-lookup"><span data-stu-id="00454-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="00454-106">событие</span><span class="sxs-lookup"><span data-stu-id="00454-106">event</span></span>|<span data-ttu-id="00454-107">The name of the event to handle.</span><span class="sxs-lookup"><span data-stu-id="00454-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="00454-108">The name of a procedure that handles the event.</span><span class="sxs-lookup"><span data-stu-id="00454-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="00454-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="00454-109">Remarks</span></span>  
 <span data-ttu-id="00454-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span><span class="sxs-lookup"><span data-stu-id="00454-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="00454-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span><span class="sxs-lookup"><span data-stu-id="00454-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="00454-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="00454-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="00454-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="00454-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="00454-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="00454-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="00454-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="00454-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00454-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span><span class="sxs-lookup"><span data-stu-id="00454-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="00454-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="00454-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00454-118">Пример</span><span class="sxs-lookup"><span data-stu-id="00454-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="00454-119">См. также</span><span class="sxs-lookup"><span data-stu-id="00454-119">See also</span></span>

- [<span data-ttu-id="00454-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="00454-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="00454-121">Handles</span><span class="sxs-lookup"><span data-stu-id="00454-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="00454-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="00454-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="00454-123">События</span><span class="sxs-lookup"><span data-stu-id="00454-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
