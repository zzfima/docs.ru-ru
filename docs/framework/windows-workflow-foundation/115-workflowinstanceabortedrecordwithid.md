---
title: 115 - WorkflowInstanceAbortedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0293dd4e-e6ae-473a-b3d6-c2d38f9bd875
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 314f880f1fc2d78efc59f73f37122d03ae30cf72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="115---workflowinstanceabortedrecordwithid"></a><span data-ttu-id="5c8cf-102">115 - WorkflowInstanceAbortedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="5c8cf-102">115 - WorkflowInstanceAbortedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="5c8cf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5c8cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c8cf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5c8cf-104">ID</span></span>|<span data-ttu-id="5c8cf-105">115</span><span class="sxs-lookup"><span data-stu-id="5c8cf-105">115</span></span>|  
|<span data-ttu-id="5c8cf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="5c8cf-106">Keywords</span></span>|<span data-ttu-id="5c8cf-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="5c8cf-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="5c8cf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="5c8cf-108">Level</span></span>|<span data-ttu-id="5c8cf-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="5c8cf-109">Warning</span></span>|  
|<span data-ttu-id="5c8cf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5c8cf-110">Channel</span></span>|<span data-ttu-id="5c8cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5c8cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5c8cf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8cf-112">Description</span></span>  
 <span data-ttu-id="5c8cf-113">Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceAbortedRecord.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5c8cf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5c8cf-114">Message</span></span>  
 <span data-ttu-id="5c8cf-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="5c8cf-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="5c8cf-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5c8cf-116">Details</span></span>  
  
|<span data-ttu-id="5c8cf-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5c8cf-117">Data Item Name</span></span>|<span data-ttu-id="5c8cf-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5c8cf-118">Data Item Type</span></span>|<span data-ttu-id="5c8cf-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8cf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5c8cf-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c8cf-120">InstanceId</span></span>|<span data-ttu-id="5c8cf-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="5c8cf-121">xs:GUID</span></span>|<span data-ttu-id="5c8cf-122">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="5c8cf-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="5c8cf-123">RecordNumber</span></span>|<span data-ttu-id="5c8cf-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="5c8cf-124">xs:long</span></span>|<span data-ttu-id="5c8cf-125">Порядковый номер созданной записи.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="5c8cf-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="5c8cf-126">EventTime</span></span>|<span data-ttu-id="5c8cf-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="5c8cf-127">xs:dateTime</span></span>|<span data-ttu-id="5c8cf-128">Время в формате UTC, когда было создано событие.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="5c8cf-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="5c8cf-129">ActivityDefinitionId</span></span>|<span data-ttu-id="5c8cf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-130">xs:string</span></span>|<span data-ttu-id="5c8cf-131">Имя корневого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="5c8cf-132">Состояние</span><span class="sxs-lookup"><span data-stu-id="5c8cf-132">State</span></span>|<span data-ttu-id="5c8cf-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-133">xs:string</span></span>|<span data-ttu-id="5c8cf-134">Текущее состояние рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="5c8cf-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="5c8cf-135">Annotations</span></span>|<span data-ttu-id="5c8cf-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-136">xs:string</span></span>|<span data-ttu-id="5c8cf-137">Заметки, добавленные к этому событию.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-137">The annotations that were added to this event.</span></span> <span data-ttu-id="5c8cf-138">Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="5c8cf-139">Если не задано никаких заметок, строка содержит \<элементы / >.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="5c8cf-140">Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="5c8cf-141">Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="5c8cf-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="5c8cf-142">ProfileName</span></span>|<span data-ttu-id="5c8cf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-143">xs:string</span></span>|<span data-ttu-id="5c8cf-144">Имя или профиль отслеживания, который привел к созданию этого события.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="5c8cf-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="5c8cf-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="5c8cf-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-146">xs:string</span></span>|<span data-ttu-id="5c8cf-147">Идентификатор определения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="5c8cf-147">The workflow definition id</span></span>|  
|<span data-ttu-id="5c8cf-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5c8cf-148">AppDomain</span></span>|<span data-ttu-id="5c8cf-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c8cf-149">xs:string</span></span>|<span data-ttu-id="5c8cf-150">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5c8cf-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
