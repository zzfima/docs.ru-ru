---
title: MessageQueueDuplicatedSocketLeak
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 374a5900839dc1f0151743126de16369fa6bf7ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="1ee70-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="1ee70-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="1ee70-103">Идентификатор: 165</span><span class="sxs-lookup"><span data-stu-id="1ee70-103">Id: 165</span></span>  
  
 <span data-ttu-id="1ee70-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="1ee70-104">Severity: Error</span></span>  
  
 <span data-ttu-id="1ee70-105">Категория: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="1ee70-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="1ee70-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1ee70-106">Description</span></span>  
 <span data-ttu-id="1ee70-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="1ee70-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="1ee70-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="1ee70-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="1ee70-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="1ee70-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee70-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1ee70-110">See Also</span></span>  
 [<span data-ttu-id="1ee70-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="1ee70-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="1ee70-112">Общие справочные сведения события</span><span class="sxs-lookup"><span data-stu-id="1ee70-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
