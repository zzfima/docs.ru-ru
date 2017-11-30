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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4de69b1fc2647d7723db8aebb02942938db7478f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="c7039-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="c7039-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c7039-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c7039-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7039-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c7039-104">ID</span></span>|<span data-ttu-id="c7039-105">1032</span><span class="sxs-lookup"><span data-stu-id="c7039-105">1032</span></span>|  
|<span data-ttu-id="c7039-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c7039-106">Keywords</span></span>|<span data-ttu-id="c7039-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c7039-107">WFRuntime</span></span>|  
|<span data-ttu-id="c7039-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="c7039-108">Level</span></span>|<span data-ttu-id="c7039-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c7039-109">Verbose</span></span>|  
|<span data-ttu-id="c7039-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c7039-110">Channel</span></span>|<span data-ttu-id="c7039-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c7039-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7039-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c7039-112">Description</span></span>  
 <span data-ttu-id="c7039-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="c7039-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7039-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c7039-114">Message</span></span>  
 <span data-ttu-id="c7039-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="c7039-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7039-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c7039-116">Details</span></span>  
  
|<span data-ttu-id="c7039-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c7039-117">Data Item Name</span></span>|<span data-ttu-id="c7039-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c7039-118">Data Item Type</span></span>|<span data-ttu-id="c7039-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c7039-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7039-120">Действие</span><span class="sxs-lookup"><span data-stu-id="c7039-120">Activity</span></span>|<span data-ttu-id="c7039-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7039-121">xs:string</span></span>|<span data-ttu-id="c7039-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="c7039-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c7039-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c7039-123">DisplayName</span></span>|<span data-ttu-id="c7039-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7039-124">xs:string</span></span>|<span data-ttu-id="c7039-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="c7039-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c7039-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c7039-126">InstanceId</span></span>|<span data-ttu-id="c7039-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7039-127">xs:string</span></span>|<span data-ttu-id="c7039-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="c7039-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c7039-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7039-129">AppDomain</span></span>|<span data-ttu-id="c7039-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7039-130">xs:string</span></span>|<span data-ttu-id="c7039-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7039-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
