---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec89acb9d83a28ac280db7c3d536bfe63669fa97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="ee41a-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ee41a-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ee41a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ee41a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee41a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ee41a-104">ID</span></span>|<span data-ttu-id="ee41a-105">1011</span><span class="sxs-lookup"><span data-stu-id="ee41a-105">1011</span></span>|  
|<span data-ttu-id="ee41a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ee41a-106">Keywords</span></span>|<span data-ttu-id="ee41a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ee41a-107">WFRuntime</span></span>|  
|<span data-ttu-id="ee41a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ee41a-108">Level</span></span>|<span data-ttu-id="ee41a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ee41a-109">Verbose</span></span>|  
|<span data-ttu-id="ee41a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ee41a-110">Channel</span></span>|<span data-ttu-id="ee41a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ee41a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee41a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ee41a-112">Description</span></span>  
 <span data-ttu-id="ee41a-113">Указывает, что элемент ExecuteActivityWorkItem запланирован.</span><span class="sxs-lookup"><span data-stu-id="ee41a-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee41a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ee41a-114">Message</span></span>  
 <span data-ttu-id="ee41a-115">ExecuteActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="ee41a-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee41a-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ee41a-116">Details</span></span>  
  
|<span data-ttu-id="ee41a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ee41a-117">Data Item Name</span></span>|<span data-ttu-id="ee41a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ee41a-118">Data Item Type</span></span>|<span data-ttu-id="ee41a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ee41a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee41a-120">Действие</span><span class="sxs-lookup"><span data-stu-id="ee41a-120">Activity</span></span>|<span data-ttu-id="ee41a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee41a-121">xs:string</span></span>|<span data-ttu-id="ee41a-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="ee41a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ee41a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ee41a-123">DisplayName</span></span>|<span data-ttu-id="ee41a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee41a-124">xs:string</span></span>|<span data-ttu-id="ee41a-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="ee41a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ee41a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ee41a-126">InstanceId</span></span>|<span data-ttu-id="ee41a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee41a-127">xs:string</span></span>|<span data-ttu-id="ee41a-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="ee41a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ee41a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ee41a-129">AppDomain</span></span>|<span data-ttu-id="ee41a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee41a-130">xs:string</span></span>|<span data-ttu-id="ee41a-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ee41a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
