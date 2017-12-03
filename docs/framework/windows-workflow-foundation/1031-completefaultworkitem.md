---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="8d5ec-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="8d5ec-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8d5ec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8d5ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d5ec-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8d5ec-104">ID</span></span>|<span data-ttu-id="8d5ec-105">1031</span><span class="sxs-lookup"><span data-stu-id="8d5ec-105">1031</span></span>|  
|<span data-ttu-id="8d5ec-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8d5ec-106">Keywords</span></span>|<span data-ttu-id="8d5ec-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8d5ec-107">WFRuntime</span></span>|  
|<span data-ttu-id="8d5ec-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8d5ec-108">Level</span></span>|<span data-ttu-id="8d5ec-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8d5ec-109">Verbose</span></span>|  
|<span data-ttu-id="8d5ec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8d5ec-110">Channel</span></span>|<span data-ttu-id="8d5ec-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8d5ec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d5ec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8d5ec-112">Description</span></span>  
 <span data-ttu-id="8d5ec-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d5ec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8d5ec-114">Message</span></span>  
 <span data-ttu-id="8d5ec-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="8d5ec-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="8d5ec-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="8d5ec-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d5ec-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8d5ec-117">Details</span></span>  
  
|<span data-ttu-id="8d5ec-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8d5ec-118">Data Item Name</span></span>|<span data-ttu-id="8d5ec-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8d5ec-119">Data Item Type</span></span>|<span data-ttu-id="8d5ec-120">Описание</span><span class="sxs-lookup"><span data-stu-id="8d5ec-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d5ec-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="8d5ec-121">FaultActivity</span></span>|<span data-ttu-id="8d5ec-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-122">xs:string</span></span>|<span data-ttu-id="8d5ec-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="8d5ec-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8d5ec-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="8d5ec-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-125">xs:string</span></span>|<span data-ttu-id="8d5ec-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="8d5ec-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8d5ec-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="8d5ec-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-128">xs:string</span></span>|<span data-ttu-id="8d5ec-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="8d5ec-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="8d5ec-130">ExceptionActivity</span></span>|<span data-ttu-id="8d5ec-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-131">xs:string</span></span>|<span data-ttu-id="8d5ec-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8d5ec-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8d5ec-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="8d5ec-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-134">xs:string</span></span>|<span data-ttu-id="8d5ec-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8d5ec-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8d5ec-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="8d5ec-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-137">xs:string</span></span>|<span data-ttu-id="8d5ec-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8d5ec-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="8d5ec-139">Exception</span></span>|<span data-ttu-id="8d5ec-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-140">xs:string</span></span>|<span data-ttu-id="8d5ec-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="8d5ec-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="8d5ec-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8d5ec-142">AppDomain</span></span>|<span data-ttu-id="8d5ec-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5ec-143">xs:string</span></span>|<span data-ttu-id="8d5ec-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8d5ec-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
