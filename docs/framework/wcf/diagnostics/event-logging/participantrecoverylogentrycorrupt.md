---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 61ab172a3924e3c0ca00ffc25ef96446e33c5142
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796231"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="acb5d-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="acb5d-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="acb5d-103">ИД: 138</span><span class="sxs-lookup"><span data-stu-id="acb5d-103">Id: 138</span></span>  
  
 <span data-ttu-id="acb5d-104">"Уровень серьезности" — Ошибка</span><span class="sxs-lookup"><span data-stu-id="acb5d-104">Severity: Error</span></span>  
  
 <span data-ttu-id="acb5d-105">Категори трансактионбридже</span><span class="sxs-lookup"><span data-stu-id="acb5d-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="acb5d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="acb5d-106">Description</span></span>  
 <span data-ttu-id="acb5d-107">Это событие показывает, что запись в журнале восстановления участника была повреждена и ее не удалось десериализовать.</span><span class="sxs-lookup"><span data-stu-id="acb5d-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="acb5d-108">Эта ошибка может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="acb5d-108">Data loss may result from this error.</span></span> <span data-ttu-id="acb5d-109">В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="acb5d-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb5d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="acb5d-110">See also</span></span>

- [<span data-ttu-id="acb5d-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="acb5d-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="acb5d-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="acb5d-112">Events General Reference</span></span>](events-general-reference.md)
