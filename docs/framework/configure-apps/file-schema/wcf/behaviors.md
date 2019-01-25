---
title: '&lt;Поведения&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a6786efb289ee66da3f0635e1a86e23f9b7302d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528437"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="e5a06-102">&lt;Поведения&gt;</span><span class="sxs-lookup"><span data-stu-id="e5a06-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="e5a06-103">Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="e5a06-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="e5a06-104">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="e5a06-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="e5a06-105">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="e5a06-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="e5a06-106">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="e5a06-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e5a06-107">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5a06-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="e5a06-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5a06-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a06-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5a06-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a06-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5a06-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5a06-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5a06-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a06-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5a06-112">Attributes</span></span>  
 <span data-ttu-id="e5a06-113">Нет</span><span class="sxs-lookup"><span data-stu-id="e5a06-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5a06-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5a06-114">Child Elements</span></span>  
  
|<span data-ttu-id="e5a06-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5a06-115">Element</span></span>|<span data-ttu-id="e5a06-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="e5a06-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a06-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e5a06-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="e5a06-118">Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5a06-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="e5a06-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e5a06-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="e5a06-120">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="e5a06-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a06-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5a06-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a06-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5a06-122">Element</span></span>|<span data-ttu-id="e5a06-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="e5a06-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a06-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e5a06-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="e5a06-125">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e5a06-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a06-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5a06-126">Remarks</span></span>  
 <span data-ttu-id="e5a06-127">Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="e5a06-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="e5a06-128">Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="e5a06-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="e5a06-129">Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e5a06-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a06-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e5a06-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="e5a06-131">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="e5a06-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="e5a06-132">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="e5a06-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="e5a06-133">Указание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e5a06-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="e5a06-134">Указание поведения службы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e5a06-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="e5a06-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="e5a06-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
