---
title: ParticipantRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fe80e3785a579d429acb9026748787dd9a27379
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="d1bef-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="d1bef-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="d1bef-103">Идентификатор: 138</span><span class="sxs-lookup"><span data-stu-id="d1bef-103">Id: 138</span></span>  
  
 <span data-ttu-id="d1bef-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="d1bef-104">Severity: Error</span></span>  
  
 <span data-ttu-id="d1bef-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="d1bef-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="d1bef-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="d1bef-106">Description</span></span>  
 <span data-ttu-id="d1bef-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="d1bef-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="d1bef-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="d1bef-108">Data loss may result from this error.</span></span> <span data-ttu-id="d1bef-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="d1bef-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1bef-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d1bef-110">See Also</span></span>  
 [<span data-ttu-id="d1bef-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="d1bef-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="d1bef-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="d1bef-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
