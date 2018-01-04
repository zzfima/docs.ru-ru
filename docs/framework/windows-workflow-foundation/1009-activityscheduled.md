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
ms.workload: dotnet
ms.openlocfilehash: 4a0d8cc3d17ecd13d9312b42554ef5347cccf213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="926b6-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="926b6-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="926b6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="926b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="926b6-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="926b6-104">ID</span></span>|<span data-ttu-id="926b6-105">1009</span><span class="sxs-lookup"><span data-stu-id="926b6-105">1009</span></span>|  
|<span data-ttu-id="926b6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="926b6-106">Keywords</span></span>|<span data-ttu-id="926b6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="926b6-107">WFRuntime</span></span>|  
|<span data-ttu-id="926b6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="926b6-108">Level</span></span>|<span data-ttu-id="926b6-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="926b6-109">Information</span></span>|  
|<span data-ttu-id="926b6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="926b6-110">Channel</span></span>|<span data-ttu-id="926b6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="926b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="926b6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="926b6-112">Description</span></span>  
 <span data-ttu-id="926b6-113">Указывает, что действие запланировано для выполнения.</span><span class="sxs-lookup"><span data-stu-id="926b6-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="926b6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="926b6-114">Message</span></span>  
 <span data-ttu-id="926b6-115">Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).</span><span class="sxs-lookup"><span data-stu-id="926b6-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="926b6-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="926b6-116">Details</span></span>  
  
|<span data-ttu-id="926b6-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="926b6-117">Data Item Name</span></span>|<span data-ttu-id="926b6-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="926b6-118">Data Item Type</span></span>|<span data-ttu-id="926b6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="926b6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="926b6-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="926b6-120">ParentActivity</span></span>|<span data-ttu-id="926b6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-121">xs:string</span></span>|<span data-ttu-id="926b6-122">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="926b6-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="926b6-123">ParentDisplayName</span></span>|<span data-ttu-id="926b6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-124">xs:string</span></span>|<span data-ttu-id="926b6-125">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="926b6-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="926b6-126">ParentInstanceId</span></span>|<span data-ttu-id="926b6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-127">xs:string</span></span>|<span data-ttu-id="926b6-128">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="926b6-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="926b6-129">ChildActivity</span></span>|<span data-ttu-id="926b6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-130">xs:string</span></span>|<span data-ttu-id="926b6-131">Имя типа запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="926b6-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="926b6-132">ChildDisplayName</span></span>|<span data-ttu-id="926b6-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-133">xs:string</span></span>|<span data-ttu-id="926b6-134">Отображаемое имя запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="926b6-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="926b6-135">ChildInstanceId</span></span>|<span data-ttu-id="926b6-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-136">xs:string</span></span>|<span data-ttu-id="926b6-137">Идентификатор экземпляра запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="926b6-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="926b6-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="926b6-138">AppDomain</span></span>|<span data-ttu-id="926b6-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="926b6-139">xs:string</span></span>|<span data-ttu-id="926b6-140">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="926b6-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
