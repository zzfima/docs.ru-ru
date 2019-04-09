---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121632"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="f6df9-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="f6df9-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="f6df9-103">ИД: 139</span><span class="sxs-lookup"><span data-stu-id="f6df9-103">Id: 139</span></span>  
  
 <span data-ttu-id="f6df9-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="f6df9-104">Severity: Error</span></span>  
  
 <span data-ttu-id="f6df9-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="f6df9-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="f6df9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f6df9-106">Description</span></span>  
 <span data-ttu-id="f6df9-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="f6df9-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="f6df9-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="f6df9-108">Data loss may result from this error.</span></span> <span data-ttu-id="f6df9-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="f6df9-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6df9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f6df9-110">See also</span></span>

- [<span data-ttu-id="f6df9-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="f6df9-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="f6df9-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="f6df9-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
