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
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="497cd-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="497cd-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="497cd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="497cd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="497cd-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="497cd-104">ID</span></span>|<span data-ttu-id="497cd-105">1031</span><span class="sxs-lookup"><span data-stu-id="497cd-105">1031</span></span>|  
|<span data-ttu-id="497cd-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="497cd-106">Keywords</span></span>|<span data-ttu-id="497cd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="497cd-107">WFRuntime</span></span>|  
|<span data-ttu-id="497cd-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="497cd-108">Level</span></span>|<span data-ttu-id="497cd-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="497cd-109">Verbose</span></span>|  
|<span data-ttu-id="497cd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="497cd-110">Channel</span></span>|<span data-ttu-id="497cd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="497cd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="497cd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="497cd-112">Description</span></span>  
 <span data-ttu-id="497cd-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="497cd-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="497cd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="497cd-114">Message</span></span>  
 <span data-ttu-id="497cd-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="497cd-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="497cd-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="497cd-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="497cd-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="497cd-117">Details</span></span>  
  
|<span data-ttu-id="497cd-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="497cd-118">Data Item Name</span></span>|<span data-ttu-id="497cd-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="497cd-119">Data Item Type</span></span>|<span data-ttu-id="497cd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="497cd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="497cd-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="497cd-121">FaultActivity</span></span>|<span data-ttu-id="497cd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-122">xs:string</span></span>|<span data-ttu-id="497cd-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="497cd-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="497cd-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="497cd-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="497cd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-125">xs:string</span></span>|<span data-ttu-id="497cd-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="497cd-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="497cd-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="497cd-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="497cd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-128">xs:string</span></span>|<span data-ttu-id="497cd-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="497cd-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="497cd-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="497cd-130">ExceptionActivity</span></span>|<span data-ttu-id="497cd-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-131">xs:string</span></span>|<span data-ttu-id="497cd-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="497cd-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="497cd-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="497cd-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="497cd-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-134">xs:string</span></span>|<span data-ttu-id="497cd-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="497cd-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="497cd-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="497cd-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="497cd-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-137">xs:string</span></span>|<span data-ttu-id="497cd-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="497cd-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="497cd-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="497cd-139">Exception</span></span>|<span data-ttu-id="497cd-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-140">xs:string</span></span>|<span data-ttu-id="497cd-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="497cd-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="497cd-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="497cd-142">AppDomain</span></span>|<span data-ttu-id="497cd-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="497cd-143">xs:string</span></span>|<span data-ttu-id="497cd-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="497cd-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
