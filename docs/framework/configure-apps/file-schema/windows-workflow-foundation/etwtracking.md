---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 12589ab7c6cb65618a5f53a3e4be49d85a2ffbb7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358968"
---
# <a name="etwtracking"></a><span data-ttu-id="d26c8-101">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="d26c8-101">\<etwTracking></span></span>
<span data-ttu-id="d26c8-102">Поведение службы позволяет ей использовать отслеживание ETW Совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="d26c8-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="d26c8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d26c8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d26c8-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="d26c8-104">\<behaviors></span></span>  
<span data-ttu-id="d26c8-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d26c8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="d26c8-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d26c8-106">\<behavior></span></span>  
<span data-ttu-id="d26c8-107">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="d26c8-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26c8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d26c8-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d26c8-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d26c8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d26c8-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d26c8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d26c8-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d26c8-111">Attributes</span></span>  
  
|<span data-ttu-id="d26c8-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d26c8-112">Attribute</span></span>|<span data-ttu-id="d26c8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d26c8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d26c8-114">profileName</span><span class="sxs-lookup"><span data-stu-id="d26c8-114">profileName</span></span>|<span data-ttu-id="d26c8-115">Строка, указывающая имя профиля отслеживания, связанного с этим поведением.</span><span class="sxs-lookup"><span data-stu-id="d26c8-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d26c8-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d26c8-116">Child Elements</span></span>  
 <span data-ttu-id="d26c8-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d26c8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d26c8-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d26c8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d26c8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="d26c8-119">Element</span></span>|<span data-ttu-id="d26c8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d26c8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d26c8-121">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d26c8-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d26c8-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="d26c8-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d26c8-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="d26c8-123">Remarks</span></span>  
 <span data-ttu-id="d26c8-124">Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d26c8-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="d26c8-125">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="d26c8-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="d26c8-126">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d26c8-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d26c8-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d26c8-127">Example</span></span>  
 <span data-ttu-id="d26c8-128">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="d26c8-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="d26c8-129">Идентификатор поставщика, который используется участником отслеживания ETW использует для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздел.</span><span class="sxs-lookup"><span data-stu-id="d26c8-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="d26c8-130">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="d26c8-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="d26c8-131">Это определяется **profileName** атрибут  **\<Добавить >** элемент.</span><span class="sxs-lookup"><span data-stu-id="d26c8-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="d26c8-132">После их определения участник отслеживания добавляется  **\<etwTracking >** поведение службы.</span><span class="sxs-lookup"><span data-stu-id="d26c8-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="d26c8-133">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d26c8-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d26c8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d26c8-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="d26c8-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d26c8-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d26c8-136">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="d26c8-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
