---
title: События стека (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: f3014a04ba7cacbe37b6706e2919ffd7de19aa65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715907"
---
# <a name="stack-etw-event"></a><span data-ttu-id="6f7aa-102">События стека (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="6f7aa-102">Stack ETW Event</span></span>
<span data-ttu-id="6f7aa-103">Событие стека должно использоваться вместе с другими событиями для создания трассировок стека после вызова события.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="6f7aa-104">Оно регистрируется при включенном поставщике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="6f7aa-105">Это очень часто случающееся событие, так как оно сопровождает создание другого события времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="6f7aa-106">По этой причине рекомендуется использовать его с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="6f7aa-107">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="6f7aa-108">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="6f7aa-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6f7aa-109">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6f7aa-109">Keyword for raising the event</span></span>|<span data-ttu-id="6f7aa-110">Уровень</span><span class="sxs-lookup"><span data-stu-id="6f7aa-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6f7aa-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="6f7aa-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="6f7aa-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="6f7aa-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="6f7aa-113">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6f7aa-114">Event</span><span class="sxs-lookup"><span data-stu-id="6f7aa-114">Event</span></span>|<span data-ttu-id="6f7aa-115">Код события</span><span class="sxs-lookup"><span data-stu-id="6f7aa-115">Event ID</span></span>|<span data-ttu-id="6f7aa-116">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6f7aa-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="6f7aa-117">82</span><span class="sxs-lookup"><span data-stu-id="6f7aa-117">82</span></span>|<span data-ttu-id="6f7aa-118">Вместе с другими событиями для создания трассировок стека после этого события.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="6f7aa-119">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6f7aa-120">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6f7aa-120">Field name</span></span>|<span data-ttu-id="6f7aa-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6f7aa-121">Data Type</span></span>|<span data-ttu-id="6f7aa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6f7aa-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6f7aa-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f7aa-123">ClrInstanceID</span></span>|<span data-ttu-id="6f7aa-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="6f7aa-124">win:Uint16</span></span>|<span data-ttu-id="6f7aa-125">Уникальный идентификатор среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="6f7aa-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="6f7aa-126">Reserved1</span></span>|<span data-ttu-id="6f7aa-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="6f7aa-127">win:UInt8</span></span>|<span data-ttu-id="6f7aa-128">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-128">Reserved.</span></span>|  
|<span data-ttu-id="6f7aa-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="6f7aa-129">Reserved2</span></span>|<span data-ttu-id="6f7aa-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="6f7aa-130">win:UInt8</span></span>|<span data-ttu-id="6f7aa-131">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-131">Reserved.</span></span>|  
|<span data-ttu-id="6f7aa-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="6f7aa-132">FrameCount</span></span>|<span data-ttu-id="6f7aa-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6f7aa-133">win:UInt32</span></span>|<span data-ttu-id="6f7aa-134">Число кадров в трассировке стека.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="6f7aa-135">Стек</span><span class="sxs-lookup"><span data-stu-id="6f7aa-135">Stack</span></span>|<span data-ttu-id="6f7aa-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="6f7aa-136">win:Pointer</span></span>|<span data-ttu-id="6f7aa-137">Столбцы указателей инструкций.</span><span class="sxs-lookup"><span data-stu-id="6f7aa-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f7aa-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f7aa-138">See also</span></span>

- [<span data-ttu-id="6f7aa-139">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="6f7aa-139">CLR ETW Events</span></span>](clr-etw-events.md)
