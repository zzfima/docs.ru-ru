---
title: События конфликтов (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90beb1487581ff4c031d6f10fb613430207dc026
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575571"
---
# <a name="contention-etw-events"></a><span data-ttu-id="a415d-102">События конфликтов (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="a415d-102">Contention ETW Events</span></span>
<span data-ttu-id="a415d-103">События конфликтов возникают каждый раз при обнаружении конфликта за блокировки <xref:System.Threading.Monitor?displayProperty=nameWithType> или блокировки машинного кода, используемые средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a415d-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="a415d-104">Конфликт происходит, когда поток ожидает блокировку, которая обрабатывается другим потоком.</span><span class="sxs-lookup"><span data-stu-id="a415d-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>  
  
 <span data-ttu-id="a415d-105">В следующей таблице показаны ключевое слово, в котором возникает событие конфликта, а также уровень события.</span><span class="sxs-lookup"><span data-stu-id="a415d-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="a415d-106">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a415d-106">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a415d-107">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a415d-107">Keyword for raising the event</span></span>|<span data-ttu-id="a415d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a415d-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a415d-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="a415d-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="a415d-110">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a415d-110">Informational (4)</span></span>|  
  
 <span data-ttu-id="a415d-111">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a415d-111">The following table shows event information.</span></span>  
  
|<span data-ttu-id="a415d-112">событие</span><span class="sxs-lookup"><span data-stu-id="a415d-112">Event</span></span>|<span data-ttu-id="a415d-113">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a415d-113">Event ID</span></span>|<span data-ttu-id="a415d-114">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a415d-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|<span data-ttu-id="a415d-115">81</span><span class="sxs-lookup"><span data-stu-id="a415d-115">81</span></span>|<span data-ttu-id="a415d-116">Начало конфликта.</span><span class="sxs-lookup"><span data-stu-id="a415d-116">Contention starts.</span></span> <span data-ttu-id="a415d-117">Это событие не содержит сведений о времени, в течение которого поток ожидает получения блокировки. Оно возникает только в том случае, когда поток ожидает получения блокировки.</span><span class="sxs-lookup"><span data-stu-id="a415d-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|  
|`ContentionStop`|<span data-ttu-id="a415d-118">81</span><span class="sxs-lookup"><span data-stu-id="a415d-118">81</span></span>|<span data-ttu-id="a415d-119">Конец конфликта.</span><span class="sxs-lookup"><span data-stu-id="a415d-119">Contention ends.</span></span>|  
  
 <span data-ttu-id="a415d-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a415d-120">The following table shows event data.</span></span>  
  
|<span data-ttu-id="a415d-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a415d-121">Field name</span></span>|<span data-ttu-id="a415d-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a415d-122">Data type</span></span>|<span data-ttu-id="a415d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a415d-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a415d-124">Флаги</span><span class="sxs-lookup"><span data-stu-id="a415d-124">Flags</span></span>|<span data-ttu-id="a415d-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="a415d-125">win:UInt8</span></span>|<span data-ttu-id="a415d-126">0 — управляемый; 1 — машинный.</span><span class="sxs-lookup"><span data-stu-id="a415d-126">0 for managed; 1 for native.</span></span>|  
|<span data-ttu-id="a415d-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a415d-127">ClrInstanceID</span></span>|<span data-ttu-id="a415d-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a415d-128">win:UInt16</span></span>|<span data-ttu-id="a415d-129">Уникальный идентификатор экземпляра среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a415d-129">Unique ID for the instance of CLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a415d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a415d-130">See also</span></span>
- [<span data-ttu-id="a415d-131">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="a415d-131">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
