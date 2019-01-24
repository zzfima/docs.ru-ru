---
title: '&lt;channelSettings&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: 0d48955c7e8f872504514c270ffe02867f507b47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731794"
---
# <a name="ltchannelsettingsgt"></a><span data-ttu-id="5d886-102">&lt;channelSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="5d886-102">&lt;channelSettings&gt;</span></span>
<span data-ttu-id="5d886-103">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="5d886-103">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="5d886-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5d886-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d886-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5d886-105">\<behaviors></span></span>  
<span data-ttu-id="5d886-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5d886-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5d886-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5d886-107">\<behavior></span></span>  
<span data-ttu-id="5d886-108">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="5d886-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="5d886-109">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="5d886-109">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d886-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d886-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d886-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5d886-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d886-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5d886-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d886-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5d886-113">Attributes</span></span>  
  
|<span data-ttu-id="5d886-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5d886-114">Attribute</span></span>|<span data-ttu-id="5d886-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5d886-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d886-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="5d886-116">idleTimeout</span></span>|<span data-ttu-id="5d886-117">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="5d886-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="5d886-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="5d886-118">leaseTimeout</span></span>|<span data-ttu-id="5d886-119">Значение TimeSpan, указывающее интервал времени, после которого объект удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="5d886-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="5d886-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="5d886-120">maxItemsInCache</span></span>|<span data-ttu-id="5d886-121">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="5d886-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d886-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5d886-122">Child Elements</span></span>  
 <span data-ttu-id="5d886-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5d886-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d886-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5d886-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5d886-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d886-125">Element</span></span>|<span data-ttu-id="5d886-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="5d886-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d886-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="5d886-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="5d886-128">Поведение службы, которое позволяет изменить совместное использование уровней, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий отправки сообщений кэша.</span><span class="sxs-lookup"><span data-stu-id="5d886-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d886-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d886-129">Remarks</span></span>  
 <span data-ttu-id="5d886-130">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="5d886-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="5d886-131">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5d886-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="5d886-132">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="5d886-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="5d886-133">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="5d886-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="5d886-134">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="5d886-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="5d886-135">Дополнительные сведения о способах изменения кэша по умолчанию, совместное использование уровни и параметры кэша для фабрики каналов и кэша каналов, см. в разделе [изменение уровней совместного использования кэша для действий отправки](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="5d886-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d886-136">Пример</span><span class="sxs-lookup"><span data-stu-id="5d886-136">Example</span></span>  
 <span data-ttu-id="5d886-137">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="5d886-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="5d886-138">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="5d886-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="5d886-139">В следующем примере показано содержимое файла конфигурации, содержащий **MyChannelCacheBehavior** поведение службы с параметрами кэша пользовательской фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="5d886-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="5d886-140">Это поведение службы добавляется к службе через **behaviorConfiguarion** атрибута.</span><span class="sxs-lookup"><span data-stu-id="5d886-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d886-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5d886-141">See also</span></span>
- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="5d886-142">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="5d886-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
