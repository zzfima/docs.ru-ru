---
title: "&lt;system.serviceModel&gt; рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 650cc0850b76cd6c855ea1f20b639752d7bef8cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="341a5-102">&lt;system.serviceModel&gt; рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="341a5-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="341a5-103">В этом разделе конфигурации содержатся все элементы конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="341a5-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="341a5-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName="String"   
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>    
     <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
     </participants>   
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="341a5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="341a5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="341a5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="341a5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="341a5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="341a5-107">Attributes</span></span>  
 <span data-ttu-id="341a5-108">Нет</span><span class="sxs-lookup"><span data-stu-id="341a5-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="341a5-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="341a5-109">Child Elements</span></span>  
  
|<span data-ttu-id="341a5-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="341a5-110">Element</span></span>|<span data-ttu-id="341a5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="341a5-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="341a5-112">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="341a5-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="341a5-113">В этом разделе определены **serviceBehaviors** коллекции.</span><span class="sxs-lookup"><span data-stu-id="341a5-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="341a5-114">Каждый элемент в коллекции определяет элементы поведения, используемые службами.</span><span class="sxs-lookup"><span data-stu-id="341a5-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="341a5-115">Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.</span><span class="sxs-lookup"><span data-stu-id="341a5-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="341a5-116">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="341a5-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="341a5-117">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="341a5-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="341a5-118">Дополнительные сведения об отслеживании рабочих процессов и их конфигурации см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания для рабочего процесса](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="341a5-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="341a5-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="341a5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="341a5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="341a5-120">Element</span></span>|<span data-ttu-id="341a5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="341a5-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="341a5-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="341a5-122">\<configuration></span></span>|<span data-ttu-id="341a5-123">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="341a5-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
