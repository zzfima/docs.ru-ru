---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f9b09001212de6d5aa4f5fde577b9eeb9d967ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="b45b2-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="b45b2-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b45b2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b45b2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b45b2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b45b2-104">ID</span></span>|<span data-ttu-id="b45b2-105">1016</span><span class="sxs-lookup"><span data-stu-id="b45b2-105">1016</span></span>|  
|<span data-ttu-id="b45b2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b45b2-106">Keywords</span></span>|<span data-ttu-id="b45b2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b45b2-107">WFRuntime</span></span>|  
|<span data-ttu-id="b45b2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b45b2-108">Level</span></span>|<span data-ttu-id="b45b2-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b45b2-109">Verbose</span></span>|  
|<span data-ttu-id="b45b2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b45b2-110">Channel</span></span>|<span data-ttu-id="b45b2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b45b2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b45b2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b45b2-112">Description</span></span>  
 <span data-ttu-id="b45b2-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b45b2-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b45b2-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b45b2-114">Message</span></span>  
 <span data-ttu-id="b45b2-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="b45b2-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b45b2-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="b45b2-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b45b2-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b45b2-117">Details</span></span>  
  
|<span data-ttu-id="b45b2-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b45b2-118">Data Item Name</span></span>|<span data-ttu-id="b45b2-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b45b2-119">Data Item Type</span></span>|<span data-ttu-id="b45b2-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b45b2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b45b2-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="b45b2-121">ParentActivity</span></span>|<span data-ttu-id="b45b2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-122">xs:string</span></span>|<span data-ttu-id="b45b2-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="b45b2-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="b45b2-124">ParentDisplayName</span></span>|<span data-ttu-id="b45b2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-125">xs:string</span></span>|<span data-ttu-id="b45b2-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="b45b2-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="b45b2-127">ParentInstanceId</span></span>|<span data-ttu-id="b45b2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-128">xs:string</span></span>|<span data-ttu-id="b45b2-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="b45b2-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="b45b2-130">CompletedActivity</span></span>|<span data-ttu-id="b45b2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-131">xs:string</span></span>|<span data-ttu-id="b45b2-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="b45b2-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b45b2-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="b45b2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-134">xs:string</span></span>|<span data-ttu-id="b45b2-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="b45b2-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b45b2-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="b45b2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-137">xs:string</span></span>|<span data-ttu-id="b45b2-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="b45b2-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="b45b2-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b45b2-139">AppDomain</span></span>|<span data-ttu-id="b45b2-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b45b2-140">xs:string</span></span>|<span data-ttu-id="b45b2-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b45b2-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
