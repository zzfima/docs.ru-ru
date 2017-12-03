---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d483a681cae6328dd6111b320a12b5a064d3ff5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="dd3c8-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="dd3c8-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dd3c8-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="dd3c8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd3c8-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="dd3c8-104">ID</span></span>|<span data-ttu-id="dd3c8-105">1014</span><span class="sxs-lookup"><span data-stu-id="dd3c8-105">1014</span></span>|  
|<span data-ttu-id="dd3c8-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="dd3c8-106">Keywords</span></span>|<span data-ttu-id="dd3c8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dd3c8-107">WFRuntime</span></span>|  
|<span data-ttu-id="dd3c8-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="dd3c8-108">Level</span></span>|<span data-ttu-id="dd3c8-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="dd3c8-109">Verbose</span></span>|  
|<span data-ttu-id="dd3c8-110">Канал</span><span class="sxs-lookup"><span data-stu-id="dd3c8-110">Channel</span></span>|<span data-ttu-id="dd3c8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="dd3c8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd3c8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dd3c8-112">Description</span></span>  
 <span data-ttu-id="dd3c8-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd3c8-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="dd3c8-114">Message</span></span>  
 <span data-ttu-id="dd3c8-115">CompletionWorkItem был запланирован для родительского элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="dd3c8-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="dd3c8-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="dd3c8-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd3c8-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="dd3c8-117">Details</span></span>  
  
|<span data-ttu-id="dd3c8-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="dd3c8-118">Data Item Name</span></span>|<span data-ttu-id="dd3c8-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="dd3c8-119">Data Item Type</span></span>|<span data-ttu-id="dd3c8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="dd3c8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd3c8-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="dd3c8-121">ParentActivity</span></span>|<span data-ttu-id="dd3c8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-122">xs:string</span></span>|<span data-ttu-id="dd3c8-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="dd3c8-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="dd3c8-124">ParentDisplayName</span></span>|<span data-ttu-id="dd3c8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-125">xs:string</span></span>|<span data-ttu-id="dd3c8-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="dd3c8-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="dd3c8-127">ParentInstanceId</span></span>|<span data-ttu-id="dd3c8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-128">xs:string</span></span>|<span data-ttu-id="dd3c8-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="dd3c8-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="dd3c8-130">CompletedActivity</span></span>|<span data-ttu-id="dd3c8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-131">xs:string</span></span>|<span data-ttu-id="dd3c8-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="dd3c8-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="dd3c8-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="dd3c8-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-134">xs:string</span></span>|<span data-ttu-id="dd3c8-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="dd3c8-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="dd3c8-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="dd3c8-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-137">xs:string</span></span>|<span data-ttu-id="dd3c8-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="dd3c8-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dd3c8-139">AppDomain</span></span>|<span data-ttu-id="dd3c8-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd3c8-140">xs:string</span></span>|<span data-ttu-id="dd3c8-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dd3c8-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
