---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1020---createbookmark"></a><span data-ttu-id="bb061-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="bb061-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="bb061-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="bb061-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb061-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="bb061-104">ID</span></span>|<span data-ttu-id="bb061-105">1020</span><span class="sxs-lookup"><span data-stu-id="bb061-105">1020</span></span>|  
|<span data-ttu-id="bb061-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="bb061-106">Keywords</span></span>|<span data-ttu-id="bb061-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bb061-107">WFRuntime</span></span>|  
|<span data-ttu-id="bb061-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="bb061-108">Level</span></span>|<span data-ttu-id="bb061-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="bb061-109">Verbose</span></span>|  
|<span data-ttu-id="bb061-110">Канал</span><span class="sxs-lookup"><span data-stu-id="bb061-110">Channel</span></span>|<span data-ttu-id="bb061-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bb061-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bb061-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bb061-112">Description</span></span>  
 <span data-ttu-id="bb061-113">Указывает, что для действия создана закладка.</span><span class="sxs-lookup"><span data-stu-id="bb061-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bb061-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="bb061-114">Message</span></span>  
 <span data-ttu-id="bb061-115">Будет создана закладка для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="bb061-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="bb061-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="bb061-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bb061-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="bb061-117">Details</span></span>  
  
|<span data-ttu-id="bb061-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="bb061-118">Data Item Name</span></span>|<span data-ttu-id="bb061-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="bb061-119">Data Item Type</span></span>|<span data-ttu-id="bb061-120">Описание</span><span class="sxs-lookup"><span data-stu-id="bb061-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bb061-121">Действие</span><span class="sxs-lookup"><span data-stu-id="bb061-121">Activity</span></span>|<span data-ttu-id="bb061-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-122">xs:string</span></span>|<span data-ttu-id="bb061-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="bb061-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="bb061-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb061-124">DisplayName</span></span>|<span data-ttu-id="bb061-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-125">xs:string</span></span>|<span data-ttu-id="bb061-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="bb061-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="bb061-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bb061-127">InstanceId</span></span>|<span data-ttu-id="bb061-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-128">xs:string</span></span>|<span data-ttu-id="bb061-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="bb061-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bb061-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="bb061-130">BookmarkName</span></span>|<span data-ttu-id="bb061-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-131">xs:string</span></span>|<span data-ttu-id="bb061-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="bb061-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="bb061-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="bb061-133">BookmarkScope</span></span>|<span data-ttu-id="bb061-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-134">xs:string</span></span>|<span data-ttu-id="bb061-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="bb061-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="bb061-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bb061-136">AppDomain</span></span>|<span data-ttu-id="bb061-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb061-137">xs:string</span></span>|<span data-ttu-id="bb061-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bb061-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
