---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: 8677f25057486247e64879298755fe972bd373d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008854"
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="158da-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="158da-102">1023 - CompleteBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="158da-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="158da-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="158da-104">ID</span><span class="sxs-lookup"><span data-stu-id="158da-104">ID</span></span>|<span data-ttu-id="158da-105">1023</span><span class="sxs-lookup"><span data-stu-id="158da-105">1023</span></span>|  
|<span data-ttu-id="158da-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="158da-106">Keywords</span></span>|<span data-ttu-id="158da-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="158da-107">WFRuntime</span></span>|  
|<span data-ttu-id="158da-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="158da-108">Level</span></span>|<span data-ttu-id="158da-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="158da-109">Verbose</span></span>|  
|<span data-ttu-id="158da-110">Канал</span><span class="sxs-lookup"><span data-stu-id="158da-110">Channel</span></span>|<span data-ttu-id="158da-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="158da-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="158da-112">Описание</span><span class="sxs-lookup"><span data-stu-id="158da-112">Description</span></span>  
 <span data-ttu-id="158da-113">Указывает на завершение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="158da-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="158da-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="158da-114">Message</span></span>  
 <span data-ttu-id="158da-115">BookmarkWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="158da-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="158da-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="158da-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="158da-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="158da-117">Details</span></span>  
  
|<span data-ttu-id="158da-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="158da-118">Data Item Name</span></span>|<span data-ttu-id="158da-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="158da-119">Data Item Type</span></span>|<span data-ttu-id="158da-120">Описание</span><span class="sxs-lookup"><span data-stu-id="158da-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="158da-121">Действие</span><span class="sxs-lookup"><span data-stu-id="158da-121">Activity</span></span>|<span data-ttu-id="158da-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-122">xs:string</span></span>|<span data-ttu-id="158da-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="158da-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="158da-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="158da-124">DisplayName</span></span>|<span data-ttu-id="158da-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-125">xs:string</span></span>|<span data-ttu-id="158da-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="158da-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="158da-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="158da-127">InstanceId</span></span>|<span data-ttu-id="158da-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-128">xs:string</span></span>|<span data-ttu-id="158da-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="158da-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="158da-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="158da-130">BookmarkName</span></span>|<span data-ttu-id="158da-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-131">xs:string</span></span>|<span data-ttu-id="158da-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="158da-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="158da-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="158da-133">BookmarkScope</span></span>|<span data-ttu-id="158da-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-134">xs:string</span></span>|<span data-ttu-id="158da-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="158da-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="158da-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="158da-136">AppDomain</span></span>|<span data-ttu-id="158da-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="158da-137">xs:string</span></span>|<span data-ttu-id="158da-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="158da-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
