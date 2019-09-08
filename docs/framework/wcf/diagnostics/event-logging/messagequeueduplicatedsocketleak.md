---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 00658372e59030ca00c257b6699c24b9e8dc90a4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797681"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="cbbda-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="cbbda-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="cbbda-103">ИД: 165</span><span class="sxs-lookup"><span data-stu-id="cbbda-103">Id: 165</span></span>  
  
 <span data-ttu-id="cbbda-104">"Уровень серьезности" — Ошибка</span><span class="sxs-lookup"><span data-stu-id="cbbda-104">Severity: Error</span></span>  
  
 <span data-ttu-id="cbbda-105">Категори SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="cbbda-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="cbbda-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cbbda-106">Description</span></span>  
 <span data-ttu-id="cbbda-107">Это событие показывает, что произошла ошибка при диспетчеризации дублированного сокета.</span><span class="sxs-lookup"><span data-stu-id="cbbda-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="cbbda-108">В данном процессе происходит утечка этого дескриптора.</span><span class="sxs-lookup"><span data-stu-id="cbbda-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="cbbda-109">В событии указаны источник, исключение, имя процесса и ИД процесса.</span><span class="sxs-lookup"><span data-stu-id="cbbda-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbda-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cbbda-110">See also</span></span>

- [<span data-ttu-id="cbbda-111">Ведение журнала событий</span><span class="sxs-lookup"><span data-stu-id="cbbda-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="cbbda-112">Общие справочные сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="cbbda-112">Events General Reference</span></span>](events-general-reference.md)
