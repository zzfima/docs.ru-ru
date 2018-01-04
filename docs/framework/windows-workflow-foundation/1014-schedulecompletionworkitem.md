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
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="29614-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="29614-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="29614-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="29614-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29614-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="29614-104">ID</span></span>|<span data-ttu-id="29614-105">1014</span><span class="sxs-lookup"><span data-stu-id="29614-105">1014</span></span>|  
|<span data-ttu-id="29614-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="29614-106">Keywords</span></span>|<span data-ttu-id="29614-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="29614-107">WFRuntime</span></span>|  
|<span data-ttu-id="29614-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="29614-108">Level</span></span>|<span data-ttu-id="29614-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="29614-109">Verbose</span></span>|  
|<span data-ttu-id="29614-110">Канал</span><span class="sxs-lookup"><span data-stu-id="29614-110">Channel</span></span>|<span data-ttu-id="29614-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="29614-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="29614-112">Описание</span><span class="sxs-lookup"><span data-stu-id="29614-112">Description</span></span>  
 <span data-ttu-id="29614-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="29614-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="29614-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="29614-114">Message</span></span>  
 <span data-ttu-id="29614-115">CompletionWorkItem был запланирован для родительского элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="29614-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="29614-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="29614-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="29614-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="29614-117">Details</span></span>  
  
|<span data-ttu-id="29614-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="29614-118">Data Item Name</span></span>|<span data-ttu-id="29614-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="29614-119">Data Item Type</span></span>|<span data-ttu-id="29614-120">Описание</span><span class="sxs-lookup"><span data-stu-id="29614-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="29614-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="29614-121">ParentActivity</span></span>|<span data-ttu-id="29614-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-122">xs:string</span></span>|<span data-ttu-id="29614-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="29614-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="29614-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="29614-124">ParentDisplayName</span></span>|<span data-ttu-id="29614-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-125">xs:string</span></span>|<span data-ttu-id="29614-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="29614-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="29614-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="29614-127">ParentInstanceId</span></span>|<span data-ttu-id="29614-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-128">xs:string</span></span>|<span data-ttu-id="29614-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="29614-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="29614-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="29614-130">CompletedActivity</span></span>|<span data-ttu-id="29614-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-131">xs:string</span></span>|<span data-ttu-id="29614-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="29614-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="29614-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="29614-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="29614-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-134">xs:string</span></span>|<span data-ttu-id="29614-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="29614-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="29614-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="29614-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="29614-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-137">xs:string</span></span>|<span data-ttu-id="29614-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="29614-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="29614-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="29614-139">AppDomain</span></span>|<span data-ttu-id="29614-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="29614-140">xs:string</span></span>|<span data-ttu-id="29614-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="29614-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
