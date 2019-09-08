---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797982"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="1c25f-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="1c25f-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="1c25f-103">ИД: 139</span><span class="sxs-lookup"><span data-stu-id="1c25f-103">Id: 139</span></span>  
  
 <span data-ttu-id="1c25f-104">"Уровень серьезности" — Ошибка</span><span class="sxs-lookup"><span data-stu-id="1c25f-104">Severity: Error</span></span>  
  
 <span data-ttu-id="1c25f-105">Категори трансактионбридже</span><span class="sxs-lookup"><span data-stu-id="1c25f-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c25f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1c25f-106">Description</span></span>  
 <span data-ttu-id="1c25f-107">Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="1c25f-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="1c25f-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="1c25f-108">Data loss may result from this error.</span></span> <span data-ttu-id="1c25f-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="1c25f-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c25f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1c25f-110">See also</span></span>

- [<span data-ttu-id="1c25f-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="1c25f-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="1c25f-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="1c25f-112">Events General Reference</span></span>](events-general-reference.md)
