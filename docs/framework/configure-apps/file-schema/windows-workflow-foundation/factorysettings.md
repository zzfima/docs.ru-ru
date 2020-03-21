---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: afb129407bc9dff752375f6e9fd69c728a809b37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152188"
---
# <a name="factorysettings"></a><span data-ttu-id="56fba-101">\<заводНастройки></span><span class="sxs-lookup"><span data-stu-id="56fba-101">\<factorySettings></span></span>
<span data-ttu-id="56fba-102">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="56fba-102">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="56fba-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56fba-104">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="56fba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="56fba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="56fba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="56fba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)</span></span>\
<span data-ttu-id="56fba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<заводНастройки>**</span><span class="sxs-lookup"><span data-stu-id="56fba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<factorySettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56fba-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56fba-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56fba-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56fba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="56fba-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56fba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56fba-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56fba-113">Attributes</span></span>  
  
|<span data-ttu-id="56fba-114">attribute</span><span class="sxs-lookup"><span data-stu-id="56fba-114">Attribute</span></span>|<span data-ttu-id="56fba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="56fba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56fba-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="56fba-116">idleTimeout</span></span>|<span data-ttu-id="56fba-117">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="56fba-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="56fba-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="56fba-118">leaseTimeout</span></span>|<span data-ttu-id="56fba-119">Значение TimeSpan, указывающее интервал времени, по истечении которого объект удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="56fba-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="56fba-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="56fba-120">maxItemsInCache</span></span>|<span data-ttu-id="56fba-121">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="56fba-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56fba-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56fba-122">Child Elements</span></span>  
 <span data-ttu-id="56fba-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="56fba-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56fba-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56fba-124">Parent Elements</span></span>  
  
|<span data-ttu-id="56fba-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="56fba-125">Element</span></span>|<span data-ttu-id="56fba-126">Описание</span><span class="sxs-lookup"><span data-stu-id="56fba-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56fba-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="56fba-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="56fba-128">Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="56fba-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56fba-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="56fba-129">Remarks</span></span>  
 <span data-ttu-id="56fba-130">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="56fba-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="56fba-131">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="56fba-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="56fba-132">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="56fba-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="56fba-133">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="56fba-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="56fba-134">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="56fba-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="56fba-135">Для получения дополнительной информации о том, как изменить уровни совместного использования кэша по умолчанию и настройки кэша для фабрики каналов и кэша канала, [см.](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)</span><span class="sxs-lookup"><span data-stu-id="56fba-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56fba-136">Пример</span><span class="sxs-lookup"><span data-stu-id="56fba-136">Example</span></span>  
 <span data-ttu-id="56fba-137">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="56fba-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="56fba-138">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="56fba-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="56fba-139">В следующем примере отображается содержимое `MyChannelCacheBehavior` файла конфигурации, содержащего поведение службы с настройками кэша назакази и кэша каналов.</span><span class="sxs-lookup"><span data-stu-id="56fba-139">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="56fba-140">Это поведение службы добавляется `behaviorConfiguration` в службу через атрибут.</span><span class="sxs-lookup"><span data-stu-id="56fba-140">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56fba-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="56fba-141">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="56fba-142">Изменение уровней совместного использования кэша для действий «Send»</span><span class="sxs-lookup"><span data-stu-id="56fba-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
