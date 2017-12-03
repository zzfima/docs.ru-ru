---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0837caa668d6395bf1551c319781934bcfecc1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="22814-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="22814-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="22814-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="22814-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22814-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="22814-104">ID</span></span>|<span data-ttu-id="22814-105">1020</span><span class="sxs-lookup"><span data-stu-id="22814-105">1020</span></span>|  
|<span data-ttu-id="22814-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="22814-106">Keywords</span></span>|<span data-ttu-id="22814-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22814-107">WFRuntime</span></span>|  
|<span data-ttu-id="22814-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="22814-108">Level</span></span>|<span data-ttu-id="22814-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="22814-109">Verbose</span></span>|  
|<span data-ttu-id="22814-110">Канал</span><span class="sxs-lookup"><span data-stu-id="22814-110">Channel</span></span>|<span data-ttu-id="22814-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="22814-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22814-112">Описание</span><span class="sxs-lookup"><span data-stu-id="22814-112">Description</span></span>  
 <span data-ttu-id="22814-113">Указывает, что для действия создана закладка.</span><span class="sxs-lookup"><span data-stu-id="22814-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22814-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="22814-114">Message</span></span>  
 <span data-ttu-id="22814-115">Будет создана закладка для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="22814-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="22814-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="22814-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22814-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="22814-117">Details</span></span>  
  
|<span data-ttu-id="22814-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="22814-118">Data Item Name</span></span>|<span data-ttu-id="22814-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="22814-119">Data Item Type</span></span>|<span data-ttu-id="22814-120">Описание</span><span class="sxs-lookup"><span data-stu-id="22814-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22814-121">Действие</span><span class="sxs-lookup"><span data-stu-id="22814-121">Activity</span></span>|<span data-ttu-id="22814-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-122">xs:string</span></span>|<span data-ttu-id="22814-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="22814-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="22814-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="22814-124">DisplayName</span></span>|<span data-ttu-id="22814-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-125">xs:string</span></span>|<span data-ttu-id="22814-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="22814-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="22814-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="22814-127">InstanceId</span></span>|<span data-ttu-id="22814-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-128">xs:string</span></span>|<span data-ttu-id="22814-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="22814-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="22814-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="22814-130">BookmarkName</span></span>|<span data-ttu-id="22814-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-131">xs:string</span></span>|<span data-ttu-id="22814-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="22814-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="22814-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="22814-133">BookmarkScope</span></span>|<span data-ttu-id="22814-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-134">xs:string</span></span>|<span data-ttu-id="22814-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="22814-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="22814-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22814-136">AppDomain</span></span>|<span data-ttu-id="22814-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="22814-137">xs:string</span></span>|<span data-ttu-id="22814-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="22814-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
