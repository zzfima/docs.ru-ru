---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 8fcb5ac0c552d1ac2e849c95a5c0757d0c142f3d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926397"
---
# <a name="behaviors"></a><span data-ttu-id="f83ef-101">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="f83ef-101">\<behaviors></span></span>
<span data-ttu-id="f83ef-102">Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="f83ef-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="f83ef-103">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="f83ef-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="f83ef-104">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="f83ef-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="f83ef-105">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="f83ef-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f83ef-106">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f83ef-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="f83ef-107">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f83ef-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83ef-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f83ef-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f83ef-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f83ef-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f83ef-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f83ef-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f83ef-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f83ef-111">Attributes</span></span>  
 <span data-ttu-id="f83ef-112">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f83ef-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f83ef-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f83ef-113">Child Elements</span></span>  
  
|<span data-ttu-id="f83ef-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f83ef-114">Element</span></span>|<span data-ttu-id="f83ef-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f83ef-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f83ef-116">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f83ef-116">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="f83ef-117">Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f83ef-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="f83ef-118">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f83ef-118">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="f83ef-119">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="f83ef-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f83ef-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f83ef-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f83ef-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f83ef-121">Element</span></span>|<span data-ttu-id="f83ef-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f83ef-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f83ef-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f83ef-123">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="f83ef-124">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f83ef-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f83ef-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f83ef-125">Remarks</span></span>  
 <span data-ttu-id="f83ef-126">Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="f83ef-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="f83ef-127">Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="f83ef-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="f83ef-128">Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="f83ef-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83ef-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f83ef-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="f83ef-130">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="f83ef-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="f83ef-131">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="f83ef-131">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="f83ef-132">Указание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f83ef-132">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="f83ef-133">Указание поведения службы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f83ef-133">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="f83ef-134">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="f83ef-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
