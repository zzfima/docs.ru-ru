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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0584c6eeaf0e08e92ad94e01e1fca765616440f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="b8e90-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="b8e90-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="b8e90-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b8e90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8e90-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b8e90-104">ID</span></span>|<span data-ttu-id="b8e90-105">1020</span><span class="sxs-lookup"><span data-stu-id="b8e90-105">1020</span></span>|  
|<span data-ttu-id="b8e90-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b8e90-106">Keywords</span></span>|<span data-ttu-id="b8e90-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b8e90-107">WFRuntime</span></span>|  
|<span data-ttu-id="b8e90-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b8e90-108">Level</span></span>|<span data-ttu-id="b8e90-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b8e90-109">Verbose</span></span>|  
|<span data-ttu-id="b8e90-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b8e90-110">Channel</span></span>|<span data-ttu-id="b8e90-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b8e90-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b8e90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b8e90-112">Description</span></span>  
 <span data-ttu-id="b8e90-113">Указывает, что для действия создана закладка.</span><span class="sxs-lookup"><span data-stu-id="b8e90-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b8e90-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b8e90-114">Message</span></span>  
 <span data-ttu-id="b8e90-115">Будет создана закладка для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="b8e90-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b8e90-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="b8e90-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b8e90-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b8e90-117">Details</span></span>  
  
|<span data-ttu-id="b8e90-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8e90-118">Data Item Name</span></span>|<span data-ttu-id="b8e90-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8e90-119">Data Item Type</span></span>|<span data-ttu-id="b8e90-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b8e90-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b8e90-121">Действие</span><span class="sxs-lookup"><span data-stu-id="b8e90-121">Activity</span></span>|<span data-ttu-id="b8e90-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-122">xs:string</span></span>|<span data-ttu-id="b8e90-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="b8e90-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b8e90-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b8e90-124">DisplayName</span></span>|<span data-ttu-id="b8e90-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-125">xs:string</span></span>|<span data-ttu-id="b8e90-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="b8e90-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b8e90-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b8e90-127">InstanceId</span></span>|<span data-ttu-id="b8e90-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-128">xs:string</span></span>|<span data-ttu-id="b8e90-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="b8e90-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b8e90-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="b8e90-130">BookmarkName</span></span>|<span data-ttu-id="b8e90-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-131">xs:string</span></span>|<span data-ttu-id="b8e90-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="b8e90-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="b8e90-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="b8e90-133">BookmarkScope</span></span>|<span data-ttu-id="b8e90-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-134">xs:string</span></span>|<span data-ttu-id="b8e90-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="b8e90-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="b8e90-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b8e90-136">AppDomain</span></span>|<span data-ttu-id="b8e90-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8e90-137">xs:string</span></span>|<span data-ttu-id="b8e90-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b8e90-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
