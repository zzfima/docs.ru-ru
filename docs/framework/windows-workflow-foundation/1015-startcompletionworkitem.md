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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="6af95-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="6af95-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6af95-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6af95-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6af95-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6af95-104">ID</span></span>|<span data-ttu-id="6af95-105">1015</span><span class="sxs-lookup"><span data-stu-id="6af95-105">1015</span></span>|  
|<span data-ttu-id="6af95-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6af95-106">Keywords</span></span>|<span data-ttu-id="6af95-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6af95-107">WFRuntime</span></span>|  
|<span data-ttu-id="6af95-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6af95-108">Level</span></span>|<span data-ttu-id="6af95-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="6af95-109">Verbose</span></span>|  
|<span data-ttu-id="6af95-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6af95-110">Channel</span></span>|<span data-ttu-id="6af95-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6af95-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6af95-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6af95-112">Description</span></span>  
 <span data-ttu-id="6af95-113">Указывает, что выполнение CompletionWorkItem начинается.</span><span class="sxs-lookup"><span data-stu-id="6af95-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6af95-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6af95-114">Message</span></span>  
 <span data-ttu-id="6af95-115">Начато выполнение CompletionWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="6af95-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="6af95-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="6af95-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6af95-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6af95-117">Details</span></span>  
  
|<span data-ttu-id="6af95-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6af95-118">Data Item Name</span></span>|<span data-ttu-id="6af95-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6af95-119">Data Item Type</span></span>|<span data-ttu-id="6af95-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6af95-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6af95-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="6af95-121">ParentActivity</span></span>|<span data-ttu-id="6af95-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-122">xs:string</span></span>|<span data-ttu-id="6af95-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="6af95-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="6af95-124">ParentDisplayName</span></span>|<span data-ttu-id="6af95-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-125">xs:string</span></span>|<span data-ttu-id="6af95-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="6af95-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="6af95-127">ParentInstanceId</span></span>|<span data-ttu-id="6af95-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-128">xs:string</span></span>|<span data-ttu-id="6af95-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="6af95-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="6af95-130">CompletedActivity</span></span>|<span data-ttu-id="6af95-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-131">xs:string</span></span>|<span data-ttu-id="6af95-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="6af95-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6af95-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="6af95-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-134">xs:string</span></span>|<span data-ttu-id="6af95-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="6af95-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6af95-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="6af95-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-137">xs:string</span></span>|<span data-ttu-id="6af95-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="6af95-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="6af95-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6af95-139">AppDomain</span></span>|<span data-ttu-id="6af95-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6af95-140">xs:string</span></span>|<span data-ttu-id="6af95-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6af95-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
