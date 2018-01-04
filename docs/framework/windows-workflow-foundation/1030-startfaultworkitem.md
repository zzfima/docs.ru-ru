---
title: 1030 - StartFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 436a0323fcf4498a1d707f7af9bd8204885fd645
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="0f452-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="0f452-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0f452-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0f452-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f452-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="0f452-104">ID</span></span>|<span data-ttu-id="0f452-105">1030</span><span class="sxs-lookup"><span data-stu-id="0f452-105">1030</span></span>|  
|<span data-ttu-id="0f452-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0f452-106">Keywords</span></span>|<span data-ttu-id="0f452-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0f452-107">WFRuntime</span></span>|  
|<span data-ttu-id="0f452-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0f452-108">Level</span></span>|<span data-ttu-id="0f452-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="0f452-109">Verbose</span></span>|  
|<span data-ttu-id="0f452-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0f452-110">Channel</span></span>|<span data-ttu-id="0f452-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0f452-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0f452-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0f452-112">Description</span></span>  
 <span data-ttu-id="0f452-113">Указывает на начало выполнения FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0f452-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0f452-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0f452-114">Message</span></span>  
 <span data-ttu-id="0f452-115">Начинается выполнение элемента FaultWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="0f452-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0f452-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="0f452-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0f452-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0f452-117">Details</span></span>  
  
|<span data-ttu-id="0f452-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0f452-118">Data Item Name</span></span>|<span data-ttu-id="0f452-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0f452-119">Data Item Type</span></span>|<span data-ttu-id="0f452-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0f452-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0f452-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="0f452-121">FaultActivity</span></span>|<span data-ttu-id="0f452-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-122">xs:string</span></span>|<span data-ttu-id="0f452-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0f452-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="0f452-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0f452-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="0f452-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-125">xs:string</span></span>|<span data-ttu-id="0f452-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0f452-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="0f452-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0f452-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="0f452-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-128">xs:string</span></span>|<span data-ttu-id="0f452-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0f452-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="0f452-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="0f452-130">ExceptionActivity</span></span>|<span data-ttu-id="0f452-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-131">xs:string</span></span>|<span data-ttu-id="0f452-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="0f452-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0f452-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0f452-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="0f452-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-134">xs:string</span></span>|<span data-ttu-id="0f452-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="0f452-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0f452-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0f452-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="0f452-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-137">xs:string</span></span>|<span data-ttu-id="0f452-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="0f452-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0f452-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="0f452-139">Exception</span></span>|<span data-ttu-id="0f452-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-140">xs:string</span></span>|<span data-ttu-id="0f452-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="0f452-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="0f452-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0f452-142">AppDomain</span></span>|<span data-ttu-id="0f452-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f452-143">xs:string</span></span>|<span data-ttu-id="0f452-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0f452-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
