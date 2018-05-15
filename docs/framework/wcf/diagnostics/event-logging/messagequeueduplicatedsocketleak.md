---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: a646fbe52c40e14658f2403580870ada6de2d400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="d4074-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="d4074-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="d4074-103">Идентификатор: 165</span><span class="sxs-lookup"><span data-stu-id="d4074-103">Id: 165</span></span>  
  
 <span data-ttu-id="d4074-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="d4074-104">Severity: Error</span></span>  
  
 <span data-ttu-id="d4074-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="d4074-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="d4074-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d4074-106">Description</span></span>  
 <span data-ttu-id="d4074-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="d4074-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="d4074-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="d4074-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="d4074-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="d4074-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4074-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d4074-110">See Also</span></span>  
 [<span data-ttu-id="d4074-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="d4074-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="d4074-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="d4074-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
