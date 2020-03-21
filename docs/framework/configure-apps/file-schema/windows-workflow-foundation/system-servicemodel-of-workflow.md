---
title: <system.serviceМоделирование> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151953"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="4846d-102">\<system.serviceМоделирование> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4846d-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="4846d-103">В этом разделе конфигурации содержатся все элементы конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4846d-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="4846d-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4846d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4846d-105">&nbsp;&nbsp;**\<Системы. СервисМодель>**</span><span class="sxs-lookup"><span data-stu-id="4846d-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4846d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4846d-106">Syntax</span></span>  
  
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
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4846d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4846d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4846d-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4846d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4846d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4846d-109">Attributes</span></span>  
 <span data-ttu-id="4846d-110">None</span><span class="sxs-lookup"><span data-stu-id="4846d-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4846d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4846d-111">Child Elements</span></span>  
  
|<span data-ttu-id="4846d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4846d-112">Element</span></span>|<span data-ttu-id="4846d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4846d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4846d-114">\<поведение></span><span class="sxs-lookup"><span data-stu-id="4846d-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="4846d-115">Этот раздел определяет коллекцию **serviceBehaviors.**</span><span class="sxs-lookup"><span data-stu-id="4846d-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="4846d-116">Каждый элемент в коллекции определяет элементы поведения, используемые службами.</span><span class="sxs-lookup"><span data-stu-id="4846d-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="4846d-117">Каждый элемент поведения идентифицируется по своему уникальному атрибуту **имени.**</span><span class="sxs-lookup"><span data-stu-id="4846d-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="4846d-118">\<отслеживание></span><span class="sxs-lookup"><span data-stu-id="4846d-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="4846d-119">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4846d-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="4846d-120">Для получения дополнительной информации о отслеживании рабочего процесса и [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)его конфигурации [см.](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="4846d-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4846d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4846d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4846d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="4846d-122">Element</span></span>|<span data-ttu-id="4846d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="4846d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4846d-124">\<конфигурация></span><span class="sxs-lookup"><span data-stu-id="4846d-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="4846d-125">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="4846d-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
