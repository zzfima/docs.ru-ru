---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 0dc74b784d8a9ed3ab27bb4b8d3de34143f6ce07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639488"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="3c854-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="3c854-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="3c854-103">ИД: 139</span><span class="sxs-lookup"><span data-stu-id="3c854-103">Id: 139</span></span>  
  
 <span data-ttu-id="3c854-104">Уровень серьезности: Error</span><span class="sxs-lookup"><span data-stu-id="3c854-104">Severity: Error</span></span>  
  
 <span data-ttu-id="3c854-105">Категория: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="3c854-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c854-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3c854-106">Description</span></span>  
 <span data-ttu-id="3c854-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="3c854-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="3c854-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="3c854-108">Data loss may result from this error.</span></span> <span data-ttu-id="3c854-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="3c854-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c854-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3c854-110">See also</span></span>
- [<span data-ttu-id="3c854-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="3c854-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="3c854-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="3c854-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
