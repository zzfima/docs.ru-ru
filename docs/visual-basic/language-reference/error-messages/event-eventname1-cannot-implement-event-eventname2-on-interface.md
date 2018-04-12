---
title: Событие &#39; &lt;имя_события1&gt;&#39; не может реализовать событие &#39;&lt; имя_события2&gt;&#39; на интерфейс &#39;&lt; интерфейс&gt;&#39; поскольку их делегируемые типы &#39;&lt; delegate1&gt;&#39; и &#39;&lt; delegate2&gt;&#39; не совпадают
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="cb827-102">Событие &#39; &lt;имя_события1&gt;&#39; не может реализовать событие &#39;&lt; имя_события2&gt;&#39; на интерфейс &#39;&lt; интерфейс&gt;&#39; поскольку их делегируемые типы &#39;&lt; delegate1&gt;&#39; и &#39;&lt; delegate2&gt;&#39; не совпадают</span><span class="sxs-lookup"><span data-stu-id="cb827-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="cb827-103">не удается реализовать событие, поскольку тип делегата события не соответствует типу делегата события интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb827-103"> cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="cb827-104">Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события.</span><span class="sxs-lookup"><span data-stu-id="cb827-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="cb827-105">Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="cb827-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="cb827-106">**Идентификатор ошибки:** BC31423</span><span class="sxs-lookup"><span data-stu-id="cb827-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb827-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cb827-107">To correct this error</span></span>  
  
-   <span data-ttu-id="cb827-108">Реализуйте события по отдельности.</span><span class="sxs-lookup"><span data-stu-id="cb827-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="cb827-109">—или—</span><span class="sxs-lookup"><span data-stu-id="cb827-109">—or—</span></span>  
  
-   <span data-ttu-id="cb827-110">Определите события в интерфейсе, используя `As` синтаксис и указать тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="cb827-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb827-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cb827-111">See Also</span></span>  
 [<span data-ttu-id="cb827-112">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="cb827-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="cb827-113">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="cb827-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="cb827-114">События</span><span class="sxs-lookup"><span data-stu-id="cb827-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
