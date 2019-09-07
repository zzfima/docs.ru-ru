---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 094fbf95042c00287fb8dfcca28753cfe501a8d8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398760"
---
# <a name="etwtracking"></a><span data-ttu-id="6f0ca-101">\<Етвтраккинг ></span><span class="sxs-lookup"><span data-stu-id="6f0ca-101">\<etwTracking></span></span>
<span data-ttu-id="6f0ca-102">Поведение службы, которое позволяет службе использовать отслеживание ETW с помощью <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="6f0ca-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f0ca-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f0ca-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6f0ca-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="6f0ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6f0ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6f0ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6f0ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6f0ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6f0ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="6f0ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Етвтраккинг >**</span><span class="sxs-lookup"><span data-stu-id="6f0ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0ca-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f0ca-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f0ca-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6f0ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f0ca-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f0ca-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f0ca-112">Attributes</span></span>  
  
|<span data-ttu-id="6f0ca-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6f0ca-113">Attribute</span></span>|<span data-ttu-id="6f0ca-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6f0ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f0ca-115">profileName</span><span class="sxs-lookup"><span data-stu-id="6f0ca-115">profileName</span></span>|<span data-ttu-id="6f0ca-116">Строка, указывающая имя профиля отслеживания, связанного с этим поведением.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f0ca-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f0ca-117">Child Elements</span></span>  
 <span data-ttu-id="6f0ca-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f0ca-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f0ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6f0ca-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f0ca-120">Element</span></span>|<span data-ttu-id="6f0ca-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6f0ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f0ca-122">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="6f0ca-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="6f0ca-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f0ca-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f0ca-124">Remarks</span></span>  
 <span data-ttu-id="6f0ca-125">Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="6f0ca-126">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="6f0ca-127">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f0ca-128">Пример</span><span class="sxs-lookup"><span data-stu-id="6f0ca-128">Example</span></span>  
 <span data-ttu-id="6f0ca-129">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="6f0ca-130">Идентификатор поставщика, используемый участником отслеживания ETW для записи записей отслеживания в ETW, определяется в  **\<разделе > диагностики** .</span><span class="sxs-lookup"><span data-stu-id="6f0ca-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="6f0ca-131">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="6f0ca-132">Это определяется атрибутом  **\<filename элемента Add >** .</span><span class="sxs-lookup"><span data-stu-id="6f0ca-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="6f0ca-133">После того как они определены, участник отслеживания добавляется в  **\<поведение службы > етвтраккинг** .</span><span class="sxs-lookup"><span data-stu-id="6f0ca-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="6f0ca-134">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f0ca-135">См. также</span><span class="sxs-lookup"><span data-stu-id="6f0ca-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="6f0ca-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6f0ca-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6f0ca-137">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="6f0ca-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
