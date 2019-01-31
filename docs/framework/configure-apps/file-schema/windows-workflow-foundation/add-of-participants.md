---
title: <add> из <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 65b8a34250a22da79e900f6bee894b501c5ad6ba
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284548"
---
# <a name="add-of-participants"></a><span data-ttu-id="30ed2-102">\<Добавить > из \<участников ></span><span class="sxs-lookup"><span data-stu-id="30ed2-102">\<add> of \<participants></span></span>
<span data-ttu-id="30ed2-103">Настройте участника отслеживания, который будет прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="30ed2-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="30ed2-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="30ed2-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="30ed2-105">Дополнительные сведения об отслеживании рабочих процессов и участники отслеживания, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="30ed2-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="30ed2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="30ed2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="30ed2-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="30ed2-107">\<tracking></span></span>  
<span data-ttu-id="30ed2-108">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="30ed2-108">\<participants></span></span>  
<span data-ttu-id="30ed2-109">\<add></span><span class="sxs-lookup"><span data-stu-id="30ed2-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ed2-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30ed2-110">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30ed2-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="30ed2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="30ed2-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="30ed2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30ed2-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30ed2-113">Attributes</span></span>  
  
|<span data-ttu-id="30ed2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="30ed2-114">Element</span></span>|<span data-ttu-id="30ed2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="30ed2-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30ed2-116">имя</span><span class="sxs-lookup"><span data-stu-id="30ed2-116">name</span></span>|<span data-ttu-id="30ed2-117">Строка, задающая имя участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="30ed2-118">profileName</span><span class="sxs-lookup"><span data-stu-id="30ed2-118">profileName</span></span>|<span data-ttu-id="30ed2-119">Строка, задающая имя профиля отслеживания, который определяет, на какие записи отслеживания подписан участник.</span><span class="sxs-lookup"><span data-stu-id="30ed2-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="30ed2-120">тип</span><span class="sxs-lookup"><span data-stu-id="30ed2-120">type</span></span>|<span data-ttu-id="30ed2-121">Строка, задающая тип участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30ed2-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30ed2-122">Child Elements</span></span>  
 <span data-ttu-id="30ed2-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="30ed2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30ed2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="30ed2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="30ed2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="30ed2-125">Element</span></span>|<span data-ttu-id="30ed2-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="30ed2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30ed2-127">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="30ed2-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="30ed2-128">Список участников отслеживания</span><span class="sxs-lookup"><span data-stu-id="30ed2-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30ed2-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="30ed2-129">Remarks</span></span>  
 <span data-ttu-id="30ed2-130">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="30ed2-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="30ed2-131">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="30ed2-132">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="30ed2-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="30ed2-133">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="30ed2-134">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="30ed2-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="30ed2-135">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="30ed2-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="30ed2-136">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="30ed2-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="30ed2-137">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ed2-138">Пример</span><span class="sxs-lookup"><span data-stu-id="30ed2-138">Example</span></span>  
 <span data-ttu-id="30ed2-139">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="30ed2-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="30ed2-140">Идентификатор поставщика, который используется участником отслеживания ETW использует для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздел.</span><span class="sxs-lookup"><span data-stu-id="30ed2-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="30ed2-141">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="30ed2-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="30ed2-142">Это определяется **profileName** атрибут  **\<Добавить >** элемент.</span><span class="sxs-lookup"><span data-stu-id="30ed2-142">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="30ed2-143">После их определения участник отслеживания добавляется  **\<etwTracking >** поведение службы.</span><span class="sxs-lookup"><span data-stu-id="30ed2-143">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="30ed2-144">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30ed2-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30ed2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="30ed2-145">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="30ed2-146">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="30ed2-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="30ed2-147">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="30ed2-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
