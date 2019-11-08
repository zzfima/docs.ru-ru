---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738787"
---
# <a name="oneway"></a><span data-ttu-id="aa4b9-101">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="aa4b9-101">\<oneWay></span></span>
<span data-ttu-id="aa4b9-102">Включает поддержку маршрутизации пакетов и использования односторонних методов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="aa4b9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa4b9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa4b9-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa4b9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa4b9-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="aa4b9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="aa4b9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="aa4b9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="aa4b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="aa4b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="aa4b9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<oneWay >**</span><span class="sxs-lookup"><span data-stu-id="aa4b9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4b9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa4b9-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa4b9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa4b9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aa4b9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa4b9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa4b9-112">Attributes</span></span>  
  
|<span data-ttu-id="aa4b9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa4b9-113">Attribute</span></span>|<span data-ttu-id="aa4b9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="aa4b9-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="aa4b9-115">Логическое значение, указывающее, включена ли поддержка маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="aa4b9-116">Значение по умолчанию: `false`.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="aa4b9-117">Целое число, указывающее максимальное количество принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa4b9-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa4b9-118">Child Elements</span></span>  
  
|<span data-ttu-id="aa4b9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa4b9-119">Element</span></span>|<span data-ttu-id="aa4b9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="aa4b9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa4b9-121">\<Чаннелпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="aa4b9-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="aa4b9-122">Объект <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>, содержащий свойства пула каналов для текущего канала.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa4b9-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa4b9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="aa4b9-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa4b9-124">Element</span></span>|<span data-ttu-id="aa4b9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="aa4b9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa4b9-126">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="aa4b9-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="aa4b9-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa4b9-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="aa4b9-128">Remarks</span></span>  
 <span data-ttu-id="aa4b9-129">Чтобы включить поддержку маршрутизации пакетов, необходим уровень одностороннего преобразования, предоставляемый данным элементом.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="aa4b9-130">Пользователь может создавать пользовательские привязки, которые выполняют наложение данной привязки на транспорт с поддержкой сеансов или типа «запрос-отклик», чтобы включить для него поддержку маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="aa4b9-131">Этот элемент также полезен, если необходимо предоставить односторонние методы более естественным образом.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="aa4b9-132">К данному уровню могут применяться дополнительные преобразования, например Composite Duplex и Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="aa4b9-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4b9-133">См. также</span><span class="sxs-lookup"><span data-stu-id="aa4b9-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="aa4b9-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="aa4b9-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aa4b9-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="aa4b9-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="aa4b9-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="aa4b9-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="aa4b9-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="aa4b9-137">\<customBinding></span></span>](custombinding.md)
