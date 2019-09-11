---
title: <participants>WCF
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: 35ed7a49967143838a6f74c51e77c553817bd09a
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855080"
---
# <a name="participants-of-wcf"></a><span data-ttu-id="e79ce-102">\<Участники > WCF</span><span class="sxs-lookup"><span data-stu-id="e79ce-102">\<participants> of WCF</span></span>
<span data-ttu-id="e79ce-103">Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="e79ce-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="e79ce-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="e79ce-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
<span data-ttu-id="e79ce-105">Дополнительные сведения об участниках отслеживания и отслеживания рабочих процессов см. в статье участники [отслеживания рабочих процессов и трассировки](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [отслеживания](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="e79ce-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="e79ce-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e79ce-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e79ce-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e79ce-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e79ce-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e79ce-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>  
<span data-ttu-id="e79ce-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Участники >**</span><span class="sxs-lookup"><span data-stu-id="e79ce-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79ce-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e79ce-110">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e79ce-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e79ce-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e79ce-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e79ce-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e79ce-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e79ce-113">Attributes</span></span>  
 <span data-ttu-id="e79ce-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="e79ce-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e79ce-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e79ce-115">Child Elements</span></span>  
  
|<span data-ttu-id="e79ce-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e79ce-116">Element</span></span>|<span data-ttu-id="e79ce-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e79ce-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e79ce-118">\<add></span><span class="sxs-lookup"><span data-stu-id="e79ce-118">\<add></span></span>](../windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="e79ce-119">Содержит настройки участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e79ce-119">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e79ce-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e79ce-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e79ce-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e79ce-121">Element</span></span>|<span data-ttu-id="e79ce-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e79ce-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e79ce-123">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e79ce-123">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="e79ce-124">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e79ce-124">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e79ce-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="e79ce-125">Remarks</span></span>  
 <span data-ttu-id="e79ce-126">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="e79ce-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="e79ce-127">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e79ce-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="e79ce-128">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="e79ce-128">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="e79ce-129">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e79ce-129">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="e79ce-130">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="e79ce-130">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="e79ce-131">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="e79ce-131">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="e79ce-132">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="e79ce-132">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="e79ce-133">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e79ce-133">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e79ce-134">Пример</span><span class="sxs-lookup"><span data-stu-id="e79ce-134">Example</span></span>  
 <span data-ttu-id="e79ce-135">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="e79ce-135">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="e79ce-136">Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="e79ce-136">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="e79ce-137">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="e79ce-137">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="e79ce-138">Это определяется атрибутом `profileName` элемента `<add>`.</span><span class="sxs-lookup"><span data-stu-id="e79ce-138">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="e79ce-139">После их определения участник отслеживания добавляется к поведению службы `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="e79ce-139">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="e79ce-140">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e79ce-140">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e79ce-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e79ce-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="e79ce-142">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e79ce-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e79ce-143">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="e79ce-143">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
