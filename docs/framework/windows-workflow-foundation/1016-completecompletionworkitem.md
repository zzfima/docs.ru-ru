---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510300"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="64032-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="64032-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="64032-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="64032-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64032-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="64032-104">ID</span></span>|<span data-ttu-id="64032-105">1016</span><span class="sxs-lookup"><span data-stu-id="64032-105">1016</span></span>|  
|<span data-ttu-id="64032-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="64032-106">Keywords</span></span>|<span data-ttu-id="64032-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="64032-107">WFRuntime</span></span>|  
|<span data-ttu-id="64032-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="64032-108">Level</span></span>|<span data-ttu-id="64032-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="64032-109">Verbose</span></span>|  
|<span data-ttu-id="64032-110">Канал</span><span class="sxs-lookup"><span data-stu-id="64032-110">Channel</span></span>|<span data-ttu-id="64032-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="64032-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="64032-112">Описание</span><span class="sxs-lookup"><span data-stu-id="64032-112">Description</span></span>  
 <span data-ttu-id="64032-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="64032-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="64032-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="64032-114">Message</span></span>  
 <span data-ttu-id="64032-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="64032-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="64032-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="64032-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="64032-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="64032-117">Details</span></span>  
  
|<span data-ttu-id="64032-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="64032-118">Data Item Name</span></span>|<span data-ttu-id="64032-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="64032-119">Data Item Type</span></span>|<span data-ttu-id="64032-120">Описание</span><span class="sxs-lookup"><span data-stu-id="64032-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="64032-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="64032-121">ParentActivity</span></span>|<span data-ttu-id="64032-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-122">xs:string</span></span>|<span data-ttu-id="64032-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="64032-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="64032-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="64032-124">ParentDisplayName</span></span>|<span data-ttu-id="64032-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-125">xs:string</span></span>|<span data-ttu-id="64032-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="64032-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="64032-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="64032-127">ParentInstanceId</span></span>|<span data-ttu-id="64032-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-128">xs:string</span></span>|<span data-ttu-id="64032-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="64032-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="64032-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="64032-130">CompletedActivity</span></span>|<span data-ttu-id="64032-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-131">xs:string</span></span>|<span data-ttu-id="64032-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="64032-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="64032-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="64032-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="64032-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-134">xs:string</span></span>|<span data-ttu-id="64032-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="64032-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="64032-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="64032-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="64032-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-137">xs:string</span></span>|<span data-ttu-id="64032-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="64032-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="64032-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="64032-139">AppDomain</span></span>|<span data-ttu-id="64032-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="64032-140">xs:string</span></span>|<span data-ttu-id="64032-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="64032-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
