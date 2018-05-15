---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: 8677f25057486247e64879298755fe972bd373d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="319b5-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="319b5-102">1023 - CompleteBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="319b5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="319b5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="319b5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="319b5-104">ID</span></span>|<span data-ttu-id="319b5-105">1023</span><span class="sxs-lookup"><span data-stu-id="319b5-105">1023</span></span>|  
|<span data-ttu-id="319b5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="319b5-106">Keywords</span></span>|<span data-ttu-id="319b5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="319b5-107">WFRuntime</span></span>|  
|<span data-ttu-id="319b5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="319b5-108">Level</span></span>|<span data-ttu-id="319b5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="319b5-109">Verbose</span></span>|  
|<span data-ttu-id="319b5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="319b5-110">Channel</span></span>|<span data-ttu-id="319b5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="319b5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="319b5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="319b5-112">Description</span></span>  
 <span data-ttu-id="319b5-113">Указывает на завершение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="319b5-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="319b5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="319b5-114">Message</span></span>  
 <span data-ttu-id="319b5-115">BookmarkWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="319b5-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="319b5-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="319b5-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="319b5-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="319b5-117">Details</span></span>  
  
|<span data-ttu-id="319b5-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="319b5-118">Data Item Name</span></span>|<span data-ttu-id="319b5-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="319b5-119">Data Item Type</span></span>|<span data-ttu-id="319b5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="319b5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="319b5-121">Действие</span><span class="sxs-lookup"><span data-stu-id="319b5-121">Activity</span></span>|<span data-ttu-id="319b5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-122">xs:string</span></span>|<span data-ttu-id="319b5-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="319b5-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="319b5-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="319b5-124">DisplayName</span></span>|<span data-ttu-id="319b5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-125">xs:string</span></span>|<span data-ttu-id="319b5-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="319b5-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="319b5-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="319b5-127">InstanceId</span></span>|<span data-ttu-id="319b5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-128">xs:string</span></span>|<span data-ttu-id="319b5-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="319b5-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="319b5-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="319b5-130">BookmarkName</span></span>|<span data-ttu-id="319b5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-131">xs:string</span></span>|<span data-ttu-id="319b5-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="319b5-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="319b5-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="319b5-133">BookmarkScope</span></span>|<span data-ttu-id="319b5-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-134">xs:string</span></span>|<span data-ttu-id="319b5-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="319b5-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="319b5-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="319b5-136">AppDomain</span></span>|<span data-ttu-id="319b5-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="319b5-137">xs:string</span></span>|<span data-ttu-id="319b5-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="319b5-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
