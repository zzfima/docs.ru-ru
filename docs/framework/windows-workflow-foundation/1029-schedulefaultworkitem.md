---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509734"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="b5d92-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b5d92-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b5d92-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b5d92-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5d92-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b5d92-104">ID</span></span>|<span data-ttu-id="b5d92-105">1029</span><span class="sxs-lookup"><span data-stu-id="b5d92-105">1029</span></span>|  
|<span data-ttu-id="b5d92-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b5d92-106">Keywords</span></span>|<span data-ttu-id="b5d92-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b5d92-107">WFRuntime</span></span>|  
|<span data-ttu-id="b5d92-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b5d92-108">Level</span></span>|<span data-ttu-id="b5d92-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b5d92-109">Verbose</span></span>|  
|<span data-ttu-id="b5d92-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b5d92-110">Channel</span></span>|<span data-ttu-id="b5d92-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b5d92-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b5d92-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b5d92-112">Description</span></span>  
 <span data-ttu-id="b5d92-113">Указывает, что FaultWorkItem было предназначено.</span><span class="sxs-lookup"><span data-stu-id="b5d92-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b5d92-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b5d92-114">Message</span></span>  
 <span data-ttu-id="b5d92-115">FaultWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="b5d92-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b5d92-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="b5d92-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b5d92-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b5d92-117">Details</span></span>  
  
|<span data-ttu-id="b5d92-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b5d92-118">Data Item Name</span></span>|<span data-ttu-id="b5d92-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b5d92-119">Data Item Type</span></span>|<span data-ttu-id="b5d92-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b5d92-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b5d92-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b5d92-121">FaultActivity</span></span>|<span data-ttu-id="b5d92-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-122">xs:string</span></span>|<span data-ttu-id="b5d92-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5d92-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b5d92-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b5d92-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b5d92-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-125">xs:string</span></span>|<span data-ttu-id="b5d92-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5d92-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b5d92-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b5d92-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b5d92-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-128">xs:string</span></span>|<span data-ttu-id="b5d92-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5d92-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b5d92-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b5d92-130">ExceptionActivity</span></span>|<span data-ttu-id="b5d92-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-131">xs:string</span></span>|<span data-ttu-id="b5d92-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="b5d92-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b5d92-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b5d92-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b5d92-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-134">xs:string</span></span>|<span data-ttu-id="b5d92-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="b5d92-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b5d92-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b5d92-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b5d92-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-137">xs:string</span></span>|<span data-ttu-id="b5d92-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="b5d92-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b5d92-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="b5d92-139">Exception</span></span>|<span data-ttu-id="b5d92-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-140">xs:string</span></span>|<span data-ttu-id="b5d92-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="b5d92-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b5d92-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b5d92-142">AppDomain</span></span>|<span data-ttu-id="b5d92-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b5d92-143">xs:string</span></span>|<span data-ttu-id="b5d92-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b5d92-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
