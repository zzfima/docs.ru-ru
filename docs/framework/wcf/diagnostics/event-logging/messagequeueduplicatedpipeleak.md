---
title: MessageQueueDuplicatedPipeLeak
ms.date: 03/30/2017
ms.assetid: 743db7f1-32cc-4a3b-8d1a-5d1cf25e439c
ms.openlocfilehash: f965b25f2df261f650216f279af512d8452f76c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471078"
---
# <a name="messagequeueduplicatedpipeleak"></a><span data-ttu-id="e4ec6-102">MessageQueueDuplicatedPipeLeak</span><span class="sxs-lookup"><span data-stu-id="e4ec6-102">MessageQueueDuplicatedPipeLeak</span></span>
<span data-ttu-id="e4ec6-103">Идентификатор: 166</span><span class="sxs-lookup"><span data-stu-id="e4ec6-103">Id: 166</span></span>  
  
 <span data-ttu-id="e4ec6-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="e4ec6-104">Severity: Error</span></span>  
  
 <span data-ttu-id="e4ec6-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="e4ec6-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="e4ec6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ec6-106">Description</span></span>  
 <span data-ttu-id="e4ec6-107">Это событие указывает, что произошла ошибка при диспетчеризации дублированного именованного канала.</span><span class="sxs-lookup"><span data-stu-id="e4ec6-107">This event indicates that an error occurred while dispatching a duplicated named pipe.</span></span> <span data-ttu-id="e4ec6-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="e4ec6-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="e4ec6-109">В событии указаны источник, исключение, имя процесса и идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="e4ec6-109">The event lists the source, exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ec6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e4ec6-110">See Also</span></span>  
 [<span data-ttu-id="e4ec6-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="e4ec6-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="e4ec6-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="e4ec6-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
