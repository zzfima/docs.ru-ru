---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 8533d53dc6a2d4510ffec2dcbf0e9bef15cde6ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999197"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="05c5d-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="05c5d-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="05c5d-103">ИД: 165</span><span class="sxs-lookup"><span data-stu-id="05c5d-103">Id: 165</span></span>  
  
 <span data-ttu-id="05c5d-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="05c5d-104">Severity: Error</span></span>  
  
 <span data-ttu-id="05c5d-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="05c5d-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="05c5d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05c5d-106">Description</span></span>  
 <span data-ttu-id="05c5d-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="05c5d-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="05c5d-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="05c5d-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="05c5d-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="05c5d-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c5d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="05c5d-110">See also</span></span>

- [<span data-ttu-id="05c5d-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="05c5d-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="05c5d-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="05c5d-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
