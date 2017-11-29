---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="11d7f-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="11d7f-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="11d7f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="11d7f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11d7f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="11d7f-104">ID</span></span>|<span data-ttu-id="11d7f-105">1029</span><span class="sxs-lookup"><span data-stu-id="11d7f-105">1029</span></span>|  
|<span data-ttu-id="11d7f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="11d7f-106">Keywords</span></span>|<span data-ttu-id="11d7f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="11d7f-107">WFRuntime</span></span>|  
|<span data-ttu-id="11d7f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="11d7f-108">Level</span></span>|<span data-ttu-id="11d7f-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="11d7f-109">Verbose</span></span>|  
|<span data-ttu-id="11d7f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="11d7f-110">Channel</span></span>|<span data-ttu-id="11d7f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="11d7f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11d7f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="11d7f-112">Description</span></span>  
 <span data-ttu-id="11d7f-113">Указывает, что FaultWorkItem было предназначено.</span><span class="sxs-lookup"><span data-stu-id="11d7f-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11d7f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="11d7f-114">Message</span></span>  
 <span data-ttu-id="11d7f-115">FaultWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="11d7f-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="11d7f-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="11d7f-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11d7f-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="11d7f-117">Details</span></span>  
  
|<span data-ttu-id="11d7f-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="11d7f-118">Data Item Name</span></span>|<span data-ttu-id="11d7f-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="11d7f-119">Data Item Type</span></span>|<span data-ttu-id="11d7f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="11d7f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11d7f-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="11d7f-121">FaultActivity</span></span>|<span data-ttu-id="11d7f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-122">xs:string</span></span>|<span data-ttu-id="11d7f-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11d7f-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="11d7f-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="11d7f-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="11d7f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-125">xs:string</span></span>|<span data-ttu-id="11d7f-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11d7f-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="11d7f-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="11d7f-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="11d7f-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-128">xs:string</span></span>|<span data-ttu-id="11d7f-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11d7f-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="11d7f-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="11d7f-130">ExceptionActivity</span></span>|<span data-ttu-id="11d7f-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-131">xs:string</span></span>|<span data-ttu-id="11d7f-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="11d7f-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11d7f-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="11d7f-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="11d7f-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-134">xs:string</span></span>|<span data-ttu-id="11d7f-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="11d7f-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11d7f-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="11d7f-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="11d7f-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-137">xs:string</span></span>|<span data-ttu-id="11d7f-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="11d7f-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="11d7f-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="11d7f-139">Exception</span></span>|<span data-ttu-id="11d7f-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-140">xs:string</span></span>|<span data-ttu-id="11d7f-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="11d7f-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="11d7f-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11d7f-142">AppDomain</span></span>|<span data-ttu-id="11d7f-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d7f-143">xs:string</span></span>|<span data-ttu-id="11d7f-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="11d7f-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
