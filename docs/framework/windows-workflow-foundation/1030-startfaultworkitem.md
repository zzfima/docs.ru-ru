---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509684"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="ab1b9-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ab1b9-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ab1b9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ab1b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab1b9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ab1b9-104">ID</span></span>|<span data-ttu-id="ab1b9-105">1030</span><span class="sxs-lookup"><span data-stu-id="ab1b9-105">1030</span></span>|  
|<span data-ttu-id="ab1b9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ab1b9-106">Keywords</span></span>|<span data-ttu-id="ab1b9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ab1b9-107">WFRuntime</span></span>|  
|<span data-ttu-id="ab1b9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ab1b9-108">Level</span></span>|<span data-ttu-id="ab1b9-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ab1b9-109">Verbose</span></span>|  
|<span data-ttu-id="ab1b9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ab1b9-110">Channel</span></span>|<span data-ttu-id="ab1b9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ab1b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab1b9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ab1b9-112">Description</span></span>  
 <span data-ttu-id="ab1b9-113">Указывает на начало выполнения FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab1b9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ab1b9-114">Message</span></span>  
 <span data-ttu-id="ab1b9-115">Начинается выполнение элемента FaultWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="ab1b9-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ab1b9-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="ab1b9-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab1b9-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ab1b9-117">Details</span></span>  
  
|<span data-ttu-id="ab1b9-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab1b9-118">Data Item Name</span></span>|<span data-ttu-id="ab1b9-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab1b9-119">Data Item Type</span></span>|<span data-ttu-id="ab1b9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ab1b9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab1b9-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ab1b9-121">FaultActivity</span></span>|<span data-ttu-id="ab1b9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-122">xs:string</span></span>|<span data-ttu-id="ab1b9-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ab1b9-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ab1b9-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ab1b9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-125">xs:string</span></span>|<span data-ttu-id="ab1b9-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ab1b9-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ab1b9-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ab1b9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-128">xs:string</span></span>|<span data-ttu-id="ab1b9-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ab1b9-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ab1b9-130">ExceptionActivity</span></span>|<span data-ttu-id="ab1b9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-131">xs:string</span></span>|<span data-ttu-id="ab1b9-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab1b9-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ab1b9-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ab1b9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-134">xs:string</span></span>|<span data-ttu-id="ab1b9-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab1b9-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ab1b9-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ab1b9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-137">xs:string</span></span>|<span data-ttu-id="ab1b9-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab1b9-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="ab1b9-139">Exception</span></span>|<span data-ttu-id="ab1b9-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-140">xs:string</span></span>|<span data-ttu-id="ab1b9-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="ab1b9-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ab1b9-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ab1b9-142">AppDomain</span></span>|<span data-ttu-id="ab1b9-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab1b9-143">xs:string</span></span>|<span data-ttu-id="ab1b9-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ab1b9-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
