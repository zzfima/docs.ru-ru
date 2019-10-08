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
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004540"
---
# <a name="addhandler-statement"></a><span data-ttu-id="b905b-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="b905b-102">AddHandler Statement</span></span>
<span data-ttu-id="b905b-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b905b-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b905b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b905b-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b905b-105">Части</span><span class="sxs-lookup"><span data-stu-id="b905b-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="b905b-106">event</span><span class="sxs-lookup"><span data-stu-id="b905b-106">event</span></span>|<span data-ttu-id="b905b-107">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="b905b-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="b905b-108">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="b905b-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="b905b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b905b-109">Remarks</span></span>  
 <span data-ttu-id="b905b-110">Операторы `AddHandler` и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="b905b-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="b905b-111">Сигнатура процедуры `eventhandler` должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="b905b-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="b905b-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="b905b-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="b905b-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b905b-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="b905b-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="b905b-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="b905b-115">Дополнительные сведения см. в разделе [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b905b-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b905b-116">Для пользовательских событий оператор `AddHandler` вызывает метод доступа `AddHandler` события.</span><span class="sxs-lookup"><span data-stu-id="b905b-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="b905b-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b905b-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b905b-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b905b-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b905b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b905b-119">See also</span></span>

- [<span data-ttu-id="b905b-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="b905b-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="b905b-121">Handles</span><span class="sxs-lookup"><span data-stu-id="b905b-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="b905b-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="b905b-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="b905b-123">События</span><span class="sxs-lookup"><span data-stu-id="b905b-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
