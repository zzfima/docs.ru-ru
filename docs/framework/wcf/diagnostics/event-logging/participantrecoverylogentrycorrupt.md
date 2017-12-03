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
ms.openlocfilehash: cd9dce1745c1a110ac2cbadd497c02c1323a2338
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="5051f-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="5051f-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="5051f-103">Идентификатор: 138</span><span class="sxs-lookup"><span data-stu-id="5051f-103">Id: 138</span></span>  
  
 <span data-ttu-id="5051f-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="5051f-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5051f-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="5051f-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="5051f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5051f-106">Description</span></span>  
 <span data-ttu-id="5051f-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="5051f-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="5051f-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="5051f-108">Data loss may result from this error.</span></span> <span data-ttu-id="5051f-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="5051f-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5051f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5051f-110">See Also</span></span>  
 [<span data-ttu-id="5051f-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="5051f-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="5051f-112">Общие справочные сведения события</span><span class="sxs-lookup"><span data-stu-id="5051f-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
