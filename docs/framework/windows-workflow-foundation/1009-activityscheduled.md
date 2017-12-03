---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="7c11b-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="7c11b-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="7c11b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7c11b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c11b-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="7c11b-104">ID</span></span>|<span data-ttu-id="7c11b-105">1009</span><span class="sxs-lookup"><span data-stu-id="7c11b-105">1009</span></span>|  
|<span data-ttu-id="7c11b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="7c11b-106">Keywords</span></span>|<span data-ttu-id="7c11b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7c11b-107">WFRuntime</span></span>|  
|<span data-ttu-id="7c11b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="7c11b-108">Level</span></span>|<span data-ttu-id="7c11b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7c11b-109">Information</span></span>|  
|<span data-ttu-id="7c11b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7c11b-110">Channel</span></span>|<span data-ttu-id="7c11b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7c11b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7c11b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7c11b-112">Description</span></span>  
 <span data-ttu-id="7c11b-113">Указывает, что действие запланировано для выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c11b-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7c11b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7c11b-114">Message</span></span>  
 <span data-ttu-id="7c11b-115">Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).</span><span class="sxs-lookup"><span data-stu-id="7c11b-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7c11b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7c11b-116">Details</span></span>  
  
|<span data-ttu-id="7c11b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7c11b-117">Data Item Name</span></span>|<span data-ttu-id="7c11b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7c11b-118">Data Item Type</span></span>|<span data-ttu-id="7c11b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7c11b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7c11b-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="7c11b-120">ParentActivity</span></span>|<span data-ttu-id="7c11b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-121">xs:string</span></span>|<span data-ttu-id="7c11b-122">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="7c11b-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="7c11b-123">ParentDisplayName</span></span>|<span data-ttu-id="7c11b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-124">xs:string</span></span>|<span data-ttu-id="7c11b-125">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="7c11b-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="7c11b-126">ParentInstanceId</span></span>|<span data-ttu-id="7c11b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-127">xs:string</span></span>|<span data-ttu-id="7c11b-128">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="7c11b-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="7c11b-129">ChildActivity</span></span>|<span data-ttu-id="7c11b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-130">xs:string</span></span>|<span data-ttu-id="7c11b-131">Имя типа запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7c11b-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="7c11b-132">ChildDisplayName</span></span>|<span data-ttu-id="7c11b-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-133">xs:string</span></span>|<span data-ttu-id="7c11b-134">Отображаемое имя запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7c11b-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="7c11b-135">ChildInstanceId</span></span>|<span data-ttu-id="7c11b-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-136">xs:string</span></span>|<span data-ttu-id="7c11b-137">Идентификатор экземпляра запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="7c11b-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7c11b-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7c11b-138">AppDomain</span></span>|<span data-ttu-id="7c11b-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c11b-139">xs:string</span></span>|<span data-ttu-id="7c11b-140">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7c11b-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
