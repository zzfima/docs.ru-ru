---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2a150b9e9c78a9ce1f5e20b962a58ef2d5dde9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="272a4-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="272a4-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="272a4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="272a4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="272a4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="272a4-104">ID</span></span>|<span data-ttu-id="272a4-105">1032</span><span class="sxs-lookup"><span data-stu-id="272a4-105">1032</span></span>|  
|<span data-ttu-id="272a4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="272a4-106">Keywords</span></span>|<span data-ttu-id="272a4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="272a4-107">WFRuntime</span></span>|  
|<span data-ttu-id="272a4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="272a4-108">Level</span></span>|<span data-ttu-id="272a4-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="272a4-109">Verbose</span></span>|  
|<span data-ttu-id="272a4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="272a4-110">Channel</span></span>|<span data-ttu-id="272a4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="272a4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="272a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="272a4-112">Description</span></span>  
 <span data-ttu-id="272a4-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="272a4-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="272a4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="272a4-114">Message</span></span>  
 <span data-ttu-id="272a4-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="272a4-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="272a4-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="272a4-116">Details</span></span>  
  
|<span data-ttu-id="272a4-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="272a4-117">Data Item Name</span></span>|<span data-ttu-id="272a4-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="272a4-118">Data Item Type</span></span>|<span data-ttu-id="272a4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="272a4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="272a4-120">Действие</span><span class="sxs-lookup"><span data-stu-id="272a4-120">Activity</span></span>|<span data-ttu-id="272a4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="272a4-121">xs:string</span></span>|<span data-ttu-id="272a4-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="272a4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="272a4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="272a4-123">DisplayName</span></span>|<span data-ttu-id="272a4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="272a4-124">xs:string</span></span>|<span data-ttu-id="272a4-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="272a4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="272a4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="272a4-126">InstanceId</span></span>|<span data-ttu-id="272a4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="272a4-127">xs:string</span></span>|<span data-ttu-id="272a4-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="272a4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="272a4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="272a4-129">AppDomain</span></span>|<span data-ttu-id="272a4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="272a4-130">xs:string</span></span>|<span data-ttu-id="272a4-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="272a4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
