---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510371"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="fe797-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="fe797-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fe797-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fe797-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe797-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="fe797-104">ID</span></span>|<span data-ttu-id="fe797-105">1014</span><span class="sxs-lookup"><span data-stu-id="fe797-105">1014</span></span>|  
|<span data-ttu-id="fe797-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fe797-106">Keywords</span></span>|<span data-ttu-id="fe797-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe797-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe797-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fe797-108">Level</span></span>|<span data-ttu-id="fe797-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fe797-109">Verbose</span></span>|  
|<span data-ttu-id="fe797-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fe797-110">Channel</span></span>|<span data-ttu-id="fe797-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe797-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe797-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fe797-112">Description</span></span>  
 <span data-ttu-id="fe797-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="fe797-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe797-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fe797-114">Message</span></span>  
 <span data-ttu-id="fe797-115">CompletionWorkItem был запланирован для родительского элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="fe797-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="fe797-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="fe797-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe797-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fe797-117">Details</span></span>  
  
|<span data-ttu-id="fe797-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fe797-118">Data Item Name</span></span>|<span data-ttu-id="fe797-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fe797-119">Data Item Type</span></span>|<span data-ttu-id="fe797-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fe797-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe797-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="fe797-121">ParentActivity</span></span>|<span data-ttu-id="fe797-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-122">xs:string</span></span>|<span data-ttu-id="fe797-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="fe797-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="fe797-124">ParentDisplayName</span></span>|<span data-ttu-id="fe797-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-125">xs:string</span></span>|<span data-ttu-id="fe797-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="fe797-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="fe797-127">ParentInstanceId</span></span>|<span data-ttu-id="fe797-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-128">xs:string</span></span>|<span data-ttu-id="fe797-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="fe797-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="fe797-130">CompletedActivity</span></span>|<span data-ttu-id="fe797-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-131">xs:string</span></span>|<span data-ttu-id="fe797-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="fe797-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fe797-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="fe797-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-134">xs:string</span></span>|<span data-ttu-id="fe797-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="fe797-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fe797-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="fe797-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-137">xs:string</span></span>|<span data-ttu-id="fe797-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="fe797-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="fe797-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe797-139">AppDomain</span></span>|<span data-ttu-id="fe797-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe797-140">xs:string</span></span>|<span data-ttu-id="fe797-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fe797-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
