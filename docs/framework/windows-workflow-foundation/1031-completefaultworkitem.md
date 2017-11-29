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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="ef9e3-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ef9e3-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ef9e3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ef9e3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef9e3-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ef9e3-104">ID</span></span>|<span data-ttu-id="ef9e3-105">1031</span><span class="sxs-lookup"><span data-stu-id="ef9e3-105">1031</span></span>|  
|<span data-ttu-id="ef9e3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ef9e3-106">Keywords</span></span>|<span data-ttu-id="ef9e3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ef9e3-107">WFRuntime</span></span>|  
|<span data-ttu-id="ef9e3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ef9e3-108">Level</span></span>|<span data-ttu-id="ef9e3-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ef9e3-109">Verbose</span></span>|  
|<span data-ttu-id="ef9e3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ef9e3-110">Channel</span></span>|<span data-ttu-id="ef9e3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ef9e3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ef9e3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ef9e3-112">Description</span></span>  
 <span data-ttu-id="ef9e3-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ef9e3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ef9e3-114">Message</span></span>  
 <span data-ttu-id="ef9e3-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="ef9e3-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="ef9e3-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="ef9e3-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ef9e3-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ef9e3-117">Details</span></span>  
  
|<span data-ttu-id="ef9e3-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ef9e3-118">Data Item Name</span></span>|<span data-ttu-id="ef9e3-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ef9e3-119">Data Item Type</span></span>|<span data-ttu-id="ef9e3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ef9e3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ef9e3-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ef9e3-121">FaultActivity</span></span>|<span data-ttu-id="ef9e3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-122">xs:string</span></span>|<span data-ttu-id="ef9e3-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ef9e3-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ef9e3-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ef9e3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-125">xs:string</span></span>|<span data-ttu-id="ef9e3-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ef9e3-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ef9e3-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ef9e3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-128">xs:string</span></span>|<span data-ttu-id="ef9e3-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ef9e3-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ef9e3-130">ExceptionActivity</span></span>|<span data-ttu-id="ef9e3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-131">xs:string</span></span>|<span data-ttu-id="ef9e3-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ef9e3-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ef9e3-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ef9e3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-134">xs:string</span></span>|<span data-ttu-id="ef9e3-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ef9e3-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ef9e3-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ef9e3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-137">xs:string</span></span>|<span data-ttu-id="ef9e3-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ef9e3-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="ef9e3-139">Exception</span></span>|<span data-ttu-id="ef9e3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-140">xs:string</span></span>|<span data-ttu-id="ef9e3-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="ef9e3-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ef9e3-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ef9e3-142">AppDomain</span></span>|<span data-ttu-id="ef9e3-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef9e3-143">xs:string</span></span>|<span data-ttu-id="ef9e3-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ef9e3-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
