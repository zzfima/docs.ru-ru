---
title: <behavior>из <serviceBehaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946080"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="4a755-102">\<> поведения > \<serviceBehaviors рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4a755-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="4a755-103">Элемент **Behavior** содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="4a755-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="4a755-104">Каждое поведение индексируется по **имени**.</span><span class="sxs-lookup"><span data-stu-id="4a755-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="4a755-105">Службы могут ссылаться на каждое поведение с помощью этого имени, используя атрибут [ \<behaviorConfiguration элемента Endpoint >](../wcf/endpoint-element.md) .</span><span class="sxs-lookup"><span data-stu-id="4a755-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="4a755-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="4a755-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="4a755-107">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4a755-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="4a755-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4a755-108">\<behaviors></span></span>  
<span data-ttu-id="4a755-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4a755-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="4a755-110">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4a755-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a755-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a755-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a755-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4a755-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4a755-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4a755-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a755-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a755-114">Attributes</span></span>  
  
|<span data-ttu-id="4a755-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4a755-115">Attribute</span></span>|<span data-ttu-id="4a755-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4a755-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a755-117">имя</span><span class="sxs-lookup"><span data-stu-id="4a755-117">name</span></span>|<span data-ttu-id="4a755-118">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="4a755-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="4a755-119">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="4a755-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a755-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a755-120">Child Elements</span></span>  
  
|<span data-ttu-id="4a755-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a755-121">Element</span></span>|<span data-ttu-id="4a755-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4a755-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a755-123">\<Буфферрецеиве ></span><span class="sxs-lookup"><span data-stu-id="4a755-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="4a755-124">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4a755-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="4a755-125">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="4a755-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="4a755-126">Поведение службы, которое позволяет службе использовать отслеживание ETW с помощью <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="4a755-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="4a755-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="4a755-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="4a755-128">Поведение службы, которое позволяет настраивать уровни совместного использования кэша, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки службы с помощью операций отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="4a755-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="4a755-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="4a755-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="4a755-130">Поведение службы, которое позволяет настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функцию, которая поддерживает сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4a755-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="4a755-131">\<Воркфловидле ></span><span class="sxs-lookup"><span data-stu-id="4a755-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="4a755-132">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4a755-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="4a755-133">\<Воркфловинстанцеманажемент ></span><span class="sxs-lookup"><span data-stu-id="4a755-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="4a755-134">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="4a755-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="4a755-135">\<Воркфловунхандледексцептион ></span><span class="sxs-lookup"><span data-stu-id="4a755-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="4a755-136">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4a755-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a755-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4a755-137">Parent Elements</span></span>  
  
|<span data-ttu-id="4a755-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a755-138">Element</span></span>|<span data-ttu-id="4a755-139">Описание</span><span class="sxs-lookup"><span data-stu-id="4a755-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a755-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4a755-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="4a755-141">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="4a755-141">A collection of service behavior elements.</span></span>|
