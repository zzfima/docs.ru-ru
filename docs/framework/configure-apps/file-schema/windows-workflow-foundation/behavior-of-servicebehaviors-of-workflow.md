---
title: <behavior>из <serviceBehaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 65bde45ffdd4af166d5b44308162c23257659802
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398892"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="9b6d5-102">\<> поведения > \<serviceBehaviors рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9b6d5-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="9b6d5-103">Элемент **Behavior** содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="9b6d5-104">Каждое поведение индексируется по **имени**.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="9b6d5-105">Службы могут ссылаться на каждое поведение с помощью этого имени, используя атрибут [ \<behaviorConfiguration элемента Endpoint >](../wcf/endpoint-element.md) .</span><span class="sxs-lookup"><span data-stu-id="9b6d5-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="9b6d5-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="9b6d5-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b6d5-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b6d5-108">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b6d5-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9b6d5-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b6d5-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9b6d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b6d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9b6d5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> поведения**</span><span class="sxs-lookup"><span data-stu-id="9b6d5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6d5-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b6d5-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b6d5-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b6d5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9b6d5-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b6d5-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b6d5-115">Attributes</span></span>  
  
|<span data-ttu-id="9b6d5-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9b6d5-116">Attribute</span></span>|<span data-ttu-id="9b6d5-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6d5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b6d5-118">имя</span><span class="sxs-lookup"><span data-stu-id="9b6d5-118">name</span></span>|<span data-ttu-id="9b6d5-119">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9b6d5-120">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b6d5-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b6d5-121">Child Elements</span></span>  
  
|<span data-ttu-id="9b6d5-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b6d5-122">Element</span></span>|<span data-ttu-id="9b6d5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6d5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b6d5-124">\<Буфферрецеиве ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-124">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="9b6d5-125">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-125">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="9b6d5-126">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9b6d5-126">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="9b6d5-127">Поведение службы, которое позволяет службе использовать отслеживание ETW с помощью <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-127">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="9b6d5-128">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-128">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="9b6d5-129">Поведение службы, которое позволяет настраивать уровни совместного использования кэша, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки службы с помощью операций отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-129">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="9b6d5-130">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-130">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="9b6d5-131">Поведение службы, которое позволяет настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функцию, которая поддерживает сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-131">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="9b6d5-132">\<Воркфловидле ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-132">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="9b6d5-133">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-133">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="9b6d5-134">\<Воркфловинстанцеманажемент ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-134">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="9b6d5-135">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-135">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="9b6d5-136">\<Воркфловунхандледексцептион ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-136">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="9b6d5-137">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-137">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b6d5-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b6d5-138">Parent Elements</span></span>  
  
|<span data-ttu-id="9b6d5-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b6d5-139">Element</span></span>|<span data-ttu-id="9b6d5-140">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6d5-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b6d5-141">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9b6d5-141">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="9b6d5-142">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="9b6d5-142">A collection of service behavior elements.</span></span>|
