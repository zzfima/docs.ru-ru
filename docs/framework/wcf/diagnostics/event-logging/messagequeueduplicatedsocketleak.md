---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 07712104a8dac002d46aee2ba6637bbbc9d850b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532353"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="4af6f-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="4af6f-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="4af6f-103">ИД: 165</span><span class="sxs-lookup"><span data-stu-id="4af6f-103">Id: 165</span></span>  
  
 <span data-ttu-id="4af6f-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="4af6f-104">Severity: Error</span></span>  
  
 <span data-ttu-id="4af6f-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="4af6f-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="4af6f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4af6f-106">Description</span></span>  
 <span data-ttu-id="4af6f-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="4af6f-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="4af6f-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="4af6f-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="4af6f-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="4af6f-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af6f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4af6f-110">See also</span></span>
- [<span data-ttu-id="4af6f-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="4af6f-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="4af6f-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="4af6f-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
