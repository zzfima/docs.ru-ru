---
title: <add> для WCF
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 76197120096329d0eb42121f5740a87c4f42318b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281558"
---
# <a name="add-of-wcf"></a><span data-ttu-id="fc644-102">\<Добавить > из WCF</span><span class="sxs-lookup"><span data-stu-id="fc644-102">\<add> of WCF</span></span>
<span data-ttu-id="fc644-103">Настройте участника отслеживания, который будет прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="fc644-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="fc644-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="fc644-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="fc644-105">Дополнительные сведения об отслеживании рабочих процессов и участники отслеживания, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="fc644-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="fc644-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fc644-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fc644-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="fc644-107">\<tracking></span></span>  
<span data-ttu-id="fc644-108">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="fc644-108">\<participants></span></span>  
<span data-ttu-id="fc644-109">\<add></span><span class="sxs-lookup"><span data-stu-id="fc644-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc644-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc644-110">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc644-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc644-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fc644-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc644-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc644-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc644-113">Attributes</span></span>  
  
|<span data-ttu-id="fc644-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc644-114">Element</span></span>|<span data-ttu-id="fc644-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fc644-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc644-116">имя</span><span class="sxs-lookup"><span data-stu-id="fc644-116">name</span></span>|<span data-ttu-id="fc644-117">Строка, задающая имя участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="fc644-118">profileName</span><span class="sxs-lookup"><span data-stu-id="fc644-118">profileName</span></span>|<span data-ttu-id="fc644-119">Строка, задающая имя профиля отслеживания, который определяет, на какие записи отслеживания подписан участник.</span><span class="sxs-lookup"><span data-stu-id="fc644-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="fc644-120">тип</span><span class="sxs-lookup"><span data-stu-id="fc644-120">type</span></span>|<span data-ttu-id="fc644-121">Строка, задающая тип участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc644-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc644-122">Child Elements</span></span>  
 <span data-ttu-id="fc644-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fc644-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc644-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc644-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fc644-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc644-125">Element</span></span>|<span data-ttu-id="fc644-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="fc644-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc644-127">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="fc644-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="fc644-128">Список участников отслеживания</span><span class="sxs-lookup"><span data-stu-id="fc644-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc644-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc644-129">Remarks</span></span>  
 <span data-ttu-id="fc644-130">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="fc644-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="fc644-131">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="fc644-132">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="fc644-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="fc644-133">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="fc644-134">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="fc644-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="fc644-135">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="fc644-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="fc644-136">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="fc644-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="fc644-137">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc644-138">Пример</span><span class="sxs-lookup"><span data-stu-id="fc644-138">Example</span></span>  
 <span data-ttu-id="fc644-139">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="fc644-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="fc644-140">Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="fc644-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="fc644-141">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="fc644-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="fc644-142">Это определяется атрибутом `profileName` элемента `<add>`.</span><span class="sxs-lookup"><span data-stu-id="fc644-142">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="fc644-143">После их определения участник отслеживания добавляется к поведению службы `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="fc644-143">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="fc644-144">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fc644-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc644-145">См. также</span><span class="sxs-lookup"><span data-stu-id="fc644-145">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="fc644-146">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="fc644-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fc644-147">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="fc644-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
