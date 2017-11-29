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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9463fbf2e7f2ac3424488dc3fca322a91d11126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="6bd1d-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="6bd1d-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="6bd1d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6bd1d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bd1d-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6bd1d-104">ID</span></span>|<span data-ttu-id="6bd1d-105">1009</span><span class="sxs-lookup"><span data-stu-id="6bd1d-105">1009</span></span>|  
|<span data-ttu-id="6bd1d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6bd1d-106">Keywords</span></span>|<span data-ttu-id="6bd1d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6bd1d-107">WFRuntime</span></span>|  
|<span data-ttu-id="6bd1d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6bd1d-108">Level</span></span>|<span data-ttu-id="6bd1d-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="6bd1d-109">Information</span></span>|  
|<span data-ttu-id="6bd1d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6bd1d-110">Channel</span></span>|<span data-ttu-id="6bd1d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6bd1d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6bd1d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6bd1d-112">Description</span></span>  
 <span data-ttu-id="6bd1d-113">Указывает, что действие запланировано для выполнения.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6bd1d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6bd1d-114">Message</span></span>  
 <span data-ttu-id="6bd1d-115">Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).</span><span class="sxs-lookup"><span data-stu-id="6bd1d-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6bd1d-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6bd1d-116">Details</span></span>  
  
|<span data-ttu-id="6bd1d-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6bd1d-117">Data Item Name</span></span>|<span data-ttu-id="6bd1d-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6bd1d-118">Data Item Type</span></span>|<span data-ttu-id="6bd1d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6bd1d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6bd1d-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="6bd1d-120">ParentActivity</span></span>|<span data-ttu-id="6bd1d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-121">xs:string</span></span>|<span data-ttu-id="6bd1d-122">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="6bd1d-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="6bd1d-123">ParentDisplayName</span></span>|<span data-ttu-id="6bd1d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-124">xs:string</span></span>|<span data-ttu-id="6bd1d-125">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="6bd1d-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="6bd1d-126">ParentInstanceId</span></span>|<span data-ttu-id="6bd1d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-127">xs:string</span></span>|<span data-ttu-id="6bd1d-128">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="6bd1d-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="6bd1d-129">ChildActivity</span></span>|<span data-ttu-id="6bd1d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-130">xs:string</span></span>|<span data-ttu-id="6bd1d-131">Имя типа запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6bd1d-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="6bd1d-132">ChildDisplayName</span></span>|<span data-ttu-id="6bd1d-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-133">xs:string</span></span>|<span data-ttu-id="6bd1d-134">Отображаемое имя запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6bd1d-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="6bd1d-135">ChildInstanceId</span></span>|<span data-ttu-id="6bd1d-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-136">xs:string</span></span>|<span data-ttu-id="6bd1d-137">Идентификатор экземпляра запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6bd1d-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6bd1d-138">AppDomain</span></span>|<span data-ttu-id="6bd1d-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bd1d-139">xs:string</span></span>|<span data-ttu-id="6bd1d-140">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6bd1d-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
