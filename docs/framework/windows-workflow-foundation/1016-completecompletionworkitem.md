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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a7c6b6060e8dd3256d23db7350299d2670f6caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="0be5a-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="0be5a-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0be5a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0be5a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0be5a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="0be5a-104">ID</span></span>|<span data-ttu-id="0be5a-105">1016</span><span class="sxs-lookup"><span data-stu-id="0be5a-105">1016</span></span>|  
|<span data-ttu-id="0be5a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0be5a-106">Keywords</span></span>|<span data-ttu-id="0be5a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0be5a-107">WFRuntime</span></span>|  
|<span data-ttu-id="0be5a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0be5a-108">Level</span></span>|<span data-ttu-id="0be5a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="0be5a-109">Verbose</span></span>|  
|<span data-ttu-id="0be5a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0be5a-110">Channel</span></span>|<span data-ttu-id="0be5a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0be5a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0be5a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0be5a-112">Description</span></span>  
 <span data-ttu-id="0be5a-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0be5a-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0be5a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0be5a-114">Message</span></span>  
 <span data-ttu-id="0be5a-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="0be5a-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="0be5a-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="0be5a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0be5a-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0be5a-117">Details</span></span>  
  
|<span data-ttu-id="0be5a-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0be5a-118">Data Item Name</span></span>|<span data-ttu-id="0be5a-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0be5a-119">Data Item Type</span></span>|<span data-ttu-id="0be5a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0be5a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0be5a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0be5a-121">ParentActivity</span></span>|<span data-ttu-id="0be5a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-122">xs:string</span></span>|<span data-ttu-id="0be5a-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0be5a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0be5a-124">ParentDisplayName</span></span>|<span data-ttu-id="0be5a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-125">xs:string</span></span>|<span data-ttu-id="0be5a-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0be5a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0be5a-127">ParentInstanceId</span></span>|<span data-ttu-id="0be5a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-128">xs:string</span></span>|<span data-ttu-id="0be5a-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0be5a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="0be5a-130">CompletedActivity</span></span>|<span data-ttu-id="0be5a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-131">xs:string</span></span>|<span data-ttu-id="0be5a-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="0be5a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0be5a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="0be5a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-134">xs:string</span></span>|<span data-ttu-id="0be5a-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="0be5a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0be5a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="0be5a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-137">xs:string</span></span>|<span data-ttu-id="0be5a-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="0be5a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="0be5a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0be5a-139">AppDomain</span></span>|<span data-ttu-id="0be5a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0be5a-140">xs:string</span></span>|<span data-ttu-id="0be5a-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0be5a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
