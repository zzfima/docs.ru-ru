---
title: "Оператор AddHandler"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords: AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a><span data-ttu-id="2f673-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="2f673-102">AddHandler Statement</span></span>
<span data-ttu-id="2f673-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f673-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f673-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f673-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2f673-105">Части</span><span class="sxs-lookup"><span data-stu-id="2f673-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="2f673-106">Имя события для обработки.</span><span class="sxs-lookup"><span data-stu-id="2f673-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="2f673-107">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="2f673-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f673-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f673-108">Remarks</span></span>  
 <span data-ttu-id="2f673-109">`AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="2f673-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="2f673-110">Подпись `eventhandler` процедуры должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="2f673-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="2f673-111">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="2f673-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="2f673-112">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f673-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="2f673-113">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="2f673-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="2f673-114">Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2f673-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f673-115">Для пользовательских событий `AddHandler` инструкция вызывает событие `AddHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="2f673-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="2f673-116">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2f673-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f673-117">Пример</span><span class="sxs-lookup"><span data-stu-id="2f673-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2f673-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2f673-118">See Also</span></span>  
 [<span data-ttu-id="2f673-119">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="2f673-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="2f673-120">Handles</span><span class="sxs-lookup"><span data-stu-id="2f673-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="2f673-121">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="2f673-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="2f673-122">События</span><span class="sxs-lookup"><span data-stu-id="2f673-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
