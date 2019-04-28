---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924323"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="9adaa-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="9adaa-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9adaa-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9adaa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9adaa-104">ID</span><span class="sxs-lookup"><span data-stu-id="9adaa-104">ID</span></span>|<span data-ttu-id="9adaa-105">1030</span><span class="sxs-lookup"><span data-stu-id="9adaa-105">1030</span></span>|  
|<span data-ttu-id="9adaa-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9adaa-106">Keywords</span></span>|<span data-ttu-id="9adaa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9adaa-107">WFRuntime</span></span>|  
|<span data-ttu-id="9adaa-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9adaa-108">Level</span></span>|<span data-ttu-id="9adaa-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="9adaa-109">Verbose</span></span>|  
|<span data-ttu-id="9adaa-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9adaa-110">Channel</span></span>|<span data-ttu-id="9adaa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9adaa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9adaa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9adaa-112">Description</span></span>  
 <span data-ttu-id="9adaa-113">Указывает на начало выполнения FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="9adaa-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9adaa-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9adaa-114">Message</span></span>  
 <span data-ttu-id="9adaa-115">Начато выполнение FaultWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="9adaa-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9adaa-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="9adaa-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9adaa-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9adaa-117">Details</span></span>  
  
|<span data-ttu-id="9adaa-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9adaa-118">Data Item Name</span></span>|<span data-ttu-id="9adaa-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9adaa-119">Data Item Type</span></span>|<span data-ttu-id="9adaa-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9adaa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9adaa-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="9adaa-121">FaultActivity</span></span>|<span data-ttu-id="9adaa-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-122">xs:string</span></span>|<span data-ttu-id="9adaa-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9adaa-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="9adaa-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9adaa-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="9adaa-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-125">xs:string</span></span>|<span data-ttu-id="9adaa-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9adaa-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="9adaa-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9adaa-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="9adaa-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-128">xs:string</span></span>|<span data-ttu-id="9adaa-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9adaa-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="9adaa-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="9adaa-130">ExceptionActivity</span></span>|<span data-ttu-id="9adaa-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-131">xs:string</span></span>|<span data-ttu-id="9adaa-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="9adaa-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9adaa-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9adaa-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="9adaa-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-134">xs:string</span></span>|<span data-ttu-id="9adaa-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="9adaa-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9adaa-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9adaa-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="9adaa-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-137">xs:string</span></span>|<span data-ttu-id="9adaa-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="9adaa-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9adaa-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="9adaa-139">Exception</span></span>|<span data-ttu-id="9adaa-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-140">xs:string</span></span>|<span data-ttu-id="9adaa-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="9adaa-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="9adaa-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="9adaa-142">AppDomain</span></span>|<span data-ttu-id="9adaa-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="9adaa-143">xs:string</span></span>|<span data-ttu-id="9adaa-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9adaa-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
