---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: ffc16f78b266b69e80023f177f10ad6f367b5623
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104888"
---
# <a name="participants"></a><span data-ttu-id="02394-101">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="02394-101">\<participants></span></span>
<span data-ttu-id="02394-102">Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="02394-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="02394-103">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="02394-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="02394-104">Дополнительные сведения об отслеживании рабочих процессов и участники отслеживания, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="02394-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="02394-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="02394-105">\<system.serviceModel></span></span>  
<span data-ttu-id="02394-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="02394-106">\<tracking></span></span>  
<span data-ttu-id="02394-107">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="02394-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02394-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02394-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02394-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02394-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02394-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="02394-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02394-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02394-111">Attributes</span></span>  
 <span data-ttu-id="02394-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="02394-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02394-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02394-113">Child Elements</span></span>  
  
|<span data-ttu-id="02394-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="02394-114">Element</span></span>|<span data-ttu-id="02394-115">Описание</span><span class="sxs-lookup"><span data-stu-id="02394-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02394-116">\<add></span><span class="sxs-lookup"><span data-stu-id="02394-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="02394-117">Содержит настройки участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="02394-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02394-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02394-118">Parent Elements</span></span>  
  
|<span data-ttu-id="02394-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="02394-119">Element</span></span>|<span data-ttu-id="02394-120">Описание</span><span class="sxs-lookup"><span data-stu-id="02394-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02394-121">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="02394-121">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="02394-122">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="02394-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02394-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="02394-123">Remarks</span></span>  
 <span data-ttu-id="02394-124">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="02394-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="02394-125">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="02394-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="02394-126">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="02394-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="02394-127">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="02394-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="02394-128">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="02394-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="02394-129">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="02394-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="02394-130">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="02394-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="02394-131">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="02394-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02394-132">Пример</span><span class="sxs-lookup"><span data-stu-id="02394-132">Example</span></span>  
 <span data-ttu-id="02394-133">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="02394-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="02394-134">Идентификатор поставщика, который используется участником отслеживания ETW использует для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздел.</span><span class="sxs-lookup"><span data-stu-id="02394-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="02394-135">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="02394-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="02394-136">Это определяется **profileName** атрибут  **\<Добавить >** элемент.</span><span class="sxs-lookup"><span data-stu-id="02394-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="02394-137">После их определения участник отслеживания добавляется  **\<etwTracking >** поведение службы.</span><span class="sxs-lookup"><span data-stu-id="02394-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="02394-138">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="02394-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02394-139">См. также</span><span class="sxs-lookup"><span data-stu-id="02394-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="02394-140">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="02394-140">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="02394-141">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="02394-141">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
