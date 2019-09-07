---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: ac38a43b39496bdeee59a591f7b8f5bc4dd30de0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398695"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="895dd-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="895dd-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="895dd-102">Поведение службы, которое позволяет настраивать уровни совместного использования кэша, параметры кэша фабрики каналов и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки службы с помощью операций отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="895dd-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="895dd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="895dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="895dd-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="895dd-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="895dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="895dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="895dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="895dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="895dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="895dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="895dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sendMessageChannelCache >**</span><span class="sxs-lookup"><span data-stu-id="895dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="895dd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="895dd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="895dd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="895dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="895dd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="895dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="895dd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="895dd-112">Attributes</span></span>  
  
|<span data-ttu-id="895dd-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="895dd-113">Attribute</span></span>|<span data-ttu-id="895dd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="895dd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="895dd-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="895dd-115">allowUnsafeCaching</span></span>|<span data-ttu-id="895dd-116">Логическое значение, указывающее, следует ли включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="895dd-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="895dd-117">Если служба рабочего процесса имеет пользовательские привязки или поведения, то кэширование может оказаться небезопасным (и будет отключено по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="895dd-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="895dd-118">Однако если вы хотите включить кэширование, присвойте этому свойству значение **true**.</span><span class="sxs-lookup"><span data-stu-id="895dd-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="895dd-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="895dd-119">Child Elements</span></span>  
  
|<span data-ttu-id="895dd-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="895dd-120">Element</span></span>|<span data-ttu-id="895dd-121">Описание</span><span class="sxs-lookup"><span data-stu-id="895dd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="895dd-122">\<Чаннелсеттингс ></span><span class="sxs-lookup"><span data-stu-id="895dd-122">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="895dd-123">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="895dd-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="895dd-124">\<Факторисеттингс ></span><span class="sxs-lookup"><span data-stu-id="895dd-124">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="895dd-125">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="895dd-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="895dd-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="895dd-126">Parent Elements</span></span>  
  
|<span data-ttu-id="895dd-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="895dd-127">Element</span></span>|<span data-ttu-id="895dd-128">Описание</span><span class="sxs-lookup"><span data-stu-id="895dd-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="895dd-129">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="895dd-129">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="895dd-130">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="895dd-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="895dd-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="895dd-131">Remarks</span></span>  
 <span data-ttu-id="895dd-132">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="895dd-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="895dd-133">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="895dd-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="895dd-134">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="895dd-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="895dd-135">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="895dd-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="895dd-136">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="895dd-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="895dd-137">Дополнительные сведения о том, как изменить уровни общего доступа к кэшу по умолчанию и параметры кэша для фабрики каналов и кэша каналов, см. [в разделе изменение уровней общего доступа к кэшу для действий отправки](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="895dd-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="895dd-138">Пример</span><span class="sxs-lookup"><span data-stu-id="895dd-138">Example</span></span>  
 <span data-ttu-id="895dd-139">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="895dd-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="895dd-140">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="895dd-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="895dd-141">В следующем примере показано содержимое файла конфигурации, содержащего `MyChannelCacheBehavior` поведение службы с настройками кэша настраиваемой фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="895dd-141">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="895dd-142">Это поведение службы добавляется в службу с помощью `behaviorConfiguration` атрибута.</span><span class="sxs-lookup"><span data-stu-id="895dd-142">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="895dd-143">См. также</span><span class="sxs-lookup"><span data-stu-id="895dd-143">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="895dd-144">Изменение уровней совместного использования кэша для действий "Send"</span><span class="sxs-lookup"><span data-stu-id="895dd-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
