---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 6856ac8b70ec30b795585b4ab2d2e76d1b61796c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684506"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="6f9d8-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="6f9d8-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="6f9d8-103">ИД: 138</span><span class="sxs-lookup"><span data-stu-id="6f9d8-103">Id: 138</span></span>  
  
 <span data-ttu-id="6f9d8-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="6f9d8-104">Severity: Error</span></span>  
  
 <span data-ttu-id="6f9d8-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="6f9d8-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f9d8-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="6f9d8-106">Description</span></span>  
 <span data-ttu-id="6f9d8-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="6f9d8-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="6f9d8-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="6f9d8-108">Data loss may result from this error.</span></span> <span data-ttu-id="6f9d8-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="6f9d8-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9d8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6f9d8-110">See also</span></span>
- [<span data-ttu-id="6f9d8-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="6f9d8-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="6f9d8-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="6f9d8-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
