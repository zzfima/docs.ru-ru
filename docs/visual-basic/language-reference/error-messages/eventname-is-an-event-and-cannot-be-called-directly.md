---
title: '&#39;&lt;EventName&gt; &#39; является событием и не может вызываться напрямую'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587336"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="1801a-102">&#39;&lt;EventName&gt; &#39; является событием и не может вызываться напрямую</span><span class="sxs-lookup"><span data-stu-id="1801a-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="1801a-103">"<`eventname`>" является событием и поэтому не может вызываться напрямую.</span><span class="sxs-lookup"><span data-stu-id="1801a-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="1801a-104">Используйте `RaiseEvent` оператор для вызова события.</span><span class="sxs-lookup"><span data-stu-id="1801a-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="1801a-105">При вызове процедуры указывается событие имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="1801a-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="1801a-106">Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.</span><span class="sxs-lookup"><span data-stu-id="1801a-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="1801a-107">**Идентификатор ошибки:** BC32022</span><span class="sxs-lookup"><span data-stu-id="1801a-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1801a-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1801a-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="1801a-109">Используйте `RaiseEvent` инструкции для генерации события и вызова процедуры или процедуры его обработки.</span><span class="sxs-lookup"><span data-stu-id="1801a-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1801a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1801a-110">See Also</span></span>  
 [<span data-ttu-id="1801a-111">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="1801a-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
