---
title: '&lt;participants&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d797e216fd53a2572b6c457c1fc82f1693dce3f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltparticipantsgt-of-wcf"></a><span data-ttu-id="3670d-102">&lt;participants&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="3670d-102">&lt;participants&gt; of WCF</span></span>
<span data-ttu-id="3670d-103">Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="3670d-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="3670d-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="3670d-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="3670d-105">Дополнительные сведения об отслеживании рабочих процессов и участниках отслеживания см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="3670d-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="3670d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3670d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3670d-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="3670d-107">\<tracking></span></span>  
<span data-ttu-id="3670d-108">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="3670d-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3670d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3670d-109">Syntax</span></span>  
  
```xml
   <tracking>    <participants>       <add name="String"            profileName="String"           type="String" />    </participants> </tracking>   
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3670d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3670d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3670d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3670d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3670d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3670d-112">Attributes</span></span>  
 <span data-ttu-id="3670d-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3670d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3670d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3670d-114">Child Elements</span></span>  
  
|<span data-ttu-id="3670d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="3670d-115">Element</span></span>|<span data-ttu-id="3670d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3670d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3670d-117">\<add></span><span class="sxs-lookup"><span data-stu-id="3670d-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="3670d-118">Содержит настройки участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3670d-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3670d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3670d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3670d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3670d-120">Element</span></span>|<span data-ttu-id="3670d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3670d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3670d-122">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="3670d-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="3670d-123">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3670d-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3670d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3670d-124">Remarks</span></span>  
 <span data-ttu-id="3670d-125">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="3670d-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="3670d-126">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3670d-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="3670d-127">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="3670d-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="3670d-128">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3670d-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="3670d-129">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="3670d-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="3670d-130">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="3670d-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="3670d-131">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="3670d-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="3670d-132">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3670d-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3670d-133">Пример</span><span class="sxs-lookup"><span data-stu-id="3670d-133">Example</span></span>  
 <span data-ttu-id="3670d-134">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="3670d-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="3670d-135">Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="3670d-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="3670d-136">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="3670d-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="3670d-137">Это определяется атрибутом `profileName` элемента `<add>`.</span><span class="sxs-lookup"><span data-stu-id="3670d-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="3670d-138">После их определения участник отслеживания добавляется к поведению службы `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="3670d-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="3670d-139">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3670d-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3670d-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3670d-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 [<span data-ttu-id="3670d-141">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3670d-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3670d-142">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="3670d-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
