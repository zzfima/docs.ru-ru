---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924752"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="47f63-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="47f63-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="47f63-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="47f63-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47f63-104">ID</span><span class="sxs-lookup"><span data-stu-id="47f63-104">ID</span></span>|<span data-ttu-id="47f63-105">1020</span><span class="sxs-lookup"><span data-stu-id="47f63-105">1020</span></span>|  
|<span data-ttu-id="47f63-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="47f63-106">Keywords</span></span>|<span data-ttu-id="47f63-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="47f63-107">WFRuntime</span></span>|  
|<span data-ttu-id="47f63-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="47f63-108">Level</span></span>|<span data-ttu-id="47f63-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="47f63-109">Verbose</span></span>|  
|<span data-ttu-id="47f63-110">Канал</span><span class="sxs-lookup"><span data-stu-id="47f63-110">Channel</span></span>|<span data-ttu-id="47f63-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="47f63-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="47f63-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47f63-112">Description</span></span>  
 <span data-ttu-id="47f63-113">Указывает, что для действия создана закладка.</span><span class="sxs-lookup"><span data-stu-id="47f63-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="47f63-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="47f63-114">Message</span></span>  
 <span data-ttu-id="47f63-115">Закладка будет создана для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="47f63-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="47f63-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="47f63-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="47f63-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="47f63-117">Details</span></span>  
  
|<span data-ttu-id="47f63-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="47f63-118">Data Item Name</span></span>|<span data-ttu-id="47f63-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="47f63-119">Data Item Type</span></span>|<span data-ttu-id="47f63-120">Описание</span><span class="sxs-lookup"><span data-stu-id="47f63-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="47f63-121">Действие</span><span class="sxs-lookup"><span data-stu-id="47f63-121">Activity</span></span>|<span data-ttu-id="47f63-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-122">xs:string</span></span>|<span data-ttu-id="47f63-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="47f63-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="47f63-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="47f63-124">DisplayName</span></span>|<span data-ttu-id="47f63-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-125">xs:string</span></span>|<span data-ttu-id="47f63-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="47f63-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="47f63-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="47f63-127">InstanceId</span></span>|<span data-ttu-id="47f63-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-128">xs:string</span></span>|<span data-ttu-id="47f63-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="47f63-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="47f63-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="47f63-130">BookmarkName</span></span>|<span data-ttu-id="47f63-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-131">xs:string</span></span>|<span data-ttu-id="47f63-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="47f63-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="47f63-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="47f63-133">BookmarkScope</span></span>|<span data-ttu-id="47f63-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-134">xs:string</span></span>|<span data-ttu-id="47f63-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="47f63-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="47f63-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="47f63-136">AppDomain</span></span>|<span data-ttu-id="47f63-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="47f63-137">xs:string</span></span>|<span data-ttu-id="47f63-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="47f63-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
