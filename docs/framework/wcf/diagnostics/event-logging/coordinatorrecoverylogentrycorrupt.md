---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121632"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="78412-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="78412-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="78412-103">ИД: 139</span><span class="sxs-lookup"><span data-stu-id="78412-103">Id: 139</span></span>  
  
 <span data-ttu-id="78412-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="78412-104">Severity: Error</span></span>  
  
 <span data-ttu-id="78412-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="78412-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="78412-106">Описание</span><span class="sxs-lookup"><span data-stu-id="78412-106">Description</span></span>  
 <span data-ttu-id="78412-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="78412-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="78412-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="78412-108">Data loss may result from this error.</span></span> <span data-ttu-id="78412-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="78412-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78412-110">См. также</span><span class="sxs-lookup"><span data-stu-id="78412-110">See also</span></span>

- [<span data-ttu-id="78412-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="78412-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="78412-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="78412-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
