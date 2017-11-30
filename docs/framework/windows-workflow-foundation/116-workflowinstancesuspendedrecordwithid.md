---
title: "116 ― WorkflowInstanceSuspendedRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6dc875721c323a48f5cc0b49e4ef0e7c167622b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a><span data-ttu-id="4b5a0-102">116 ― WorkflowInstanceSuspendedRecord</span><span class="sxs-lookup"><span data-stu-id="4b5a0-102">116 - WorkflowInstanceSuspendedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="4b5a0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4b5a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b5a0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4b5a0-104">ID</span></span>|<span data-ttu-id="4b5a0-105">116</span><span class="sxs-lookup"><span data-stu-id="4b5a0-105">116</span></span>|  
|<span data-ttu-id="4b5a0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4b5a0-106">Keywords</span></span>|<span data-ttu-id="4b5a0-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="4b5a0-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="4b5a0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4b5a0-108">Level</span></span>|<span data-ttu-id="4b5a0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="4b5a0-109">Information</span></span>|  
|<span data-ttu-id="4b5a0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4b5a0-110">Channel</span></span>|<span data-ttu-id="4b5a0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4b5a0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4b5a0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5a0-112">Description</span></span>  
 <span data-ttu-id="4b5a0-113">Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceSuspendedRecord.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4b5a0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4b5a0-114">Message</span></span>  
 <span data-ttu-id="4b5a0-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="4b5a0-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="4b5a0-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4b5a0-116">Details</span></span>  
  
|<span data-ttu-id="4b5a0-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b5a0-117">Data Item Name</span></span>|<span data-ttu-id="4b5a0-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b5a0-118">Data Item Type</span></span>|<span data-ttu-id="4b5a0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5a0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4b5a0-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4b5a0-120">InstanceId</span></span>|<span data-ttu-id="4b5a0-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="4b5a0-121">xs:GUID</span></span>|<span data-ttu-id="4b5a0-122">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4b5a0-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="4b5a0-123">RecordNumber</span></span>|<span data-ttu-id="4b5a0-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="4b5a0-124">xs:long</span></span>|<span data-ttu-id="4b5a0-125">Порядковый номер созданной записи.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="4b5a0-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="4b5a0-126">EventTime</span></span>|<span data-ttu-id="4b5a0-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="4b5a0-127">xs:dateTime</span></span>|<span data-ttu-id="4b5a0-128">Время в формате UTC, когда было создано событие.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="4b5a0-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="4b5a0-129">ActivityDefinitionId</span></span>|<span data-ttu-id="4b5a0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-130">xs:string</span></span>|<span data-ttu-id="4b5a0-131">Имя корневого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="4b5a0-132">Состояние</span><span class="sxs-lookup"><span data-stu-id="4b5a0-132">State</span></span>|<span data-ttu-id="4b5a0-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-133">xs:string</span></span>|<span data-ttu-id="4b5a0-134">Текущее состояние рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="4b5a0-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="4b5a0-135">Annotations</span></span>|<span data-ttu-id="4b5a0-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-136">xs:string</span></span>|<span data-ttu-id="4b5a0-137">Заметки, добавленные к этому событию.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-137">The annotations that were added to this event.</span></span> <span data-ttu-id="4b5a0-138">Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="4b5a0-139">Если не задано никаких заметок, строка содержит \<элементы / >.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="4b5a0-140">Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="4b5a0-141">Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="4b5a0-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="4b5a0-142">ProfileName</span></span>|<span data-ttu-id="4b5a0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-143">xs:string</span></span>|<span data-ttu-id="4b5a0-144">Имя или профиль отслеживания, который привел к созданию этого события.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="4b5a0-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="4b5a0-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="4b5a0-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-146">xs:string</span></span>|<span data-ttu-id="4b5a0-147">Идентификатор определения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4b5a0-147">The workflow definition id</span></span>|  
|<span data-ttu-id="4b5a0-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4b5a0-148">AppDomain</span></span>|<span data-ttu-id="4b5a0-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b5a0-149">xs:string</span></span>|<span data-ttu-id="4b5a0-150">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4b5a0-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
