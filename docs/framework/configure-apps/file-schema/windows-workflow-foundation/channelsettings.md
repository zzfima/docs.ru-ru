---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: 9caf87bdf2029d273a9d6d7ac90b83ba72bafc7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945841"
---
# <a name="channelsettings"></a><span data-ttu-id="1df41-101">\<Чаннелсеттингс ></span><span class="sxs-lookup"><span data-stu-id="1df41-101">\<channelSettings></span></span>
<span data-ttu-id="1df41-102">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="1df41-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="1df41-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1df41-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1df41-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1df41-104">\<behaviors></span></span>  
<span data-ttu-id="1df41-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1df41-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1df41-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1df41-106">\<behavior></span></span>  
<span data-ttu-id="1df41-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="1df41-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="1df41-108">\<Чаннелсеттингс ></span><span class="sxs-lookup"><span data-stu-id="1df41-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df41-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1df41-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1df41-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1df41-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1df41-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1df41-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1df41-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1df41-112">Attributes</span></span>  
  
|<span data-ttu-id="1df41-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1df41-113">Attribute</span></span>|<span data-ttu-id="1df41-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1df41-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1df41-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="1df41-115">idleTimeout</span></span>|<span data-ttu-id="1df41-116">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="1df41-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="1df41-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="1df41-117">leaseTimeout</span></span>|<span data-ttu-id="1df41-118">Значение TimeSpan, указывающее интервал времени, по истечении которого объект удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="1df41-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="1df41-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="1df41-119">maxItemsInCache</span></span>|<span data-ttu-id="1df41-120">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="1df41-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1df41-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1df41-121">Child Elements</span></span>  
 <span data-ttu-id="1df41-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="1df41-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1df41-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1df41-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1df41-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1df41-124">Element</span></span>|<span data-ttu-id="1df41-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1df41-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1df41-126">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="1df41-126">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="1df41-127">Поведение службы, которое позволяет настраивать уровни совместного использования кэша, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки службы с помощью операций отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="1df41-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1df41-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="1df41-128">Remarks</span></span>  
 <span data-ttu-id="1df41-129">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="1df41-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="1df41-130">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1df41-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="1df41-131">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="1df41-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="1df41-132">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="1df41-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="1df41-133">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="1df41-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="1df41-134">Дополнительные сведения о том, как изменить уровни общего доступа к кэшу по умолчанию и параметры кэша для фабрики каналов и кэша каналов, см. [в разделе изменение уровней общего доступа к кэшу для действий отправки](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="1df41-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1df41-135">Пример</span><span class="sxs-lookup"><span data-stu-id="1df41-135">Example</span></span>  
 <span data-ttu-id="1df41-136">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="1df41-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="1df41-137">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="1df41-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="1df41-138">В следующем примере показано содержимое файла конфигурации, содержащего `MyChannelCacheBehavior` поведение службы с настройками кэша настраиваемой фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="1df41-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="1df41-139">Это поведение службы добавляется в службу с помощью `behaviorConfiguration` атрибута.</span><span class="sxs-lookup"><span data-stu-id="1df41-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1df41-140">См. также</span><span class="sxs-lookup"><span data-stu-id="1df41-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="1df41-141">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="1df41-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
