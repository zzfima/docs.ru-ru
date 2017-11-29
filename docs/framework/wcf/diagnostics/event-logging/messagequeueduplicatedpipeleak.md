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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edbfbd3d938bece688996e078d6663199d4cd563
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="messagequeueduplicatedpipeleak"></a><span data-ttu-id="e149a-102">MessageQueueDuplicatedPipeLeak</span><span class="sxs-lookup"><span data-stu-id="e149a-102">MessageQueueDuplicatedPipeLeak</span></span>
<span data-ttu-id="e149a-103">Идентификатор: 166</span><span class="sxs-lookup"><span data-stu-id="e149a-103">Id: 166</span></span>  
  
 <span data-ttu-id="e149a-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="e149a-104">Severity: Error</span></span>  
  
 <span data-ttu-id="e149a-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="e149a-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="e149a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e149a-106">Description</span></span>  
 <span data-ttu-id="e149a-107">Это событие указывает, что произошла ошибка при диспетчеризации дублированного именованного канала.</span><span class="sxs-lookup"><span data-stu-id="e149a-107">This event indicates that an error occurred while dispatching a duplicated named pipe.</span></span> <span data-ttu-id="e149a-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="e149a-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="e149a-109">В событии указаны источник, исключение, имя процесса и идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="e149a-109">The event lists the source, exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e149a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e149a-110">See Also</span></span>  
 [<span data-ttu-id="e149a-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="e149a-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="e149a-112">Общие справочные сведения события</span><span class="sxs-lookup"><span data-stu-id="e149a-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
