---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509760"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="7cef6-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="7cef6-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7cef6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7cef6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cef6-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="7cef6-104">ID</span></span>|<span data-ttu-id="7cef6-105">1021</span><span class="sxs-lookup"><span data-stu-id="7cef6-105">1021</span></span>|  
|<span data-ttu-id="7cef6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="7cef6-106">Keywords</span></span>|<span data-ttu-id="7cef6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7cef6-107">WFRuntime</span></span>|  
|<span data-ttu-id="7cef6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="7cef6-108">Level</span></span>|<span data-ttu-id="7cef6-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="7cef6-109">Verbose</span></span>|  
|<span data-ttu-id="7cef6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7cef6-110">Channel</span></span>|<span data-ttu-id="7cef6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7cef6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7cef6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7cef6-112">Description</span></span>  
 <span data-ttu-id="7cef6-113">Указывает, что элемент BookmarkWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="7cef6-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7cef6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7cef6-114">Message</span></span>  
 <span data-ttu-id="7cef6-115">BookmarkWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="7cef6-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="7cef6-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="7cef6-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7cef6-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7cef6-117">Details</span></span>  
  
|<span data-ttu-id="7cef6-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7cef6-118">Data Item Name</span></span>|<span data-ttu-id="7cef6-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7cef6-119">Data Item Type</span></span>|<span data-ttu-id="7cef6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7cef6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7cef6-121">Действие</span><span class="sxs-lookup"><span data-stu-id="7cef6-121">Activity</span></span>|<span data-ttu-id="7cef6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-122">xs:string</span></span>|<span data-ttu-id="7cef6-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="7cef6-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="7cef6-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7cef6-124">DisplayName</span></span>|<span data-ttu-id="7cef6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-125">xs:string</span></span>|<span data-ttu-id="7cef6-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="7cef6-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="7cef6-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7cef6-127">InstanceId</span></span>|<span data-ttu-id="7cef6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-128">xs:string</span></span>|<span data-ttu-id="7cef6-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="7cef6-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7cef6-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="7cef6-130">BookmarkName</span></span>|<span data-ttu-id="7cef6-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-131">xs:string</span></span>|<span data-ttu-id="7cef6-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="7cef6-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="7cef6-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="7cef6-133">BookmarkScope</span></span>|<span data-ttu-id="7cef6-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-134">xs:string</span></span>|<span data-ttu-id="7cef6-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="7cef6-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="7cef6-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7cef6-136">AppDomain</span></span>|<span data-ttu-id="7cef6-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cef6-137">xs:string</span></span>|<span data-ttu-id="7cef6-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7cef6-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
