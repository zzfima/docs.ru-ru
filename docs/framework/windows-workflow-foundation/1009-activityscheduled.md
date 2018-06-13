---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509976"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="9981e-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="9981e-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="9981e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9981e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9981e-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9981e-104">ID</span></span>|<span data-ttu-id="9981e-105">1009</span><span class="sxs-lookup"><span data-stu-id="9981e-105">1009</span></span>|  
|<span data-ttu-id="9981e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9981e-106">Keywords</span></span>|<span data-ttu-id="9981e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9981e-107">WFRuntime</span></span>|  
|<span data-ttu-id="9981e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9981e-108">Level</span></span>|<span data-ttu-id="9981e-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9981e-109">Information</span></span>|  
|<span data-ttu-id="9981e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9981e-110">Channel</span></span>|<span data-ttu-id="9981e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9981e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9981e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9981e-112">Description</span></span>  
 <span data-ttu-id="9981e-113">Указывает, что действие запланировано для выполнения.</span><span class="sxs-lookup"><span data-stu-id="9981e-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9981e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9981e-114">Message</span></span>  
 <span data-ttu-id="9981e-115">Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).</span><span class="sxs-lookup"><span data-stu-id="9981e-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9981e-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9981e-116">Details</span></span>  
  
|<span data-ttu-id="9981e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9981e-117">Data Item Name</span></span>|<span data-ttu-id="9981e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9981e-118">Data Item Type</span></span>|<span data-ttu-id="9981e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9981e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9981e-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="9981e-120">ParentActivity</span></span>|<span data-ttu-id="9981e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-121">xs:string</span></span>|<span data-ttu-id="9981e-122">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="9981e-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="9981e-123">ParentDisplayName</span></span>|<span data-ttu-id="9981e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-124">xs:string</span></span>|<span data-ttu-id="9981e-125">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="9981e-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="9981e-126">ParentInstanceId</span></span>|<span data-ttu-id="9981e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-127">xs:string</span></span>|<span data-ttu-id="9981e-128">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="9981e-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="9981e-129">ChildActivity</span></span>|<span data-ttu-id="9981e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-130">xs:string</span></span>|<span data-ttu-id="9981e-131">Имя типа запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="9981e-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="9981e-132">ChildDisplayName</span></span>|<span data-ttu-id="9981e-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-133">xs:string</span></span>|<span data-ttu-id="9981e-134">Отображаемое имя запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="9981e-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="9981e-135">ChildInstanceId</span></span>|<span data-ttu-id="9981e-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-136">xs:string</span></span>|<span data-ttu-id="9981e-137">Идентификатор экземпляра запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="9981e-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="9981e-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9981e-138">AppDomain</span></span>|<span data-ttu-id="9981e-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="9981e-139">xs:string</span></span>|<span data-ttu-id="9981e-140">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9981e-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
