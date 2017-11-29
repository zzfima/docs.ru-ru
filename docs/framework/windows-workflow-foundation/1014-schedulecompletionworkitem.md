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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b6f58cf711a91a748d3516bdd0708cc89b02c623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="5b96a-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="5b96a-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5b96a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5b96a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b96a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5b96a-104">ID</span></span>|<span data-ttu-id="5b96a-105">1014</span><span class="sxs-lookup"><span data-stu-id="5b96a-105">1014</span></span>|  
|<span data-ttu-id="5b96a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="5b96a-106">Keywords</span></span>|<span data-ttu-id="5b96a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5b96a-107">WFRuntime</span></span>|  
|<span data-ttu-id="5b96a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="5b96a-108">Level</span></span>|<span data-ttu-id="5b96a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="5b96a-109">Verbose</span></span>|  
|<span data-ttu-id="5b96a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5b96a-110">Channel</span></span>|<span data-ttu-id="5b96a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5b96a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b96a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5b96a-112">Description</span></span>  
 <span data-ttu-id="5b96a-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="5b96a-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b96a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5b96a-114">Message</span></span>  
 <span data-ttu-id="5b96a-115">CompletionWorkItem был запланирован для родительского элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="5b96a-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5b96a-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="5b96a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b96a-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5b96a-117">Details</span></span>  
  
|<span data-ttu-id="5b96a-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5b96a-118">Data Item Name</span></span>|<span data-ttu-id="5b96a-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5b96a-119">Data Item Type</span></span>|<span data-ttu-id="5b96a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5b96a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b96a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5b96a-121">ParentActivity</span></span>|<span data-ttu-id="5b96a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-122">xs:string</span></span>|<span data-ttu-id="5b96a-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5b96a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5b96a-124">ParentDisplayName</span></span>|<span data-ttu-id="5b96a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-125">xs:string</span></span>|<span data-ttu-id="5b96a-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5b96a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5b96a-127">ParentInstanceId</span></span>|<span data-ttu-id="5b96a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-128">xs:string</span></span>|<span data-ttu-id="5b96a-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5b96a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="5b96a-130">CompletedActivity</span></span>|<span data-ttu-id="5b96a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-131">xs:string</span></span>|<span data-ttu-id="5b96a-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="5b96a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5b96a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="5b96a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-134">xs:string</span></span>|<span data-ttu-id="5b96a-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="5b96a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5b96a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="5b96a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-137">xs:string</span></span>|<span data-ttu-id="5b96a-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5b96a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="5b96a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b96a-139">AppDomain</span></span>|<span data-ttu-id="5b96a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b96a-140">xs:string</span></span>|<span data-ttu-id="5b96a-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5b96a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
