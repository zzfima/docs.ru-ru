---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982271"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="ee363-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="ee363-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ee363-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ee363-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee363-104">ID</span><span class="sxs-lookup"><span data-stu-id="ee363-104">ID</span></span>|<span data-ttu-id="ee363-105">1014</span><span class="sxs-lookup"><span data-stu-id="ee363-105">1014</span></span>|  
|<span data-ttu-id="ee363-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ee363-106">Keywords</span></span>|<span data-ttu-id="ee363-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ee363-107">WFRuntime</span></span>|  
|<span data-ttu-id="ee363-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ee363-108">Level</span></span>|<span data-ttu-id="ee363-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ee363-109">Verbose</span></span>|  
|<span data-ttu-id="ee363-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ee363-110">Channel</span></span>|<span data-ttu-id="ee363-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ee363-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee363-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ee363-112">Description</span></span>  
 <span data-ttu-id="ee363-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="ee363-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee363-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ee363-114">Message</span></span>  
 <span data-ttu-id="ee363-115">CompletionWorkItem запланирован для родительского действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="ee363-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ee363-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="ee363-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee363-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ee363-117">Details</span></span>  
  
|<span data-ttu-id="ee363-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ee363-118">Data Item Name</span></span>|<span data-ttu-id="ee363-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ee363-119">Data Item Type</span></span>|<span data-ttu-id="ee363-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ee363-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee363-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="ee363-121">ParentActivity</span></span>|<span data-ttu-id="ee363-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-122">xs:string</span></span>|<span data-ttu-id="ee363-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="ee363-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="ee363-124">ParentDisplayName</span></span>|<span data-ttu-id="ee363-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-125">xs:string</span></span>|<span data-ttu-id="ee363-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="ee363-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="ee363-127">ParentInstanceId</span></span>|<span data-ttu-id="ee363-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-128">xs:string</span></span>|<span data-ttu-id="ee363-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="ee363-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="ee363-130">CompletedActivity</span></span>|<span data-ttu-id="ee363-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-131">xs:string</span></span>|<span data-ttu-id="ee363-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="ee363-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ee363-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="ee363-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-134">xs:string</span></span>|<span data-ttu-id="ee363-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="ee363-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ee363-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="ee363-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-137">xs:string</span></span>|<span data-ttu-id="ee363-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="ee363-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="ee363-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ee363-139">AppDomain</span></span>|<span data-ttu-id="ee363-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee363-140">xs:string</span></span>|<span data-ttu-id="ee363-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ee363-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
