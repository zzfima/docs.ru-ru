---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032270"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="33c8b-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="33c8b-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="33c8b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="33c8b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33c8b-104">ID</span><span class="sxs-lookup"><span data-stu-id="33c8b-104">ID</span></span>|<span data-ttu-id="33c8b-105">1015</span><span class="sxs-lookup"><span data-stu-id="33c8b-105">1015</span></span>|  
|<span data-ttu-id="33c8b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="33c8b-106">Keywords</span></span>|<span data-ttu-id="33c8b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="33c8b-107">WFRuntime</span></span>|  
|<span data-ttu-id="33c8b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="33c8b-108">Level</span></span>|<span data-ttu-id="33c8b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="33c8b-109">Verbose</span></span>|  
|<span data-ttu-id="33c8b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="33c8b-110">Channel</span></span>|<span data-ttu-id="33c8b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="33c8b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33c8b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="33c8b-112">Description</span></span>  
 <span data-ttu-id="33c8b-113">Указывает, что выполнение CompletionWorkItem начинается.</span><span class="sxs-lookup"><span data-stu-id="33c8b-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33c8b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="33c8b-114">Message</span></span>  
 <span data-ttu-id="33c8b-115">Начато выполнение CompletionWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="33c8b-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="33c8b-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="33c8b-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33c8b-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="33c8b-117">Details</span></span>  
  
|<span data-ttu-id="33c8b-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="33c8b-118">Data Item Name</span></span>|<span data-ttu-id="33c8b-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="33c8b-119">Data Item Type</span></span>|<span data-ttu-id="33c8b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="33c8b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33c8b-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="33c8b-121">ParentActivity</span></span>|<span data-ttu-id="33c8b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-122">xs:string</span></span>|<span data-ttu-id="33c8b-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="33c8b-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="33c8b-124">ParentDisplayName</span></span>|<span data-ttu-id="33c8b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-125">xs:string</span></span>|<span data-ttu-id="33c8b-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="33c8b-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="33c8b-127">ParentInstanceId</span></span>|<span data-ttu-id="33c8b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-128">xs:string</span></span>|<span data-ttu-id="33c8b-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="33c8b-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="33c8b-130">CompletedActivity</span></span>|<span data-ttu-id="33c8b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-131">xs:string</span></span>|<span data-ttu-id="33c8b-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="33c8b-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="33c8b-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="33c8b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-134">xs:string</span></span>|<span data-ttu-id="33c8b-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="33c8b-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="33c8b-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="33c8b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-137">xs:string</span></span>|<span data-ttu-id="33c8b-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="33c8b-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="33c8b-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="33c8b-139">AppDomain</span></span>|<span data-ttu-id="33c8b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="33c8b-140">xs:string</span></span>|<span data-ttu-id="33c8b-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="33c8b-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
