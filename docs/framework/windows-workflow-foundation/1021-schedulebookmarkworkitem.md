---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924427"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="e488c-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="e488c-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e488c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e488c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e488c-104">ID</span><span class="sxs-lookup"><span data-stu-id="e488c-104">ID</span></span>|<span data-ttu-id="e488c-105">1021</span><span class="sxs-lookup"><span data-stu-id="e488c-105">1021</span></span>|  
|<span data-ttu-id="e488c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e488c-106">Keywords</span></span>|<span data-ttu-id="e488c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e488c-107">WFRuntime</span></span>|  
|<span data-ttu-id="e488c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e488c-108">Level</span></span>|<span data-ttu-id="e488c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="e488c-109">Verbose</span></span>|  
|<span data-ttu-id="e488c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e488c-110">Channel</span></span>|<span data-ttu-id="e488c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e488c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e488c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e488c-112">Description</span></span>  
 <span data-ttu-id="e488c-113">Указывает, что элемент BookmarkWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="e488c-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e488c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e488c-114">Message</span></span>  
 <span data-ttu-id="e488c-115">BookmarkWorkItem запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="e488c-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="e488c-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="e488c-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e488c-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e488c-117">Details</span></span>  
  
|<span data-ttu-id="e488c-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e488c-118">Data Item Name</span></span>|<span data-ttu-id="e488c-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e488c-119">Data Item Type</span></span>|<span data-ttu-id="e488c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e488c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e488c-121">Действие</span><span class="sxs-lookup"><span data-stu-id="e488c-121">Activity</span></span>|<span data-ttu-id="e488c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-122">xs:string</span></span>|<span data-ttu-id="e488c-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="e488c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="e488c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e488c-124">DisplayName</span></span>|<span data-ttu-id="e488c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-125">xs:string</span></span>|<span data-ttu-id="e488c-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="e488c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="e488c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e488c-127">InstanceId</span></span>|<span data-ttu-id="e488c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-128">xs:string</span></span>|<span data-ttu-id="e488c-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="e488c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e488c-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="e488c-130">BookmarkName</span></span>|<span data-ttu-id="e488c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-131">xs:string</span></span>|<span data-ttu-id="e488c-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="e488c-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="e488c-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="e488c-133">BookmarkScope</span></span>|<span data-ttu-id="e488c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-134">xs:string</span></span>|<span data-ttu-id="e488c-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="e488c-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="e488c-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="e488c-136">AppDomain</span></span>|<span data-ttu-id="e488c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e488c-137">xs:string</span></span>|<span data-ttu-id="e488c-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e488c-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
