---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 8533d53dc6a2d4510ffec2dcbf0e9bef15cde6ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206126"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="25ee0-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="25ee0-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="25ee0-103">ИД: 165</span><span class="sxs-lookup"><span data-stu-id="25ee0-103">Id: 165</span></span>  
  
 <span data-ttu-id="25ee0-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="25ee0-104">Severity: Error</span></span>  
  
 <span data-ttu-id="25ee0-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="25ee0-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="25ee0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="25ee0-106">Description</span></span>  
 <span data-ttu-id="25ee0-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="25ee0-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="25ee0-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="25ee0-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="25ee0-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="25ee0-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ee0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="25ee0-110">See also</span></span>

- [<span data-ttu-id="25ee0-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="25ee0-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="25ee0-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="25ee0-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
