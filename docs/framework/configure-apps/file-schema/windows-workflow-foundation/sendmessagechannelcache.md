---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 60847f423c61b9e7f49a4a7594c965fb75354714
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140183"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="76bd9-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="76bd9-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="76bd9-102">Поведение службы, которое позволяет изменить совместное использование уровней, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий отправки сообщений кэша.</span><span class="sxs-lookup"><span data-stu-id="76bd9-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="76bd9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="76bd9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="76bd9-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="76bd9-104">\<behaviors></span></span>  
<span data-ttu-id="76bd9-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="76bd9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="76bd9-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="76bd9-106">\<behavior></span></span>  
<span data-ttu-id="76bd9-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="76bd9-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76bd9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76bd9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76bd9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76bd9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="76bd9-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76bd9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76bd9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76bd9-111">Attributes</span></span>  
  
|<span data-ttu-id="76bd9-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="76bd9-112">Attribute</span></span>|<span data-ttu-id="76bd9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="76bd9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76bd9-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="76bd9-114">allowUnsafeCaching</span></span>|<span data-ttu-id="76bd9-115">Логическое значение, указывающее, следует ли включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="76bd9-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="76bd9-116">Если служба рабочего процесса имеет пользовательские привязки или поведения, то кэширование может оказаться небезопасным (и будет отключено по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="76bd9-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="76bd9-117">Тем не менее, если вы хотите включить кэширование на значение этого свойства **true**.</span><span class="sxs-lookup"><span data-stu-id="76bd9-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76bd9-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76bd9-118">Child Elements</span></span>  
  
|<span data-ttu-id="76bd9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="76bd9-119">Element</span></span>|<span data-ttu-id="76bd9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="76bd9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76bd9-121">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="76bd9-121">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="76bd9-122">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="76bd9-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="76bd9-123">\<factorySettings ></span><span class="sxs-lookup"><span data-stu-id="76bd9-123">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="76bd9-124">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="76bd9-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76bd9-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76bd9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="76bd9-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="76bd9-126">Element</span></span>|<span data-ttu-id="76bd9-127">Описание</span><span class="sxs-lookup"><span data-stu-id="76bd9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76bd9-128">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="76bd9-128">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="76bd9-129">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="76bd9-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76bd9-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="76bd9-130">Remarks</span></span>  
 <span data-ttu-id="76bd9-131">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="76bd9-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="76bd9-132">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="76bd9-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="76bd9-133">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="76bd9-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="76bd9-134">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="76bd9-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="76bd9-135">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="76bd9-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="76bd9-136">Дополнительные сведения о способах изменения кэша по умолчанию, совместное использование уровни и параметры кэша для фабрики каналов и кэша каналов, см. в разделе [изменение уровней совместного использования кэша для действий отправки](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="76bd9-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76bd9-137">Пример</span><span class="sxs-lookup"><span data-stu-id="76bd9-137">Example</span></span>  
 <span data-ttu-id="76bd9-138">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="76bd9-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="76bd9-139">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="76bd9-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="76bd9-140">В следующем примере показано содержимое файла конфигурации, содержащий **MyChannelCacheBehavior** поведение службы с параметрами кэша пользовательской фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="76bd9-140">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="76bd9-141">Это поведение службы добавляется к службе через **behaviorConfiguarion** атрибута.</span><span class="sxs-lookup"><span data-stu-id="76bd9-141">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76bd9-142">См. также</span><span class="sxs-lookup"><span data-stu-id="76bd9-142">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="76bd9-143">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="76bd9-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
