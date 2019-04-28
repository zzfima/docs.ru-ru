---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008802"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="db00e-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="db00e-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="db00e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="db00e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db00e-104">ID</span><span class="sxs-lookup"><span data-stu-id="db00e-104">ID</span></span>|<span data-ttu-id="db00e-105">1031</span><span class="sxs-lookup"><span data-stu-id="db00e-105">1031</span></span>|  
|<span data-ttu-id="db00e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="db00e-106">Keywords</span></span>|<span data-ttu-id="db00e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="db00e-107">WFRuntime</span></span>|  
|<span data-ttu-id="db00e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="db00e-108">Level</span></span>|<span data-ttu-id="db00e-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="db00e-109">Verbose</span></span>|  
|<span data-ttu-id="db00e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="db00e-110">Channel</span></span>|<span data-ttu-id="db00e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="db00e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="db00e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="db00e-112">Description</span></span>  
 <span data-ttu-id="db00e-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="db00e-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="db00e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="db00e-114">Message</span></span>  
 <span data-ttu-id="db00e-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="db00e-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="db00e-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="db00e-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="db00e-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="db00e-117">Details</span></span>  
  
|<span data-ttu-id="db00e-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="db00e-118">Data Item Name</span></span>|<span data-ttu-id="db00e-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="db00e-119">Data Item Type</span></span>|<span data-ttu-id="db00e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="db00e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="db00e-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="db00e-121">FaultActivity</span></span>|<span data-ttu-id="db00e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-122">xs:string</span></span>|<span data-ttu-id="db00e-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="db00e-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="db00e-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="db00e-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="db00e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-125">xs:string</span></span>|<span data-ttu-id="db00e-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="db00e-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="db00e-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="db00e-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="db00e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-128">xs:string</span></span>|<span data-ttu-id="db00e-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="db00e-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="db00e-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="db00e-130">ExceptionActivity</span></span>|<span data-ttu-id="db00e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-131">xs:string</span></span>|<span data-ttu-id="db00e-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="db00e-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="db00e-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="db00e-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="db00e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-134">xs:string</span></span>|<span data-ttu-id="db00e-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="db00e-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="db00e-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="db00e-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="db00e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-137">xs:string</span></span>|<span data-ttu-id="db00e-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="db00e-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="db00e-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="db00e-139">Exception</span></span>|<span data-ttu-id="db00e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-140">xs:string</span></span>|<span data-ttu-id="db00e-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="db00e-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="db00e-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="db00e-142">AppDomain</span></span>|<span data-ttu-id="db00e-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="db00e-143">xs:string</span></span>|<span data-ttu-id="db00e-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="db00e-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
