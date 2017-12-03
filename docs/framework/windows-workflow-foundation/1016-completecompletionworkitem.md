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
ms.openlocfilehash: b01706f6e84987ea20f52c131139e243e8184c51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="02109-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="02109-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="02109-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="02109-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02109-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="02109-104">ID</span></span>|<span data-ttu-id="02109-105">1016</span><span class="sxs-lookup"><span data-stu-id="02109-105">1016</span></span>|  
|<span data-ttu-id="02109-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="02109-106">Keywords</span></span>|<span data-ttu-id="02109-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="02109-107">WFRuntime</span></span>|  
|<span data-ttu-id="02109-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="02109-108">Level</span></span>|<span data-ttu-id="02109-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="02109-109">Verbose</span></span>|  
|<span data-ttu-id="02109-110">Канал</span><span class="sxs-lookup"><span data-stu-id="02109-110">Channel</span></span>|<span data-ttu-id="02109-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02109-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02109-112">Описание</span><span class="sxs-lookup"><span data-stu-id="02109-112">Description</span></span>  
 <span data-ttu-id="02109-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="02109-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02109-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="02109-114">Message</span></span>  
 <span data-ttu-id="02109-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="02109-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="02109-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="02109-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02109-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="02109-117">Details</span></span>  
  
|<span data-ttu-id="02109-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="02109-118">Data Item Name</span></span>|<span data-ttu-id="02109-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="02109-119">Data Item Type</span></span>|<span data-ttu-id="02109-120">Описание</span><span class="sxs-lookup"><span data-stu-id="02109-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02109-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="02109-121">ParentActivity</span></span>|<span data-ttu-id="02109-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-122">xs:string</span></span>|<span data-ttu-id="02109-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02109-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="02109-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="02109-124">ParentDisplayName</span></span>|<span data-ttu-id="02109-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-125">xs:string</span></span>|<span data-ttu-id="02109-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02109-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="02109-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="02109-127">ParentInstanceId</span></span>|<span data-ttu-id="02109-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-128">xs:string</span></span>|<span data-ttu-id="02109-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02109-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="02109-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="02109-130">CompletedActivity</span></span>|<span data-ttu-id="02109-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-131">xs:string</span></span>|<span data-ttu-id="02109-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="02109-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="02109-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="02109-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="02109-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-134">xs:string</span></span>|<span data-ttu-id="02109-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="02109-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="02109-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="02109-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="02109-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-137">xs:string</span></span>|<span data-ttu-id="02109-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="02109-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="02109-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02109-139">AppDomain</span></span>|<span data-ttu-id="02109-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="02109-140">xs:string</span></span>|<span data-ttu-id="02109-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02109-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
