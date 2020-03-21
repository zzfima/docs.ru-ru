---
title: <add> из <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 61832edbf7d206d6a5f7a85619eb17ebc010c193
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152363"
---
# <a name="add-of-participants"></a><span data-ttu-id="1ba79-102">\<добавить \<> участников></span><span class="sxs-lookup"><span data-stu-id="1ba79-102">\<add> of \<participants></span></span>
<span data-ttu-id="1ba79-103">Настройте участника отслеживания, который будет прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="1ba79-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="1ba79-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="1ba79-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="1ba79-105">Для получения дополнительной информации в процессе отслеживания и [отслеживания](../../../windows-workflow-foundation/tracking-participants.md)участников, [см.](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="1ba79-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="1ba79-106">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ba79-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ba79-107">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1ba79-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1ba79-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1ba79-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1ba79-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<участники>**](participants.md)</span><span class="sxs-lookup"><span data-stu-id="1ba79-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants.md)</span></span>\
<span data-ttu-id="1ba79-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="1ba79-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba79-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ba79-111">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ba79-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ba79-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1ba79-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ba79-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ba79-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ba79-114">Attributes</span></span>  
  
|<span data-ttu-id="1ba79-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ba79-115">Element</span></span>|<span data-ttu-id="1ba79-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1ba79-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ba79-117">name</span><span class="sxs-lookup"><span data-stu-id="1ba79-117">name</span></span>|<span data-ttu-id="1ba79-118">Строка, задающая имя участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="1ba79-119">profileName</span><span class="sxs-lookup"><span data-stu-id="1ba79-119">profileName</span></span>|<span data-ttu-id="1ba79-120">Строка, задающая имя профиля отслеживания, который определяет, на какие записи отслеживания подписан участник.</span><span class="sxs-lookup"><span data-stu-id="1ba79-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="1ba79-121">type</span><span class="sxs-lookup"><span data-stu-id="1ba79-121">type</span></span>|<span data-ttu-id="1ba79-122">Строка, задающая тип участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ba79-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ba79-123">Child Elements</span></span>  
 <span data-ttu-id="1ba79-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="1ba79-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ba79-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ba79-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1ba79-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ba79-126">Element</span></span>|<span data-ttu-id="1ba79-127">Описание</span><span class="sxs-lookup"><span data-stu-id="1ba79-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ba79-128">\<участники></span><span class="sxs-lookup"><span data-stu-id="1ba79-128">\<participants></span></span>](participants.md)|<span data-ttu-id="1ba79-129">Список участников отслеживания</span><span class="sxs-lookup"><span data-stu-id="1ba79-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba79-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ba79-130">Remarks</span></span>  
 <span data-ttu-id="1ba79-131">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="1ba79-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="1ba79-132">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="1ba79-133">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="1ba79-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="1ba79-134">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="1ba79-135">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="1ba79-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="1ba79-136">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="1ba79-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="1ba79-137">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="1ba79-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="1ba79-138">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ba79-139">Пример</span><span class="sxs-lookup"><span data-stu-id="1ba79-139">Example</span></span>  
 <span data-ttu-id="1ba79-140">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="1ba79-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="1ba79-141">Идентификатор поставщика, который участник отслеживания ETW использует для написания записей отслеживания для ETW, определяется в разделе \*\* \<диагностики>.\*\*</span><span class="sxs-lookup"><span data-stu-id="1ba79-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="1ba79-142">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="1ba79-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="1ba79-143">Это определяется атрибутом **profileName** \*\* \<элемента добавления>.\*\*</span><span class="sxs-lookup"><span data-stu-id="1ba79-143">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="1ba79-144">Как только они определены, участник отслеживания добавляется в поведение \*\* \<службы etwTracking>.\*\*</span><span class="sxs-lookup"><span data-stu-id="1ba79-144">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="1ba79-145">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ba79-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ba79-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ba79-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="1ba79-147">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1ba79-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ba79-148">Отслеживание участников</span><span class="sxs-lookup"><span data-stu-id="1ba79-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
