---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="686ec-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="686ec-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="686ec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="686ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="686ec-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="686ec-104">ID</span></span>|<span data-ttu-id="686ec-105">1021</span><span class="sxs-lookup"><span data-stu-id="686ec-105">1021</span></span>|  
|<span data-ttu-id="686ec-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="686ec-106">Keywords</span></span>|<span data-ttu-id="686ec-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="686ec-107">WFRuntime</span></span>|  
|<span data-ttu-id="686ec-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="686ec-108">Level</span></span>|<span data-ttu-id="686ec-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="686ec-109">Verbose</span></span>|  
|<span data-ttu-id="686ec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="686ec-110">Channel</span></span>|<span data-ttu-id="686ec-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="686ec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="686ec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="686ec-112">Description</span></span>  
 <span data-ttu-id="686ec-113">Указывает, что элемент BookmarkWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="686ec-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="686ec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="686ec-114">Message</span></span>  
 <span data-ttu-id="686ec-115">BookmarkWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="686ec-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="686ec-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="686ec-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="686ec-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="686ec-117">Details</span></span>  
  
|<span data-ttu-id="686ec-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="686ec-118">Data Item Name</span></span>|<span data-ttu-id="686ec-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="686ec-119">Data Item Type</span></span>|<span data-ttu-id="686ec-120">Описание</span><span class="sxs-lookup"><span data-stu-id="686ec-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="686ec-121">Действие</span><span class="sxs-lookup"><span data-stu-id="686ec-121">Activity</span></span>|<span data-ttu-id="686ec-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-122">xs:string</span></span>|<span data-ttu-id="686ec-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="686ec-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="686ec-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="686ec-124">DisplayName</span></span>|<span data-ttu-id="686ec-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-125">xs:string</span></span>|<span data-ttu-id="686ec-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="686ec-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="686ec-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="686ec-127">InstanceId</span></span>|<span data-ttu-id="686ec-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-128">xs:string</span></span>|<span data-ttu-id="686ec-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="686ec-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="686ec-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="686ec-130">BookmarkName</span></span>|<span data-ttu-id="686ec-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-131">xs:string</span></span>|<span data-ttu-id="686ec-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="686ec-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="686ec-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="686ec-133">BookmarkScope</span></span>|<span data-ttu-id="686ec-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-134">xs:string</span></span>|<span data-ttu-id="686ec-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="686ec-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="686ec-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="686ec-136">AppDomain</span></span>|<span data-ttu-id="686ec-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="686ec-137">xs:string</span></span>|<span data-ttu-id="686ec-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="686ec-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
