---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: bfda2b9d7b3aa5219a3e4c344347d3b10419a7bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102418"
---
# <a name="oneway"></a><span data-ttu-id="45706-101">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="45706-101">\<oneWay></span></span>
<span data-ttu-id="45706-102">Включает поддержку маршрутизации пакетов и использования односторонних методов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="45706-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="45706-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="45706-103">\<system.serviceModel></span></span>  
<span data-ttu-id="45706-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="45706-104">\<bindings></span></span>  
<span data-ttu-id="45706-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="45706-105">\<customBinding></span></span>  
<span data-ttu-id="45706-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="45706-106">\<binding></span></span>  
<span data-ttu-id="45706-107">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="45706-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45706-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45706-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45706-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="45706-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45706-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="45706-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45706-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="45706-111">Attributes</span></span>  
  
|<span data-ttu-id="45706-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="45706-112">Attribute</span></span>|<span data-ttu-id="45706-113">Описание</span><span class="sxs-lookup"><span data-stu-id="45706-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="45706-114">Логическое значение, указывающее, включена ли поддержка маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="45706-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="45706-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="45706-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="45706-116">Целое число, указывающее максимальное количество принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="45706-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45706-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="45706-117">Child Elements</span></span>  
  
|<span data-ttu-id="45706-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="45706-118">Element</span></span>|<span data-ttu-id="45706-119">Описание</span><span class="sxs-lookup"><span data-stu-id="45706-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45706-120">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="45706-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="45706-121">Объект <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>, содержащий свойства пула каналов для текущего канала.</span><span class="sxs-lookup"><span data-stu-id="45706-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45706-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="45706-122">Parent Elements</span></span>  
  
|<span data-ttu-id="45706-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="45706-123">Element</span></span>|<span data-ttu-id="45706-124">Описание</span><span class="sxs-lookup"><span data-stu-id="45706-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45706-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="45706-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="45706-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="45706-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45706-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="45706-127">Remarks</span></span>  
 <span data-ttu-id="45706-128">Чтобы включить поддержку маршрутизации пакетов, необходим уровень одностороннего преобразования, предоставляемый данным элементом.</span><span class="sxs-lookup"><span data-stu-id="45706-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="45706-129">Пользователь может создавать пользовательские привязки, которые выполняют наложение данной привязки на транспорт с поддержкой сеансов или типа «запрос-отклик», чтобы включить для него поддержку маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="45706-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="45706-130">Этот элемент также полезен, если необходимо предоставить односторонние методы более естественным образом.</span><span class="sxs-lookup"><span data-stu-id="45706-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="45706-131">К данному уровню могут применяться дополнительные преобразования, например Composite Duplex и Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45706-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45706-132">См. также</span><span class="sxs-lookup"><span data-stu-id="45706-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="45706-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="45706-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="45706-134">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="45706-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="45706-135">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="45706-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="45706-136">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="45706-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
