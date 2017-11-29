---
title: "&lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 81dfde9a4b75caeea263cc0809f450cbc0c9a5e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="fbccc-102">&lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="fbccc-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="fbccc-103">**Поведение** элемент содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="fbccc-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="fbccc-104">Каждое поведение индексируется по его **имя**.</span><span class="sxs-lookup"><span data-stu-id="fbccc-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="fbccc-105">Службы можно связать с каждым поведением посредством этого имени, используя **behaviorConfiguration**атрибут [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="fbccc-105">Services can link to each behavior through this name using the **behaviorConfiguration**attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="fbccc-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="fbccc-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="fbccc-107">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fbccc-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="fbccc-108">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="fbccc-108">\<behaviors></span></span>  
<span data-ttu-id="fbccc-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fbccc-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="fbccc-110">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fbccc-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbccc-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbccc-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  honstLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbccc-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fbccc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fbccc-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fbccc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbccc-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fbccc-114">Attributes</span></span>  
  
|<span data-ttu-id="fbccc-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fbccc-115">Attribute</span></span>|<span data-ttu-id="fbccc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="fbccc-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbccc-117">имя</span><span class="sxs-lookup"><span data-stu-id="fbccc-117">name</span></span>|<span data-ttu-id="fbccc-118">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="fbccc-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="fbccc-119">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="fbccc-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbccc-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fbccc-120">Child Elements</span></span>  
  
|<span data-ttu-id="fbccc-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbccc-121">Element</span></span>|<span data-ttu-id="fbccc-122">Описание</span><span class="sxs-lookup"><span data-stu-id="fbccc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbccc-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="fbccc-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="fbccc-124">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="fbccc-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="fbccc-125">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="fbccc-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="fbccc-126">Поведение службы, которое позволяет службе использовать с помощью отслеживания ETW <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="fbccc-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="fbccc-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="fbccc-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="fbccc-128">Поведение службы, позволяющее настройку совместное использование уровней, параметры кэша фабрики каналов и настройки кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий обмена сообщениями отправки кэша.</span><span class="sxs-lookup"><span data-stu-id="fbccc-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="fbccc-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="fbccc-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="fbccc-130">Поведение службы, можно настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функции, которая поддерживает сохранение сведений о состоянии экземплярами службы рабочего процесса в базу данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="fbccc-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="fbccc-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="fbccc-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="fbccc-132">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fbccc-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="fbccc-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="fbccc-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="fbccc-134">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="fbccc-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="fbccc-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="fbccc-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="fbccc-136">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fbccc-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fbccc-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fbccc-137">Parent Elements</span></span>  
  
|<span data-ttu-id="fbccc-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbccc-138">Element</span></span>|<span data-ttu-id="fbccc-139">Описание</span><span class="sxs-lookup"><span data-stu-id="fbccc-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbccc-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fbccc-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="fbccc-141">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="fbccc-141">A collection of service behavior elements.</span></span>|
