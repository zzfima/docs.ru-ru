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
ms.openlocfilehash: 4e58156d5865f8f9c2cf6c76285458cd55e805db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="115---workflowinstanceabortedrecordwithid"></a><span data-ttu-id="07cfb-102">115 - WorkflowInstanceAbortedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="07cfb-102">115 - WorkflowInstanceAbortedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="07cfb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="07cfb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07cfb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="07cfb-104">ID</span></span>|<span data-ttu-id="07cfb-105">115</span><span class="sxs-lookup"><span data-stu-id="07cfb-105">115</span></span>|  
|<span data-ttu-id="07cfb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="07cfb-106">Keywords</span></span>|<span data-ttu-id="07cfb-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="07cfb-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="07cfb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="07cfb-108">Level</span></span>|<span data-ttu-id="07cfb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="07cfb-109">Warning</span></span>|  
|<span data-ttu-id="07cfb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="07cfb-110">Channel</span></span>|<span data-ttu-id="07cfb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="07cfb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07cfb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="07cfb-112">Description</span></span>  
 <span data-ttu-id="07cfb-113">Это событие создается участником отслеживания ETW, когда экземпляр рабочего процесса создает запись WorkflowInstanceAbortedRecord.</span><span class="sxs-lookup"><span data-stu-id="07cfb-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07cfb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="07cfb-114">Message</span></span>  
 <span data-ttu-id="07cfb-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="07cfb-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="07cfb-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="07cfb-116">Details</span></span>  
  
|<span data-ttu-id="07cfb-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="07cfb-117">Data Item Name</span></span>|<span data-ttu-id="07cfb-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="07cfb-118">Data Item Type</span></span>|<span data-ttu-id="07cfb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="07cfb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07cfb-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="07cfb-120">InstanceId</span></span>|<span data-ttu-id="07cfb-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="07cfb-121">xs:GUID</span></span>|<span data-ttu-id="07cfb-122">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07cfb-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="07cfb-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="07cfb-123">RecordNumber</span></span>|<span data-ttu-id="07cfb-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="07cfb-124">xs:long</span></span>|<span data-ttu-id="07cfb-125">Порядковый номер созданной записи.</span><span class="sxs-lookup"><span data-stu-id="07cfb-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="07cfb-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="07cfb-126">EventTime</span></span>|<span data-ttu-id="07cfb-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="07cfb-127">xs:dateTime</span></span>|<span data-ttu-id="07cfb-128">Время в формате UTC, когда было создано событие.</span><span class="sxs-lookup"><span data-stu-id="07cfb-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="07cfb-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="07cfb-129">ActivityDefinitionId</span></span>|<span data-ttu-id="07cfb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-130">xs:string</span></span>|<span data-ttu-id="07cfb-131">Имя корневого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="07cfb-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="07cfb-132">Состояние</span><span class="sxs-lookup"><span data-stu-id="07cfb-132">State</span></span>|<span data-ttu-id="07cfb-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-133">xs:string</span></span>|<span data-ttu-id="07cfb-134">Текущее состояние рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07cfb-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="07cfb-135">Заметки</span><span class="sxs-lookup"><span data-stu-id="07cfb-135">Annotations</span></span>|<span data-ttu-id="07cfb-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-136">xs:string</span></span>|<span data-ttu-id="07cfb-137">Заметки, добавленные к этому событию.</span><span class="sxs-lookup"><span data-stu-id="07cfb-137">The annotations that were added to this event.</span></span> <span data-ttu-id="07cfb-138">Значения хранятся в виде элемента xml в формате \<элементы >\< имя элемента = «annotationName» type="System.String" > annotationValue\</товар > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="07cfb-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="07cfb-139">Если не задано никаких заметок, строка содержит \<элементы / >.</span><span class="sxs-lookup"><span data-stu-id="07cfb-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="07cfb-140">Размер событий ETW ограничен размером буфера ETW или максимальным размером полезных данных для события ETW.</span><span class="sxs-lookup"><span data-stu-id="07cfb-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="07cfb-141">Если размер события превышает пределы трассировки событий Windows, то событие усекается путем отбрасывания заметок и замены значения заметок значением с \<элементы >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="07cfb-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="07cfb-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="07cfb-142">ProfileName</span></span>|<span data-ttu-id="07cfb-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-143">xs:string</span></span>|<span data-ttu-id="07cfb-144">Имя или профиль отслеживания, который привел к созданию этого события.</span><span class="sxs-lookup"><span data-stu-id="07cfb-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="07cfb-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="07cfb-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="07cfb-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-146">xs:string</span></span>|<span data-ttu-id="07cfb-147">Идентификатор определения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="07cfb-147">The workflow definition id</span></span>|  
|<span data-ttu-id="07cfb-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07cfb-148">AppDomain</span></span>|<span data-ttu-id="07cfb-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="07cfb-149">xs:string</span></span>|<span data-ttu-id="07cfb-150">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="07cfb-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
