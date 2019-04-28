---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924362"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="a46dd-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="a46dd-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a46dd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a46dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a46dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="a46dd-104">ID</span></span>|<span data-ttu-id="a46dd-105">1029</span><span class="sxs-lookup"><span data-stu-id="a46dd-105">1029</span></span>|  
|<span data-ttu-id="a46dd-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a46dd-106">Keywords</span></span>|<span data-ttu-id="a46dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a46dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="a46dd-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a46dd-108">Level</span></span>|<span data-ttu-id="a46dd-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="a46dd-109">Verbose</span></span>|  
|<span data-ttu-id="a46dd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a46dd-110">Channel</span></span>|<span data-ttu-id="a46dd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a46dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a46dd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a46dd-112">Description</span></span>  
 <span data-ttu-id="a46dd-113">Указывает, что FaultWorkItem было предназначено.</span><span class="sxs-lookup"><span data-stu-id="a46dd-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a46dd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a46dd-114">Message</span></span>  
 <span data-ttu-id="a46dd-115">FaultWorkItem запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="a46dd-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="a46dd-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="a46dd-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a46dd-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a46dd-117">Details</span></span>  
  
|<span data-ttu-id="a46dd-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a46dd-118">Data Item Name</span></span>|<span data-ttu-id="a46dd-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a46dd-119">Data Item Type</span></span>|<span data-ttu-id="a46dd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a46dd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a46dd-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="a46dd-121">FaultActivity</span></span>|<span data-ttu-id="a46dd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-122">xs:string</span></span>|<span data-ttu-id="a46dd-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a46dd-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="a46dd-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a46dd-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="a46dd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-125">xs:string</span></span>|<span data-ttu-id="a46dd-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a46dd-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="a46dd-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a46dd-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="a46dd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-128">xs:string</span></span>|<span data-ttu-id="a46dd-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a46dd-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="a46dd-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="a46dd-130">ExceptionActivity</span></span>|<span data-ttu-id="a46dd-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-131">xs:string</span></span>|<span data-ttu-id="a46dd-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="a46dd-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a46dd-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a46dd-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="a46dd-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-134">xs:string</span></span>|<span data-ttu-id="a46dd-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="a46dd-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a46dd-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a46dd-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="a46dd-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-137">xs:string</span></span>|<span data-ttu-id="a46dd-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="a46dd-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a46dd-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="a46dd-139">Exception</span></span>|<span data-ttu-id="a46dd-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-140">xs:string</span></span>|<span data-ttu-id="a46dd-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="a46dd-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="a46dd-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a46dd-142">AppDomain</span></span>|<span data-ttu-id="a46dd-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="a46dd-143">xs:string</span></span>|<span data-ttu-id="a46dd-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a46dd-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
