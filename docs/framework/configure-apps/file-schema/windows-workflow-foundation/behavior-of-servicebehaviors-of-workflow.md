---
title: '&lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 9b16aad6138d79d3dbff4994250f05d617d54140
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45749833"
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="df028-102">&lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="df028-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="df028-103">**Поведение** элемент содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="df028-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="df028-104">Каждое поведение индексируется по его **имя**.</span><span class="sxs-lookup"><span data-stu-id="df028-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="df028-105">Службы могут связаться с каждым поведением посредством этого имени, используя **behaviorConfiguration** атрибут [ \<конечной точки >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="df028-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="df028-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="df028-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="df028-107">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="df028-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="df028-108">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="df028-108">\<behaviors></span></span>  
<span data-ttu-id="df028-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="df028-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="df028-110">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="df028-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df028-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df028-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df028-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df028-112">Attributes and Elements</span></span>  
 <span data-ttu-id="df028-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="df028-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df028-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df028-114">Attributes</span></span>  
  
|<span data-ttu-id="df028-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="df028-115">Attribute</span></span>|<span data-ttu-id="df028-116">Описание</span><span class="sxs-lookup"><span data-stu-id="df028-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df028-117">имя</span><span class="sxs-lookup"><span data-stu-id="df028-117">name</span></span>|<span data-ttu-id="df028-118">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="df028-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="df028-119">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="df028-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df028-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df028-120">Child Elements</span></span>  
  
|<span data-ttu-id="df028-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="df028-121">Element</span></span>|<span data-ttu-id="df028-122">Описание</span><span class="sxs-lookup"><span data-stu-id="df028-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df028-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="df028-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="df028-124">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="df028-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="df028-125">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="df028-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="df028-126">Поведение службы позволяет ей использовать отслеживание ETW Совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="df028-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="df028-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="df028-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="df028-128">Поведение службы, которое позволяет изменить совместное использование уровней, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий отправки сообщений кэша.</span><span class="sxs-lookup"><span data-stu-id="df028-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="df028-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="df028-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="df028-130">Поведение службы, которое позволяет настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функция, которая поддерживает сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="df028-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="df028-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="df028-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="df028-132">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="df028-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="df028-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="df028-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="df028-134">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="df028-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="df028-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="df028-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="df028-136">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="df028-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df028-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df028-137">Parent Elements</span></span>  
  
|<span data-ttu-id="df028-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="df028-138">Element</span></span>|<span data-ttu-id="df028-139">Описание</span><span class="sxs-lookup"><span data-stu-id="df028-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df028-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="df028-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="df028-141">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="df028-141">A collection of service behavior elements.</span></span>|
