---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 653693fef92072cb1e6e23234359b765f0f18fc9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940230"
---
# <a name="etwtracking"></a><span data-ttu-id="27c6c-101">\<Етвтраккинг ></span><span class="sxs-lookup"><span data-stu-id="27c6c-101">\<etwTracking></span></span>
<span data-ttu-id="27c6c-102">Поведение службы, которое позволяет службе использовать отслеживание ETW с помощью <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="27c6c-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="27c6c-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="27c6c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="27c6c-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="27c6c-104">\<behaviors></span></span>  
<span data-ttu-id="27c6c-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="27c6c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="27c6c-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="27c6c-106">\<behavior></span></span>  
<span data-ttu-id="27c6c-107">\<Етвтраккинг ></span><span class="sxs-lookup"><span data-stu-id="27c6c-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c6c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27c6c-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27c6c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27c6c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27c6c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27c6c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c6c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27c6c-111">Attributes</span></span>  
  
|<span data-ttu-id="27c6c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27c6c-112">Attribute</span></span>|<span data-ttu-id="27c6c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="27c6c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27c6c-114">profileName</span><span class="sxs-lookup"><span data-stu-id="27c6c-114">profileName</span></span>|<span data-ttu-id="27c6c-115">Строка, указывающая имя профиля отслеживания, связанного с этим поведением.</span><span class="sxs-lookup"><span data-stu-id="27c6c-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27c6c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27c6c-116">Child Elements</span></span>  
 <span data-ttu-id="27c6c-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="27c6c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27c6c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27c6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="27c6c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="27c6c-119">Element</span></span>|<span data-ttu-id="27c6c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="27c6c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c6c-121">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="27c6c-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="27c6c-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="27c6c-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27c6c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="27c6c-123">Remarks</span></span>  
 <span data-ttu-id="27c6c-124">Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.</span><span class="sxs-lookup"><span data-stu-id="27c6c-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="27c6c-125">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="27c6c-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="27c6c-126">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="27c6c-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27c6c-127">Пример</span><span class="sxs-lookup"><span data-stu-id="27c6c-127">Example</span></span>  
 <span data-ttu-id="27c6c-128">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="27c6c-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="27c6c-129">Идентификатор поставщика, используемый участником отслеживания ETW для записи записей отслеживания в ETW, определяется в  **\<разделе > диагностики** .</span><span class="sxs-lookup"><span data-stu-id="27c6c-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="27c6c-130">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="27c6c-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="27c6c-131">Это определяется атрибутом  **\<filename элемента Add >** .</span><span class="sxs-lookup"><span data-stu-id="27c6c-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="27c6c-132">После того как они определены, участник отслеживания добавляется в  **\<поведение службы > етвтраккинг** .</span><span class="sxs-lookup"><span data-stu-id="27c6c-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="27c6c-133">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="27c6c-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27c6c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="27c6c-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="27c6c-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="27c6c-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="27c6c-136">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="27c6c-136">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
