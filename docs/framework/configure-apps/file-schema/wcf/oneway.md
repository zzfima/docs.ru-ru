---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f12969d8b752e54916b45c3d0e64f114971b8944
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397652"
---
# <a name="oneway"></a><span data-ttu-id="fae6f-101">\<> oneWay</span><span class="sxs-lookup"><span data-stu-id="fae6f-101">\<oneWay></span></span>
<span data-ttu-id="fae6f-102">Включает поддержку маршрутизации пакетов и использования односторонних методов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="fae6f-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="fae6f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fae6f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fae6f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fae6f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fae6f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fae6f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fae6f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="fae6f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="fae6f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="fae6f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fae6f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oneWay**</span><span class="sxs-lookup"><span data-stu-id="fae6f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae6f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fae6f-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fae6f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fae6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fae6f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fae6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fae6f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fae6f-112">Attributes</span></span>  
  
|<span data-ttu-id="fae6f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fae6f-113">Attribute</span></span>|<span data-ttu-id="fae6f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fae6f-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="fae6f-115">Логическое значение, указывающее, включена ли поддержка маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="fae6f-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="fae6f-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="fae6f-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="fae6f-117">Целое число, указывающее максимальное количество принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="fae6f-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fae6f-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fae6f-118">Child Elements</span></span>  
  
|<span data-ttu-id="fae6f-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fae6f-119">Element</span></span>|<span data-ttu-id="fae6f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fae6f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fae6f-121">\<Чаннелпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="fae6f-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="fae6f-122">Объект <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>, содержащий свойства пула каналов для текущего канала.</span><span class="sxs-lookup"><span data-stu-id="fae6f-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fae6f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fae6f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fae6f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="fae6f-124">Element</span></span>|<span data-ttu-id="fae6f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fae6f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fae6f-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="fae6f-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="fae6f-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="fae6f-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fae6f-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="fae6f-128">Remarks</span></span>  
 <span data-ttu-id="fae6f-129">Чтобы включить поддержку маршрутизации пакетов, необходим уровень одностороннего преобразования, предоставляемый данным элементом.</span><span class="sxs-lookup"><span data-stu-id="fae6f-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="fae6f-130">Пользователь может создавать пользовательские привязки, которые выполняют наложение данной привязки на транспорт с поддержкой сеансов или типа «запрос-отклик», чтобы включить для него поддержку маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="fae6f-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="fae6f-131">Этот элемент также полезен, если необходимо предоставить односторонние методы более естественным образом.</span><span class="sxs-lookup"><span data-stu-id="fae6f-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="fae6f-132">К данному уровню могут применяться дополнительные преобразования, например Composite Duplex и Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="fae6f-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae6f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="fae6f-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fae6f-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="fae6f-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fae6f-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="fae6f-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fae6f-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="fae6f-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fae6f-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="fae6f-137">\<customBinding></span></span>](custombinding.md)
