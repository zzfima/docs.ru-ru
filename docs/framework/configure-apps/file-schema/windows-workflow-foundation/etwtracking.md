---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152175"
---
# <a name="etwtracking"></a><span data-ttu-id="06671-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="06671-101">\<etwTracking></span></span>
<span data-ttu-id="06671-102">Поведение службы позволяет ей использовать отслеживание ETW совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="06671-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="06671-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="06671-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="06671-104">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="06671-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="06671-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="06671-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="06671-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="06671-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="06671-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="06671-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="06671-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span><span class="sxs-lookup"><span data-stu-id="06671-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06671-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06671-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06671-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06671-110">Attributes and Elements</span></span>  
 <span data-ttu-id="06671-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06671-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06671-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06671-112">Attributes</span></span>  
  
|<span data-ttu-id="06671-113">attribute</span><span class="sxs-lookup"><span data-stu-id="06671-113">Attribute</span></span>|<span data-ttu-id="06671-114">Описание</span><span class="sxs-lookup"><span data-stu-id="06671-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06671-115">profileName</span><span class="sxs-lookup"><span data-stu-id="06671-115">profileName</span></span>|<span data-ttu-id="06671-116">Строка, указывающая имя профиля отслеживания, связанного с этим поведением.</span><span class="sxs-lookup"><span data-stu-id="06671-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06671-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06671-117">Child Elements</span></span>  
 <span data-ttu-id="06671-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="06671-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06671-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06671-119">Parent Elements</span></span>  
  
|<span data-ttu-id="06671-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="06671-120">Element</span></span>|<span data-ttu-id="06671-121">Описание</span><span class="sxs-lookup"><span data-stu-id="06671-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06671-122">\<поведение> \<сервисовПоведение></span><span class="sxs-lookup"><span data-stu-id="06671-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="06671-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="06671-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06671-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="06671-124">Remarks</span></span>  
 <span data-ttu-id="06671-125">Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.</span><span class="sxs-lookup"><span data-stu-id="06671-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="06671-126">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="06671-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="06671-127">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="06671-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06671-128">Пример</span><span class="sxs-lookup"><span data-stu-id="06671-128">Example</span></span>  
 <span data-ttu-id="06671-129">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="06671-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="06671-130">Идентификатор поставщика, который участник отслеживания ETW использует для написания записей отслеживания для ETW, определяется в разделе \*\* \<диагностики>.\*\*</span><span class="sxs-lookup"><span data-stu-id="06671-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="06671-131">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="06671-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="06671-132">Это определяется атрибутом **profileName** \*\* \<элемента добавления>.\*\*</span><span class="sxs-lookup"><span data-stu-id="06671-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="06671-133">Как только они определены, участник отслеживания добавляется в поведение \*\* \<службы etwTracking>.\*\*</span><span class="sxs-lookup"><span data-stu-id="06671-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="06671-134">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="06671-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06671-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06671-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="06671-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="06671-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06671-137">Отслеживание участников</span><span class="sxs-lookup"><span data-stu-id="06671-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
