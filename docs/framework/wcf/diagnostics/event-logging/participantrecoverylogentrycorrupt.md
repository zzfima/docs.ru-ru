---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 5a2f23a3335f938b26a378010e083525803ffb87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33470495"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="c08d0-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="c08d0-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="c08d0-103">Идентификатор: 138</span><span class="sxs-lookup"><span data-stu-id="c08d0-103">Id: 138</span></span>  
  
 <span data-ttu-id="c08d0-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="c08d0-104">Severity: Error</span></span>  
  
 <span data-ttu-id="c08d0-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="c08d0-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="c08d0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c08d0-106">Description</span></span>  
 <span data-ttu-id="c08d0-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="c08d0-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="c08d0-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="c08d0-108">Data loss may result from this error.</span></span> <span data-ttu-id="c08d0-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="c08d0-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08d0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c08d0-110">See Also</span></span>  
 [<span data-ttu-id="c08d0-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="c08d0-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="c08d0-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="c08d0-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
