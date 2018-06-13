---
title: События стека (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 073622c22b957975ed799cf5b3bc3826473114b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396358"
---
# <a name="stack-etw-event"></a><span data-ttu-id="c7bfe-102">События стека (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="c7bfe-102">Stack ETW Event</span></span>
<span data-ttu-id="c7bfe-103">Событие стека должно использоваться вместе с другими событиями для создания трассировок стека после вызова события.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="c7bfe-104">Оно регистрируется при включенном поставщике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="c7bfe-105">Это очень часто случающееся событие, так как оно сопровождает создание другого события времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="c7bfe-106">По этой причине рекомендуется использовать его с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="c7bfe-107">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="c7bfe-108">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="c7bfe-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c7bfe-109">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c7bfe-109">Keyword for raising the event</span></span>|<span data-ttu-id="c7bfe-110">Уровень</span><span class="sxs-lookup"><span data-stu-id="c7bfe-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c7bfe-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="c7bfe-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="c7bfe-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="c7bfe-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="c7bfe-113">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c7bfe-114">Событие</span><span class="sxs-lookup"><span data-stu-id="c7bfe-114">Event</span></span>|<span data-ttu-id="c7bfe-115">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c7bfe-115">Event ID</span></span>|<span data-ttu-id="c7bfe-116">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c7bfe-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="c7bfe-117">82</span><span class="sxs-lookup"><span data-stu-id="c7bfe-117">82</span></span>|<span data-ttu-id="c7bfe-118">Вместе с другими событиями для создания трассировок стека после этого события.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="c7bfe-119">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c7bfe-120">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c7bfe-120">Field name</span></span>|<span data-ttu-id="c7bfe-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c7bfe-121">Data Type</span></span>|<span data-ttu-id="c7bfe-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c7bfe-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c7bfe-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c7bfe-123">ClrInstanceID</span></span>|<span data-ttu-id="c7bfe-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="c7bfe-124">win:Uint16</span></span>|<span data-ttu-id="c7bfe-125">Уникальный идентификатор среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="c7bfe-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="c7bfe-126">Reserved1</span></span>|<span data-ttu-id="c7bfe-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="c7bfe-127">win:UInt8</span></span>|<span data-ttu-id="c7bfe-128">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-128">Reserved.</span></span>|  
|<span data-ttu-id="c7bfe-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="c7bfe-129">Reserved2</span></span>|<span data-ttu-id="c7bfe-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="c7bfe-130">win:UInt8</span></span>|<span data-ttu-id="c7bfe-131">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-131">Reserved.</span></span>|  
|<span data-ttu-id="c7bfe-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="c7bfe-132">FrameCount</span></span>|<span data-ttu-id="c7bfe-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c7bfe-133">win:UInt32</span></span>|<span data-ttu-id="c7bfe-134">Число кадров в трассировке стека.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="c7bfe-135">Стек</span><span class="sxs-lookup"><span data-stu-id="c7bfe-135">Stack</span></span>|<span data-ttu-id="c7bfe-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c7bfe-136">win:Pointer</span></span>|<span data-ttu-id="c7bfe-137">Столбцы указателей инструкций.</span><span class="sxs-lookup"><span data-stu-id="c7bfe-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7bfe-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c7bfe-138">See Also</span></span>  
 [<span data-ttu-id="c7bfe-139">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="c7bfe-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
