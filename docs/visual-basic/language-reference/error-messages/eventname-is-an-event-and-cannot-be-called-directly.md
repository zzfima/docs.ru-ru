---
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803328"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="9ad7e-102">"\<имя_события >" является событием и не может вызываться напрямую</span><span class="sxs-lookup"><span data-stu-id="9ad7e-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="9ad7e-103">"<`eventname`>" является событием и поэтому не может вызываться напрямую.</span><span class="sxs-lookup"><span data-stu-id="9ad7e-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="9ad7e-104">Используйте `RaiseEvent` инструкцию, чтобы вызвать событие.</span><span class="sxs-lookup"><span data-stu-id="9ad7e-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="9ad7e-105">При вызове процедуры указывается событие для имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="9ad7e-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="9ad7e-106">Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.</span><span class="sxs-lookup"><span data-stu-id="9ad7e-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="9ad7e-107">**Идентификатор ошибки:** BC32022</span><span class="sxs-lookup"><span data-stu-id="9ad7e-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ad7e-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9ad7e-108">To correct this error</span></span>  
  
1. <span data-ttu-id="9ad7e-109">Используйте `RaiseEvent` инструкцию, чтобы оповестить о событии и вызвать одну или несколько процедур, которые его обрабатывают.</span><span class="sxs-lookup"><span data-stu-id="9ad7e-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad7e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9ad7e-110">See also</span></span>

- [<span data-ttu-id="9ad7e-111">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="9ad7e-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
