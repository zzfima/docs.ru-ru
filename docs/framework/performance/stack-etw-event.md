---
title: События стека (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7cba2bd1dd5b83e29c7a6c192a1a7e5e2d33ecc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949153"
---
# <a name="stack-etw-event"></a><span data-ttu-id="67167-102">События стека (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="67167-102">Stack ETW Event</span></span>
<span data-ttu-id="67167-103">Событие стека должно использоваться вместе с другими событиями для создания трассировок стека после вызова события.</span><span class="sxs-lookup"><span data-stu-id="67167-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="67167-104">Оно регистрируется при включенном поставщике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="67167-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="67167-105">Это очень часто случающееся событие, так как оно сопровождает создание другого события времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="67167-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="67167-106">По этой причине рекомендуется использовать его с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="67167-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="67167-107">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="67167-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="67167-108">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="67167-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="67167-109">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="67167-109">Keyword for raising the event</span></span>|<span data-ttu-id="67167-110">Уровень</span><span class="sxs-lookup"><span data-stu-id="67167-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="67167-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="67167-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="67167-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="67167-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="67167-113">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="67167-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="67167-114">событие</span><span class="sxs-lookup"><span data-stu-id="67167-114">Event</span></span>|<span data-ttu-id="67167-115">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="67167-115">Event ID</span></span>|<span data-ttu-id="67167-116">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="67167-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="67167-117">82</span><span class="sxs-lookup"><span data-stu-id="67167-117">82</span></span>|<span data-ttu-id="67167-118">Вместе с другими событиями для создания трассировок стека после этого события.</span><span class="sxs-lookup"><span data-stu-id="67167-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="67167-119">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="67167-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="67167-120">Имя поля</span><span class="sxs-lookup"><span data-stu-id="67167-120">Field name</span></span>|<span data-ttu-id="67167-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="67167-121">Data Type</span></span>|<span data-ttu-id="67167-122">Описание</span><span class="sxs-lookup"><span data-stu-id="67167-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="67167-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="67167-123">ClrInstanceID</span></span>|<span data-ttu-id="67167-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="67167-124">win:Uint16</span></span>|<span data-ttu-id="67167-125">Уникальный идентификатор среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="67167-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="67167-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="67167-126">Reserved1</span></span>|<span data-ttu-id="67167-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="67167-127">win:UInt8</span></span>|<span data-ttu-id="67167-128">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="67167-128">Reserved.</span></span>|  
|<span data-ttu-id="67167-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="67167-129">Reserved2</span></span>|<span data-ttu-id="67167-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="67167-130">win:UInt8</span></span>|<span data-ttu-id="67167-131">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="67167-131">Reserved.</span></span>|  
|<span data-ttu-id="67167-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="67167-132">FrameCount</span></span>|<span data-ttu-id="67167-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="67167-133">win:UInt32</span></span>|<span data-ttu-id="67167-134">Число кадров в трассировке стека.</span><span class="sxs-lookup"><span data-stu-id="67167-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="67167-135">Стек</span><span class="sxs-lookup"><span data-stu-id="67167-135">Stack</span></span>|<span data-ttu-id="67167-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="67167-136">win:Pointer</span></span>|<span data-ttu-id="67167-137">Столбцы указателей инструкций.</span><span class="sxs-lookup"><span data-stu-id="67167-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67167-138">См. также</span><span class="sxs-lookup"><span data-stu-id="67167-138">See also</span></span>

- [<span data-ttu-id="67167-139">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="67167-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
