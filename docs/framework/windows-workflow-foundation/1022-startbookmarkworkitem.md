---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9aaabbdca455d31d22b232ae2b08edef0687ac30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="35b41-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="35b41-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="35b41-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="35b41-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35b41-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="35b41-104">ID</span></span>|<span data-ttu-id="35b41-105">1022</span><span class="sxs-lookup"><span data-stu-id="35b41-105">1022</span></span>|  
|<span data-ttu-id="35b41-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35b41-106">Keywords</span></span>|<span data-ttu-id="35b41-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="35b41-107">WFRuntime</span></span>|  
|<span data-ttu-id="35b41-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="35b41-108">Level</span></span>|<span data-ttu-id="35b41-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="35b41-109">Verbose</span></span>|  
|<span data-ttu-id="35b41-110">Канал</span><span class="sxs-lookup"><span data-stu-id="35b41-110">Channel</span></span>|<span data-ttu-id="35b41-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="35b41-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35b41-112">Описание</span><span class="sxs-lookup"><span data-stu-id="35b41-112">Description</span></span>  
 <span data-ttu-id="35b41-113">Указывает, что начинается выполнение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="35b41-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35b41-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="35b41-114">Message</span></span>  
 <span data-ttu-id="35b41-115">Начинается выполнение элемента bookmarkworkitem для элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="35b41-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="35b41-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="35b41-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35b41-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="35b41-117">Details</span></span>  
  
|<span data-ttu-id="35b41-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="35b41-118">Data Item Name</span></span>|<span data-ttu-id="35b41-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="35b41-119">Data Item Type</span></span>|<span data-ttu-id="35b41-120">Описание</span><span class="sxs-lookup"><span data-stu-id="35b41-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35b41-121">Действие</span><span class="sxs-lookup"><span data-stu-id="35b41-121">Activity</span></span>|<span data-ttu-id="35b41-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-122">xs:string</span></span>|<span data-ttu-id="35b41-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="35b41-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="35b41-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="35b41-124">DisplayName</span></span>|<span data-ttu-id="35b41-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-125">xs:string</span></span>|<span data-ttu-id="35b41-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="35b41-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="35b41-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="35b41-127">InstanceId</span></span>|<span data-ttu-id="35b41-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-128">xs:string</span></span>|<span data-ttu-id="35b41-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="35b41-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="35b41-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="35b41-130">BookmarkName</span></span>|<span data-ttu-id="35b41-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-131">xs:string</span></span>|<span data-ttu-id="35b41-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="35b41-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="35b41-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="35b41-133">BookmarkScope</span></span>|<span data-ttu-id="35b41-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-134">xs:string</span></span>|<span data-ttu-id="35b41-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="35b41-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="35b41-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35b41-136">AppDomain</span></span>|<span data-ttu-id="35b41-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b41-137">xs:string</span></span>|<span data-ttu-id="35b41-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="35b41-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
