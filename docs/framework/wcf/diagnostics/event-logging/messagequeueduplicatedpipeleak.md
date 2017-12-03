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
ms.openlocfilehash: bd1b006d735c5b8bc140efe095adeb74aef387db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="messagequeueduplicatedpipeleak"></a><span data-ttu-id="a08c9-102">MessageQueueDuplicatedPipeLeak</span><span class="sxs-lookup"><span data-stu-id="a08c9-102">MessageQueueDuplicatedPipeLeak</span></span>
<span data-ttu-id="a08c9-103">Идентификатор: 166</span><span class="sxs-lookup"><span data-stu-id="a08c9-103">Id: 166</span></span>  
  
 <span data-ttu-id="a08c9-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="a08c9-104">Severity: Error</span></span>  
  
 <span data-ttu-id="a08c9-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="a08c9-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="a08c9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a08c9-106">Description</span></span>  
 <span data-ttu-id="a08c9-107">Это событие указывает, что произошла ошибка при диспетчеризации дублированного именованного канала.</span><span class="sxs-lookup"><span data-stu-id="a08c9-107">This event indicates that an error occurred while dispatching a duplicated named pipe.</span></span> <span data-ttu-id="a08c9-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="a08c9-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="a08c9-109">В событии указаны источник, исключение, имя процесса и идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="a08c9-109">The event lists the source, exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08c9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a08c9-110">See Also</span></span>  
 [<span data-ttu-id="a08c9-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="a08c9-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="a08c9-112">Общие справочные сведения события</span><span class="sxs-lookup"><span data-stu-id="a08c9-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
