---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="cabaf-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="cabaf-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="cabaf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="cabaf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cabaf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="cabaf-104">ID</span></span>|<span data-ttu-id="cabaf-105">1031</span><span class="sxs-lookup"><span data-stu-id="cabaf-105">1031</span></span>|  
|<span data-ttu-id="cabaf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cabaf-106">Keywords</span></span>|<span data-ttu-id="cabaf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cabaf-107">WFRuntime</span></span>|  
|<span data-ttu-id="cabaf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="cabaf-108">Level</span></span>|<span data-ttu-id="cabaf-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="cabaf-109">Verbose</span></span>|  
|<span data-ttu-id="cabaf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="cabaf-110">Channel</span></span>|<span data-ttu-id="cabaf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cabaf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cabaf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cabaf-112">Description</span></span>  
 <span data-ttu-id="cabaf-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="cabaf-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cabaf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="cabaf-114">Message</span></span>  
 <span data-ttu-id="cabaf-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="cabaf-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="cabaf-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="cabaf-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cabaf-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="cabaf-117">Details</span></span>  
  
|<span data-ttu-id="cabaf-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="cabaf-118">Data Item Name</span></span>|<span data-ttu-id="cabaf-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="cabaf-119">Data Item Type</span></span>|<span data-ttu-id="cabaf-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cabaf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cabaf-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="cabaf-121">FaultActivity</span></span>|<span data-ttu-id="cabaf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-122">xs:string</span></span>|<span data-ttu-id="cabaf-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cabaf-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="cabaf-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="cabaf-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="cabaf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-125">xs:string</span></span>|<span data-ttu-id="cabaf-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cabaf-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="cabaf-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="cabaf-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="cabaf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-128">xs:string</span></span>|<span data-ttu-id="cabaf-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cabaf-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="cabaf-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="cabaf-130">ExceptionActivity</span></span>|<span data-ttu-id="cabaf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-131">xs:string</span></span>|<span data-ttu-id="cabaf-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="cabaf-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="cabaf-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="cabaf-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="cabaf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-134">xs:string</span></span>|<span data-ttu-id="cabaf-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="cabaf-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="cabaf-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="cabaf-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="cabaf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-137">xs:string</span></span>|<span data-ttu-id="cabaf-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="cabaf-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="cabaf-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="cabaf-139">Exception</span></span>|<span data-ttu-id="cabaf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-140">xs:string</span></span>|<span data-ttu-id="cabaf-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="cabaf-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="cabaf-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cabaf-142">AppDomain</span></span>|<span data-ttu-id="cabaf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="cabaf-143">xs:string</span></span>|<span data-ttu-id="cabaf-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cabaf-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
