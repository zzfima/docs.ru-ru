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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 498752bfc896891a43a6a2e7a8245c508795c1ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="15d53-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="15d53-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="15d53-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="15d53-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15d53-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="15d53-104">ID</span></span>|<span data-ttu-id="15d53-105">1011</span><span class="sxs-lookup"><span data-stu-id="15d53-105">1011</span></span>|  
|<span data-ttu-id="15d53-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15d53-106">Keywords</span></span>|<span data-ttu-id="15d53-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="15d53-107">WFRuntime</span></span>|  
|<span data-ttu-id="15d53-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="15d53-108">Level</span></span>|<span data-ttu-id="15d53-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="15d53-109">Verbose</span></span>|  
|<span data-ttu-id="15d53-110">Канал</span><span class="sxs-lookup"><span data-stu-id="15d53-110">Channel</span></span>|<span data-ttu-id="15d53-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="15d53-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="15d53-112">Описание</span><span class="sxs-lookup"><span data-stu-id="15d53-112">Description</span></span>  
 <span data-ttu-id="15d53-113">Указывает, что элемент ExecuteActivityWorkItem запланирован.</span><span class="sxs-lookup"><span data-stu-id="15d53-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="15d53-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="15d53-114">Message</span></span>  
 <span data-ttu-id="15d53-115">ExecuteActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="15d53-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="15d53-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="15d53-116">Details</span></span>  
  
|<span data-ttu-id="15d53-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="15d53-117">Data Item Name</span></span>|<span data-ttu-id="15d53-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="15d53-118">Data Item Type</span></span>|<span data-ttu-id="15d53-119">Описание</span><span class="sxs-lookup"><span data-stu-id="15d53-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="15d53-120">Действие</span><span class="sxs-lookup"><span data-stu-id="15d53-120">Activity</span></span>|<span data-ttu-id="15d53-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="15d53-121">xs:string</span></span>|<span data-ttu-id="15d53-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="15d53-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="15d53-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="15d53-123">DisplayName</span></span>|<span data-ttu-id="15d53-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="15d53-124">xs:string</span></span>|<span data-ttu-id="15d53-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="15d53-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="15d53-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="15d53-126">InstanceId</span></span>|<span data-ttu-id="15d53-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="15d53-127">xs:string</span></span>|<span data-ttu-id="15d53-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="15d53-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="15d53-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="15d53-129">AppDomain</span></span>|<span data-ttu-id="15d53-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="15d53-130">xs:string</span></span>|<span data-ttu-id="15d53-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="15d53-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
