---
title: <behavior> из <serviceBehaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 99f98cba96ed924069ee14e1459e073ca88cd2b0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422972"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="4b220-102">\<поведение > из \<serviceBehaviors > рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4b220-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="4b220-103">**Поведение** элемент содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="4b220-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="4b220-104">Каждое поведение индексируется по его **имя**.</span><span class="sxs-lookup"><span data-stu-id="4b220-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="4b220-105">Службы могут связаться с каждым поведением посредством этого имени, используя **behaviorConfiguration** атрибут [ \<конечной точки >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="4b220-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="4b220-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="4b220-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="4b220-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4b220-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b220-108">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="4b220-108">\<behaviors></span></span>  
<span data-ttu-id="4b220-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4b220-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="4b220-110">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="4b220-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b220-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b220-111">Syntax</span></span>  
  
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
                                  hostLockRenewalPeriod="TimeSpan" 
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b220-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b220-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4b220-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4b220-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b220-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b220-114">Attributes</span></span>  
  
|<span data-ttu-id="4b220-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4b220-115">Attribute</span></span>|<span data-ttu-id="4b220-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4b220-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b220-117">имя</span><span class="sxs-lookup"><span data-stu-id="4b220-117">name</span></span>|<span data-ttu-id="4b220-118">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="4b220-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="4b220-119">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="4b220-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b220-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b220-120">Child Elements</span></span>  
  
|<span data-ttu-id="4b220-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b220-121">Element</span></span>|<span data-ttu-id="4b220-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4b220-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b220-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="4b220-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="4b220-124">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4b220-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="4b220-125">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="4b220-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="4b220-126">Поведение службы позволяет ей использовать отслеживание ETW Совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="4b220-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="4b220-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="4b220-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="4b220-128">Поведение службы, которое позволяет изменить совместное использование уровней, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий отправки сообщений кэша.</span><span class="sxs-lookup"><span data-stu-id="4b220-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="4b220-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="4b220-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="4b220-130">Поведение службы, которое позволяет настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функция, которая поддерживает сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4b220-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="4b220-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="4b220-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="4b220-132">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4b220-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="4b220-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="4b220-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="4b220-134">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="4b220-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="4b220-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="4b220-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="4b220-136">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4b220-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b220-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b220-137">Parent Elements</span></span>  
  
|<span data-ttu-id="4b220-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b220-138">Element</span></span>|<span data-ttu-id="4b220-139">Описание</span><span class="sxs-lookup"><span data-stu-id="4b220-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b220-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4b220-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="4b220-141">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="4b220-141">A collection of service behavior elements.</span></span>|
