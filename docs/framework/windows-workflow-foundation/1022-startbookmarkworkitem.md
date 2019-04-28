---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924726"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="541cb-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="541cb-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="541cb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="541cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="541cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="541cb-104">ID</span></span>|<span data-ttu-id="541cb-105">1022</span><span class="sxs-lookup"><span data-stu-id="541cb-105">1022</span></span>|  
|<span data-ttu-id="541cb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="541cb-106">Keywords</span></span>|<span data-ttu-id="541cb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="541cb-107">WFRuntime</span></span>|  
|<span data-ttu-id="541cb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="541cb-108">Level</span></span>|<span data-ttu-id="541cb-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="541cb-109">Verbose</span></span>|  
|<span data-ttu-id="541cb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="541cb-110">Channel</span></span>|<span data-ttu-id="541cb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="541cb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="541cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="541cb-112">Description</span></span>  
 <span data-ttu-id="541cb-113">Указывает, что начинается выполнение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="541cb-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="541cb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="541cb-114">Message</span></span>  
 <span data-ttu-id="541cb-115">Начато выполнение BookmarkWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="541cb-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="541cb-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="541cb-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="541cb-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="541cb-117">Details</span></span>  
  
|<span data-ttu-id="541cb-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="541cb-118">Data Item Name</span></span>|<span data-ttu-id="541cb-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="541cb-119">Data Item Type</span></span>|<span data-ttu-id="541cb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="541cb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="541cb-121">Действие</span><span class="sxs-lookup"><span data-stu-id="541cb-121">Activity</span></span>|<span data-ttu-id="541cb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-122">xs:string</span></span>|<span data-ttu-id="541cb-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="541cb-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="541cb-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="541cb-124">DisplayName</span></span>|<span data-ttu-id="541cb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-125">xs:string</span></span>|<span data-ttu-id="541cb-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="541cb-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="541cb-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="541cb-127">InstanceId</span></span>|<span data-ttu-id="541cb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-128">xs:string</span></span>|<span data-ttu-id="541cb-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="541cb-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="541cb-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="541cb-130">BookmarkName</span></span>|<span data-ttu-id="541cb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-131">xs:string</span></span>|<span data-ttu-id="541cb-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="541cb-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="541cb-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="541cb-133">BookmarkScope</span></span>|<span data-ttu-id="541cb-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-134">xs:string</span></span>|<span data-ttu-id="541cb-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="541cb-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="541cb-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="541cb-136">AppDomain</span></span>|<span data-ttu-id="541cb-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="541cb-137">xs:string</span></span>|<span data-ttu-id="541cb-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="541cb-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
