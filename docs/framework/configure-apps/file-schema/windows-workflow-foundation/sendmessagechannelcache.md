---
title: '&lt;sendMessageChannelCache&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 9fb68fb8ef4b1fa74a36005c80dc568e227c6473
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757727"
---
# <a name="ltsendmessagechannelcachegt"></a><span data-ttu-id="dadef-102">&lt;sendMessageChannelCache&gt;</span><span class="sxs-lookup"><span data-stu-id="dadef-102">&lt;sendMessageChannelCache&gt;</span></span>
<span data-ttu-id="dadef-103">Поведение службы, позволяющее настройку совместное использование уровней, параметры кэша фабрики каналов и настройки кэша канала для рабочих процессов, отправляющих сообщения в конечные точки службы, с помощью действий обмена сообщениями отправки кэша.</span><span class="sxs-lookup"><span data-stu-id="dadef-103">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="dadef-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dadef-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dadef-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="dadef-105">\<behaviors></span></span>  
<span data-ttu-id="dadef-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dadef-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dadef-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dadef-107">\<behavior></span></span>  
<span data-ttu-id="dadef-108">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="dadef-108">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dadef-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dadef-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dadef-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dadef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dadef-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dadef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dadef-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dadef-112">Attributes</span></span>  
  
|<span data-ttu-id="dadef-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dadef-113">Attribute</span></span>|<span data-ttu-id="dadef-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dadef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dadef-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="dadef-115">allowUnsafeCaching</span></span>|<span data-ttu-id="dadef-116">Логическое значение, указывающее, следует ли включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="dadef-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="dadef-117">Если служба рабочего процесса имеет пользовательские привязки или поведения, то кэширование может оказаться небезопасным (и будет отключено по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dadef-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="dadef-118">Тем не менее, если вы хотите включить кэширование на присвойте этому свойству значение **true**.</span><span class="sxs-lookup"><span data-stu-id="dadef-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dadef-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dadef-119">Child Elements</span></span>  
  
|<span data-ttu-id="dadef-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="dadef-120">Element</span></span>|<span data-ttu-id="dadef-121">Описание</span><span class="sxs-lookup"><span data-stu-id="dadef-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dadef-122">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="dadef-122">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="dadef-123">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="dadef-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="dadef-124">\<factorySettings ></span><span class="sxs-lookup"><span data-stu-id="dadef-124">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="dadef-125">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="dadef-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dadef-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dadef-126">Parent Elements</span></span>  
  
|<span data-ttu-id="dadef-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="dadef-127">Element</span></span>|<span data-ttu-id="dadef-128">Описание</span><span class="sxs-lookup"><span data-stu-id="dadef-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dadef-129">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dadef-129">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="dadef-130">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="dadef-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dadef-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="dadef-131">Remarks</span></span>  
 <span data-ttu-id="dadef-132">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="dadef-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="dadef-133">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="dadef-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="dadef-134">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="dadef-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="dadef-135">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="dadef-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="dadef-136">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="dadef-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="dadef-137">Дополнительные сведения о способах изменения кэша по умолчанию, уровни и параметры кэша для фабрики каналов и кэша канала для управления доступом см. в разделе [изменение уровней совместного использования кэша для действий отправки](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="dadef-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dadef-138">Пример</span><span class="sxs-lookup"><span data-stu-id="dadef-138">Example</span></span>  
 <span data-ttu-id="dadef-139">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="dadef-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="dadef-140">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="dadef-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="dadef-141">В следующем примере показано содержимое файла конфигурации, содержащий **MyChannelCacheBehavior** поведение службы с параметрами кэша пользовательской фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="dadef-141">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="dadef-142">Это поведение добавляется к службе через **behaviorConfiguarion** атрибута.</span><span class="sxs-lookup"><span data-stu-id="dadef-142">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dadef-143">См. также</span><span class="sxs-lookup"><span data-stu-id="dadef-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [<span data-ttu-id="dadef-144">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="dadef-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
