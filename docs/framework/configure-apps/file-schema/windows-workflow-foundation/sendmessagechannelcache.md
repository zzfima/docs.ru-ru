---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: b68c6d2e526eb22328806558d7c167b7f2ed0820
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152005"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="44977-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="44977-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="44977-102">Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="44977-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="44977-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44977-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44977-104">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="44977-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="44977-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="44977-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="44977-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="44977-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="44977-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="44977-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="44977-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span><span class="sxs-lookup"><span data-stu-id="44977-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44977-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44977-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44977-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44977-110">Attributes and Elements</span></span>  
 <span data-ttu-id="44977-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44977-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44977-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44977-112">Attributes</span></span>  
  
|<span data-ttu-id="44977-113">attribute</span><span class="sxs-lookup"><span data-stu-id="44977-113">Attribute</span></span>|<span data-ttu-id="44977-114">Описание</span><span class="sxs-lookup"><span data-stu-id="44977-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44977-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="44977-115">allowUnsafeCaching</span></span>|<span data-ttu-id="44977-116">Логическое значение, указывающее, следует ли включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="44977-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="44977-117">Если служба рабочего процесса имеет пользовательские привязки или поведения, то кэширование может оказаться небезопасным (и будет отключено по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="44977-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="44977-118">Однако, если вы хотите превратить кэширование на набор этого свойства к **истине.**</span><span class="sxs-lookup"><span data-stu-id="44977-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44977-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44977-119">Child Elements</span></span>  
  
|<span data-ttu-id="44977-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="44977-120">Element</span></span>|<span data-ttu-id="44977-121">Описание</span><span class="sxs-lookup"><span data-stu-id="44977-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44977-122">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="44977-122">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="44977-123">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="44977-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="44977-124">\<заводНастройки></span><span class="sxs-lookup"><span data-stu-id="44977-124">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="44977-125">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="44977-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44977-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44977-126">Parent Elements</span></span>  
  
|<span data-ttu-id="44977-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="44977-127">Element</span></span>|<span data-ttu-id="44977-128">Описание</span><span class="sxs-lookup"><span data-stu-id="44977-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44977-129">\<поведение> \<сервисовПоведение></span><span class="sxs-lookup"><span data-stu-id="44977-129">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="44977-130">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="44977-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44977-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="44977-131">Remarks</span></span>  
 <span data-ttu-id="44977-132">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="44977-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="44977-133">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="44977-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="44977-134">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="44977-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="44977-135">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="44977-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="44977-136">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="44977-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="44977-137">Для получения дополнительной информации о том, как изменить уровни совместного использования кэша по умолчанию и настройки кэша для фабрики каналов и кэша канала, [см.](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)</span><span class="sxs-lookup"><span data-stu-id="44977-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44977-138">Пример</span><span class="sxs-lookup"><span data-stu-id="44977-138">Example</span></span>  
 <span data-ttu-id="44977-139">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="44977-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="44977-140">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="44977-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="44977-141">В следующем примере отображается содержимое `MyChannelCacheBehavior` файла конфигурации, содержащего поведение службы с настройками кэша назакази и кэша каналов.</span><span class="sxs-lookup"><span data-stu-id="44977-141">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="44977-142">Это поведение службы добавляется `behaviorConfiguration` в службу через атрибут.</span><span class="sxs-lookup"><span data-stu-id="44977-142">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44977-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="44977-143">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="44977-144">Изменение уровней совместного использования кэша для действий «Send»</span><span class="sxs-lookup"><span data-stu-id="44977-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
