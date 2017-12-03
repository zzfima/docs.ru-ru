---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d57f0e7528c8df6ebf98aa712fe3efd728b421d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="7162f-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="7162f-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="7162f-103">Идентификатор: 139</span><span class="sxs-lookup"><span data-stu-id="7162f-103">Id: 139</span></span>  
  
 <span data-ttu-id="7162f-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="7162f-104">Severity: Error</span></span>  
  
 <span data-ttu-id="7162f-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="7162f-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="7162f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7162f-106">Description</span></span>  
 <span data-ttu-id="7162f-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="7162f-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="7162f-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="7162f-108">Data loss may result from this error.</span></span> <span data-ttu-id="7162f-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="7162f-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7162f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7162f-110">See Also</span></span>  
 [<span data-ttu-id="7162f-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="7162f-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="7162f-112">Общие справочные сведения события</span><span class="sxs-lookup"><span data-stu-id="7162f-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
