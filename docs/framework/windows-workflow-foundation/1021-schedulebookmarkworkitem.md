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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 781f4b6d064ac90f762e10e03783422c64a1bf05
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="3ad51-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="3ad51-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3ad51-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3ad51-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ad51-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3ad51-104">ID</span></span>|<span data-ttu-id="3ad51-105">1021</span><span class="sxs-lookup"><span data-stu-id="3ad51-105">1021</span></span>|  
|<span data-ttu-id="3ad51-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ad51-106">Keywords</span></span>|<span data-ttu-id="3ad51-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ad51-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ad51-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3ad51-108">Level</span></span>|<span data-ttu-id="3ad51-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3ad51-109">Verbose</span></span>|  
|<span data-ttu-id="3ad51-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3ad51-110">Channel</span></span>|<span data-ttu-id="3ad51-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3ad51-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ad51-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ad51-112">Description</span></span>  
 <span data-ttu-id="3ad51-113">Указывает, что элемент BookmarkWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="3ad51-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ad51-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3ad51-114">Message</span></span>  
 <span data-ttu-id="3ad51-115">BookmarkWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="3ad51-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3ad51-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="3ad51-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ad51-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3ad51-117">Details</span></span>  
  
|<span data-ttu-id="3ad51-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ad51-118">Data Item Name</span></span>|<span data-ttu-id="3ad51-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ad51-119">Data Item Type</span></span>|<span data-ttu-id="3ad51-120">Описание</span><span class="sxs-lookup"><span data-stu-id="3ad51-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ad51-121">Действие</span><span class="sxs-lookup"><span data-stu-id="3ad51-121">Activity</span></span>|<span data-ttu-id="3ad51-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-122">xs:string</span></span>|<span data-ttu-id="3ad51-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="3ad51-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="3ad51-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3ad51-124">DisplayName</span></span>|<span data-ttu-id="3ad51-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-125">xs:string</span></span>|<span data-ttu-id="3ad51-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="3ad51-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="3ad51-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3ad51-127">InstanceId</span></span>|<span data-ttu-id="3ad51-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-128">xs:string</span></span>|<span data-ttu-id="3ad51-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="3ad51-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3ad51-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="3ad51-130">BookmarkName</span></span>|<span data-ttu-id="3ad51-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-131">xs:string</span></span>|<span data-ttu-id="3ad51-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="3ad51-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="3ad51-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="3ad51-133">BookmarkScope</span></span>|<span data-ttu-id="3ad51-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-134">xs:string</span></span>|<span data-ttu-id="3ad51-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="3ad51-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="3ad51-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ad51-136">AppDomain</span></span>|<span data-ttu-id="3ad51-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ad51-137">xs:string</span></span>|<span data-ttu-id="3ad51-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3ad51-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
