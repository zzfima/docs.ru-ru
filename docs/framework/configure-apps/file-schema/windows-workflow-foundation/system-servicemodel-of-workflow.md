---
title: '&lt;system.serviceModel&gt; рабочего процесса'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 62047d68d559a34ead290cf18f77d032841210b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755641"
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="43148-102">&lt;system.serviceModel&gt; рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="43148-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="43148-103">В этом разделе конфигурации содержатся все элементы конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43148-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43148-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43148-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43148-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43148-105">Attributes and Elements</span></span>  
 <span data-ttu-id="43148-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43148-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43148-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43148-107">Attributes</span></span>  
 <span data-ttu-id="43148-108">Нет</span><span class="sxs-lookup"><span data-stu-id="43148-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43148-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43148-109">Child Elements</span></span>  
  
|<span data-ttu-id="43148-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="43148-110">Element</span></span>|<span data-ttu-id="43148-111">Описание</span><span class="sxs-lookup"><span data-stu-id="43148-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43148-112">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="43148-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="43148-113">В этом разделе определены **serviceBehaviors** коллекции.</span><span class="sxs-lookup"><span data-stu-id="43148-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="43148-114">Каждый элемент в коллекции определяет элементы поведения, используемые службами.</span><span class="sxs-lookup"><span data-stu-id="43148-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="43148-115">Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.</span><span class="sxs-lookup"><span data-stu-id="43148-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="43148-116">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="43148-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="43148-117">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43148-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="43148-118">Дополнительные сведения об отслеживании рабочих процессов и их конфигурации см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания для рабочего процесса](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="43148-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43148-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43148-119">Parent Elements</span></span>  
  
|<span data-ttu-id="43148-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="43148-120">Element</span></span>|<span data-ttu-id="43148-121">Описание</span><span class="sxs-lookup"><span data-stu-id="43148-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43148-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="43148-122">\<configuration></span></span>|<span data-ttu-id="43148-123">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="43148-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
