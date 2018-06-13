---
title: '&lt;Участники&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: d5ce06a535283a7789419fb9d87433a45e37fa81
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757038"
---
# <a name="ltparticipantsgt"></a><span data-ttu-id="2c074-102">&lt;Участники&gt;</span><span class="sxs-lookup"><span data-stu-id="2c074-102">&lt;participants&gt;</span></span>
<span data-ttu-id="2c074-103">Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="2c074-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="2c074-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="2c074-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="2c074-105">Дополнительные сведения об отслеживании рабочих процессов и участниках отслеживания см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="2c074-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="2c074-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2c074-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2c074-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2c074-107">\<tracking></span></span>  
<span data-ttu-id="2c074-108">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="2c074-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c074-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c074-109">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c074-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c074-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c074-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c074-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c074-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c074-112">Attributes</span></span>  
 <span data-ttu-id="2c074-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2c074-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c074-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c074-114">Child Elements</span></span>  
  
|<span data-ttu-id="2c074-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c074-115">Element</span></span>|<span data-ttu-id="2c074-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2c074-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c074-117">\<add></span><span class="sxs-lookup"><span data-stu-id="2c074-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="2c074-118">Содержит настройки участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2c074-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c074-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c074-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2c074-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c074-120">Element</span></span>|<span data-ttu-id="2c074-121">Описание</span><span class="sxs-lookup"><span data-stu-id="2c074-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c074-122">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2c074-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="2c074-123">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2c074-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c074-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c074-124">Remarks</span></span>  
 <span data-ttu-id="2c074-125">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="2c074-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="2c074-126">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2c074-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="2c074-127">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="2c074-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="2c074-128">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2c074-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="2c074-129">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="2c074-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="2c074-130">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="2c074-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="2c074-131">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="2c074-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="2c074-132">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2c074-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c074-133">Пример</span><span class="sxs-lookup"><span data-stu-id="2c074-133">Example</span></span>  
 <span data-ttu-id="2c074-134">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="2c074-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="2c074-135">Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздела.</span><span class="sxs-lookup"><span data-stu-id="2c074-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="2c074-136">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="2c074-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="2c074-137">Это определяется **profileName** атрибут  **\<Добавить >** элемента.</span><span class="sxs-lookup"><span data-stu-id="2c074-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="2c074-138">После их определения участник отслеживания добавляется к  **\<etwTracking >** поведение службы.</span><span class="sxs-lookup"><span data-stu-id="2c074-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="2c074-139">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2c074-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c074-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2c074-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [<span data-ttu-id="2c074-141">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2c074-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2c074-142">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="2c074-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
