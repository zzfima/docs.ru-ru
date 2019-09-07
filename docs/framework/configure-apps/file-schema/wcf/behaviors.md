---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a87966f643fe46d0ef69f843dc306151ca7c18bb
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400594"
---
# <a name="behaviors"></a><span data-ttu-id="2bda4-101">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="2bda4-101">\<behaviors></span></span>
<span data-ttu-id="2bda4-102">Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="2bda4-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2bda4-103">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="2bda4-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="2bda4-104">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="2bda4-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="2bda4-105">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="2bda4-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2bda4-106">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bda4-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="2bda4-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2bda4-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2bda4-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2bda4-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2bda4-109">&nbsp;&nbsp;&nbsp;&nbsp; **\<> поведения**</span><span class="sxs-lookup"><span data-stu-id="2bda4-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bda4-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bda4-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bda4-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2bda4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2bda4-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2bda4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bda4-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2bda4-113">Attributes</span></span>  
 <span data-ttu-id="2bda4-114">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2bda4-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2bda4-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2bda4-115">Child Elements</span></span>  
  
|<span data-ttu-id="2bda4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="2bda4-116">Element</span></span>|<span data-ttu-id="2bda4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2bda4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bda4-118">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2bda4-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="2bda4-119">Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2bda4-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="2bda4-120">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2bda4-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="2bda4-121">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="2bda4-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bda4-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2bda4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2bda4-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="2bda4-123">Element</span></span>|<span data-ttu-id="2bda4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="2bda4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bda4-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2bda4-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="2bda4-126">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2bda4-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bda4-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="2bda4-127">Remarks</span></span>  
 <span data-ttu-id="2bda4-128">Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="2bda4-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="2bda4-129">Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="2bda4-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="2bda4-130">Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="2bda4-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bda4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2bda4-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="2bda4-132">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="2bda4-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="2bda4-133">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="2bda4-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="2bda4-134">Указание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="2bda4-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="2bda4-135">Указание поведения службы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="2bda4-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="2bda4-136">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="2bda4-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
