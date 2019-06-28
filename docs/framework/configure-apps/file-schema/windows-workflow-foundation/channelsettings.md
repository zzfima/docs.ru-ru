---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f24efdf6e2ba99eb4fc20b81d238d33c60e6b35a
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422940"
---
# <a name="channelsettings"></a><span data-ttu-id="3dcae-101">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="3dcae-101">\<channelSettings></span></span>
<span data-ttu-id="3dcae-102">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="3dcae-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="3dcae-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3dcae-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3dcae-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="3dcae-104">\<behaviors></span></span>  
<span data-ttu-id="3dcae-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3dcae-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3dcae-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3dcae-106">\<behavior></span></span>  
<span data-ttu-id="3dcae-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="3dcae-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="3dcae-108">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="3dcae-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dcae-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3dcae-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dcae-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3dcae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3dcae-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3dcae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dcae-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3dcae-112">Attributes</span></span>  
  
|<span data-ttu-id="3dcae-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3dcae-113">Attribute</span></span>|<span data-ttu-id="3dcae-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3dcae-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dcae-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="3dcae-115">idleTimeout</span></span>|<span data-ttu-id="3dcae-116">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="3dcae-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="3dcae-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="3dcae-117">leaseTimeout</span></span>|<span data-ttu-id="3dcae-118">Значение TimeSpan, указывающее интервал времени, после которого объект удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="3dcae-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="3dcae-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="3dcae-119">maxItemsInCache</span></span>|<span data-ttu-id="3dcae-120">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="3dcae-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dcae-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3dcae-121">Child Elements</span></span>  
 <span data-ttu-id="3dcae-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3dcae-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dcae-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3dcae-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3dcae-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="3dcae-124">Element</span></span>|<span data-ttu-id="3dcae-125">Описание</span><span class="sxs-lookup"><span data-stu-id="3dcae-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dcae-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="3dcae-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="3dcae-127">Поведение службы, которое позволяет изменить совместное использование уровней, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий отправки сообщений кэша.</span><span class="sxs-lookup"><span data-stu-id="3dcae-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dcae-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="3dcae-128">Remarks</span></span>  
 <span data-ttu-id="3dcae-129">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="3dcae-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="3dcae-130">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="3dcae-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="3dcae-131">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="3dcae-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="3dcae-132">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="3dcae-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="3dcae-133">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="3dcae-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="3dcae-134">Дополнительные сведения о способах изменения кэша по умолчанию, совместное использование уровни и параметры кэша для фабрики каналов и кэша каналов, см. в разделе [изменение уровней совместного использования кэша для действий отправки](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="3dcae-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dcae-135">Пример</span><span class="sxs-lookup"><span data-stu-id="3dcae-135">Example</span></span>  
 <span data-ttu-id="3dcae-136">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="3dcae-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="3dcae-137">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="3dcae-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="3dcae-138">В следующем примере показано содержимое файла конфигурации, содержащий `MyChannelCacheBehavior` поведение службы с параметрами кэша пользовательской фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="3dcae-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="3dcae-139">Это поведение службы добавляется к службе через `behaviorConfiguration` атрибута.</span><span class="sxs-lookup"><span data-stu-id="3dcae-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3dcae-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3dcae-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="3dcae-141">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="3dcae-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
