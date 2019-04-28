---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925090"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="53532-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="53532-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="53532-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="53532-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53532-104">ID</span><span class="sxs-lookup"><span data-stu-id="53532-104">ID</span></span>|<span data-ttu-id="53532-105">1016</span><span class="sxs-lookup"><span data-stu-id="53532-105">1016</span></span>|  
|<span data-ttu-id="53532-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="53532-106">Keywords</span></span>|<span data-ttu-id="53532-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="53532-107">WFRuntime</span></span>|  
|<span data-ttu-id="53532-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="53532-108">Level</span></span>|<span data-ttu-id="53532-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="53532-109">Verbose</span></span>|  
|<span data-ttu-id="53532-110">Канал</span><span class="sxs-lookup"><span data-stu-id="53532-110">Channel</span></span>|<span data-ttu-id="53532-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="53532-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53532-112">Описание</span><span class="sxs-lookup"><span data-stu-id="53532-112">Description</span></span>  
 <span data-ttu-id="53532-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="53532-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53532-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="53532-114">Message</span></span>  
 <span data-ttu-id="53532-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="53532-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="53532-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="53532-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53532-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="53532-117">Details</span></span>  
  
|<span data-ttu-id="53532-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="53532-118">Data Item Name</span></span>|<span data-ttu-id="53532-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="53532-119">Data Item Type</span></span>|<span data-ttu-id="53532-120">Описание</span><span class="sxs-lookup"><span data-stu-id="53532-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53532-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="53532-121">ParentActivity</span></span>|<span data-ttu-id="53532-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-122">xs:string</span></span>|<span data-ttu-id="53532-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="53532-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="53532-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="53532-124">ParentDisplayName</span></span>|<span data-ttu-id="53532-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-125">xs:string</span></span>|<span data-ttu-id="53532-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="53532-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="53532-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="53532-127">ParentInstanceId</span></span>|<span data-ttu-id="53532-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-128">xs:string</span></span>|<span data-ttu-id="53532-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="53532-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="53532-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="53532-130">CompletedActivity</span></span>|<span data-ttu-id="53532-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-131">xs:string</span></span>|<span data-ttu-id="53532-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="53532-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="53532-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="53532-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="53532-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-134">xs:string</span></span>|<span data-ttu-id="53532-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="53532-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="53532-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="53532-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="53532-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-137">xs:string</span></span>|<span data-ttu-id="53532-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="53532-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="53532-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="53532-139">AppDomain</span></span>|<span data-ttu-id="53532-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="53532-140">xs:string</span></span>|<span data-ttu-id="53532-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="53532-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
