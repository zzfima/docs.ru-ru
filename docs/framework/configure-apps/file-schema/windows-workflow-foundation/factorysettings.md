---
title: '&lt;factorySettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a2bd68833cd9dc7f2d19af171b20d18fad9a1bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltfactorysettingsgt"></a><span data-ttu-id="aaa84-102">&lt;factorySettings&gt;</span><span class="sxs-lookup"><span data-stu-id="aaa84-102">&lt;factorySettings&gt;</span></span>
<span data-ttu-id="aaa84-103">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="aaa84-103">Specifies the settings of the channel factory cache.</span></span>  
  
<span data-ttu-id="aaa84-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aaa84-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aaa84-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="aaa84-105">\<behaviors></span></span>  
<span data-ttu-id="aaa84-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="aaa84-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="aaa84-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="aaa84-107">\<behavior></span></span>  
<span data-ttu-id="aaa84-108">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="aaa84-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="aaa84-109">\<factorySettings ></span><span class="sxs-lookup"><span data-stu-id="aaa84-109">\<factorySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa84-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaa84-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaa84-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aaa84-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aaa84-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aaa84-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaa84-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aaa84-113">Attributes</span></span>  
  
|<span data-ttu-id="aaa84-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aaa84-114">Attribute</span></span>|<span data-ttu-id="aaa84-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aaa84-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaa84-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="aaa84-116">idleTimeout</span></span>|<span data-ttu-id="aaa84-117">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="aaa84-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="aaa84-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="aaa84-118">leaseTimeout</span></span>|<span data-ttu-id="aaa84-119">Значение TimeSpan, указывающее интервал времени, после которого объект будет удален из кэша.</span><span class="sxs-lookup"><span data-stu-id="aaa84-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="aaa84-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="aaa84-120">maxItemsInCache</span></span>|<span data-ttu-id="aaa84-121">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="aaa84-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaa84-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aaa84-122">Child Elements</span></span>  
 <span data-ttu-id="aaa84-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aaa84-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aaa84-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aaa84-124">Parent Elements</span></span>  
  
|<span data-ttu-id="aaa84-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaa84-125">Element</span></span>|<span data-ttu-id="aaa84-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="aaa84-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaa84-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="aaa84-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="aaa84-128">Поведение службы, позволяющее настройку совместное использование уровней, параметры кэша фабрики каналов и настройки кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий обмена сообщениями отправки кэша.</span><span class="sxs-lookup"><span data-stu-id="aaa84-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa84-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaa84-129">Remarks</span></span>  
 <span data-ttu-id="aaa84-130">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="aaa84-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="aaa84-131">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="aaa84-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="aaa84-132">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="aaa84-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="aaa84-133">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="aaa84-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="aaa84-134">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="aaa84-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="aaa84-135">изменить уровни доступа к кэшу по умолчанию и настройки кэша для фабрики каналов и кэша каналов см. в разделе [изменение уровней совместного использования кэша для действий отправки](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="aaa84-135"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa84-136">Пример</span><span class="sxs-lookup"><span data-stu-id="aaa84-136">Example</span></span>  
 <span data-ttu-id="aaa84-137">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="aaa84-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="aaa84-138">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="aaa84-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="aaa84-139">В следующем примере показано содержимое файла конфигурации, содержащий **MyChannelCacheBehavior** поведение службы с параметрами кэша пользовательской фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="aaa84-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="aaa84-140">Это поведение добавляется к службе через **behaviorConfiguarion** атрибута.</span><span class="sxs-lookup"><span data-stu-id="aaa84-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aaa84-141">См. также</span><span class="sxs-lookup"><span data-stu-id="aaa84-141">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [<span data-ttu-id="aaa84-142">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="aaa84-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
