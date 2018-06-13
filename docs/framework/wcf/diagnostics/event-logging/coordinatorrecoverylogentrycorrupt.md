---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3f51d1269f5ca89f4f02257c8accef3423aa7eb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472687"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="5355d-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="5355d-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="5355d-103">Идентификатор: 139</span><span class="sxs-lookup"><span data-stu-id="5355d-103">Id: 139</span></span>  
  
 <span data-ttu-id="5355d-104">Важность: ошибка</span><span class="sxs-lookup"><span data-stu-id="5355d-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5355d-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="5355d-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="5355d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5355d-106">Description</span></span>  
 <span data-ttu-id="5355d-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="5355d-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="5355d-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="5355d-108">Data loss may result from this error.</span></span> <span data-ttu-id="5355d-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="5355d-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5355d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5355d-110">See Also</span></span>  
 [<span data-ttu-id="5355d-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="5355d-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="5355d-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="5355d-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
