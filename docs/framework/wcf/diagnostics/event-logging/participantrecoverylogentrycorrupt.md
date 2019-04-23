---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 566517a122e17078156a61e0d3808ae06d0cf93c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075435"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="ffaec-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="ffaec-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="ffaec-103">ИД: 138</span><span class="sxs-lookup"><span data-stu-id="ffaec-103">Id: 138</span></span>  
  
 <span data-ttu-id="ffaec-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="ffaec-104">Severity: Error</span></span>  
  
 <span data-ttu-id="ffaec-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="ffaec-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="ffaec-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ffaec-106">Description</span></span>  
 <span data-ttu-id="ffaec-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="ffaec-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="ffaec-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="ffaec-108">Data loss may result from this error.</span></span> <span data-ttu-id="ffaec-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="ffaec-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffaec-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ffaec-110">See also</span></span>

- [<span data-ttu-id="ffaec-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="ffaec-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="ffaec-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="ffaec-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
