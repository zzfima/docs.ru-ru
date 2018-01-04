---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="57fe4-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="57fe4-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="57fe4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="57fe4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57fe4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="57fe4-104">ID</span></span>|<span data-ttu-id="57fe4-105">1015</span><span class="sxs-lookup"><span data-stu-id="57fe4-105">1015</span></span>|  
|<span data-ttu-id="57fe4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="57fe4-106">Keywords</span></span>|<span data-ttu-id="57fe4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="57fe4-107">WFRuntime</span></span>|  
|<span data-ttu-id="57fe4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="57fe4-108">Level</span></span>|<span data-ttu-id="57fe4-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="57fe4-109">Verbose</span></span>|  
|<span data-ttu-id="57fe4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="57fe4-110">Channel</span></span>|<span data-ttu-id="57fe4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="57fe4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57fe4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="57fe4-112">Description</span></span>  
 <span data-ttu-id="57fe4-113">Указывает, что выполнение CompletionWorkItem начинается.</span><span class="sxs-lookup"><span data-stu-id="57fe4-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57fe4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="57fe4-114">Message</span></span>  
 <span data-ttu-id="57fe4-115">Начато выполнение CompletionWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="57fe4-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="57fe4-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="57fe4-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57fe4-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="57fe4-117">Details</span></span>  
  
|<span data-ttu-id="57fe4-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="57fe4-118">Data Item Name</span></span>|<span data-ttu-id="57fe4-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="57fe4-119">Data Item Type</span></span>|<span data-ttu-id="57fe4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="57fe4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57fe4-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="57fe4-121">ParentActivity</span></span>|<span data-ttu-id="57fe4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-122">xs:string</span></span>|<span data-ttu-id="57fe4-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="57fe4-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="57fe4-124">ParentDisplayName</span></span>|<span data-ttu-id="57fe4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-125">xs:string</span></span>|<span data-ttu-id="57fe4-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="57fe4-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="57fe4-127">ParentInstanceId</span></span>|<span data-ttu-id="57fe4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-128">xs:string</span></span>|<span data-ttu-id="57fe4-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="57fe4-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="57fe4-130">CompletedActivity</span></span>|<span data-ttu-id="57fe4-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-131">xs:string</span></span>|<span data-ttu-id="57fe4-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="57fe4-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="57fe4-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="57fe4-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-134">xs:string</span></span>|<span data-ttu-id="57fe4-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="57fe4-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="57fe4-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="57fe4-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-137">xs:string</span></span>|<span data-ttu-id="57fe4-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="57fe4-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="57fe4-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57fe4-139">AppDomain</span></span>|<span data-ttu-id="57fe4-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fe4-140">xs:string</span></span>|<span data-ttu-id="57fe4-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="57fe4-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
