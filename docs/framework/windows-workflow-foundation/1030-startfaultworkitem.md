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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b25dbd5ced96b8e9ca3ef51e4de841a6238d2cbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="c7941-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="c7941-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c7941-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c7941-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7941-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c7941-104">ID</span></span>|<span data-ttu-id="c7941-105">1030</span><span class="sxs-lookup"><span data-stu-id="c7941-105">1030</span></span>|  
|<span data-ttu-id="c7941-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c7941-106">Keywords</span></span>|<span data-ttu-id="c7941-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c7941-107">WFRuntime</span></span>|  
|<span data-ttu-id="c7941-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="c7941-108">Level</span></span>|<span data-ttu-id="c7941-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c7941-109">Verbose</span></span>|  
|<span data-ttu-id="c7941-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c7941-110">Channel</span></span>|<span data-ttu-id="c7941-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c7941-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7941-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c7941-112">Description</span></span>  
 <span data-ttu-id="c7941-113">Указывает на начало выполнения FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="c7941-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7941-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c7941-114">Message</span></span>  
 <span data-ttu-id="c7941-115">Начинается выполнение элемента FaultWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="c7941-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c7941-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="c7941-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7941-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c7941-117">Details</span></span>  
  
|<span data-ttu-id="c7941-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c7941-118">Data Item Name</span></span>|<span data-ttu-id="c7941-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c7941-119">Data Item Type</span></span>|<span data-ttu-id="c7941-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c7941-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7941-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="c7941-121">FaultActivity</span></span>|<span data-ttu-id="c7941-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-122">xs:string</span></span>|<span data-ttu-id="c7941-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c7941-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="c7941-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7941-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="c7941-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-125">xs:string</span></span>|<span data-ttu-id="c7941-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c7941-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="c7941-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7941-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="c7941-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-128">xs:string</span></span>|<span data-ttu-id="c7941-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c7941-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="c7941-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="c7941-130">ExceptionActivity</span></span>|<span data-ttu-id="c7941-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-131">xs:string</span></span>|<span data-ttu-id="c7941-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c7941-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7941-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7941-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="c7941-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-134">xs:string</span></span>|<span data-ttu-id="c7941-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c7941-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7941-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7941-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="c7941-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-137">xs:string</span></span>|<span data-ttu-id="c7941-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c7941-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c7941-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="c7941-139">Exception</span></span>|<span data-ttu-id="c7941-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-140">xs:string</span></span>|<span data-ttu-id="c7941-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="c7941-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="c7941-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7941-142">AppDomain</span></span>|<span data-ttu-id="c7941-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7941-143">xs:string</span></span>|<span data-ttu-id="c7941-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7941-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
