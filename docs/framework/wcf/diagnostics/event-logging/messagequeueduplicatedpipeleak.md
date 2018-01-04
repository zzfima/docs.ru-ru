---
title: MessageQueueDuplicatedPipeLeak
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743db7f1-32cc-4a3b-8d1a-5d1cf25e439c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbdc6c4a45c944b23a56778b26e3c29fac6da8bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="messagequeueduplicatedpipeleak"></a><span data-ttu-id="5c524-102">MessageQueueDuplicatedPipeLeak</span><span class="sxs-lookup"><span data-stu-id="5c524-102">MessageQueueDuplicatedPipeLeak</span></span>
<span data-ttu-id="5c524-103">Идентификатор: 166</span><span class="sxs-lookup"><span data-stu-id="5c524-103">Id: 166</span></span>  
  
 <span data-ttu-id="5c524-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="5c524-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5c524-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="5c524-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="5c524-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="5c524-106">Description</span></span>  
 <span data-ttu-id="5c524-107">Это событие указывает, что произошла ошибка при диспетчеризации дублированного именованного канала.</span><span class="sxs-lookup"><span data-stu-id="5c524-107">This event indicates that an error occurred while dispatching a duplicated named pipe.</span></span> <span data-ttu-id="5c524-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="5c524-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="5c524-109">В событии указаны источник, исключение, имя процесса и идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="5c524-109">The event lists the source, exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c524-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5c524-110">See Also</span></span>  
 [<span data-ttu-id="5c524-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="5c524-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="5c524-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="5c524-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
