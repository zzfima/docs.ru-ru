---
title: '&lt;oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 79dd5dd0ca383cebc5f08f3e12c6c6261d11a02a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="da4fa-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="da4fa-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="da4fa-103">Включает поддержку маршрутизации пакетов и использования односторонних методов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="da4fa-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="da4fa-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="da4fa-104">\<system.serviceModel></span></span>  
<span data-ttu-id="da4fa-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="da4fa-105">\<bindings></span></span>  
<span data-ttu-id="da4fa-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="da4fa-106">\<customBinding></span></span>  
<span data-ttu-id="da4fa-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="da4fa-107">\<binding></span></span>  
<span data-ttu-id="da4fa-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="da4fa-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4fa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da4fa-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da4fa-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da4fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da4fa-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da4fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da4fa-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da4fa-112">Attributes</span></span>  
  
|<span data-ttu-id="da4fa-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da4fa-113">Attribute</span></span>|<span data-ttu-id="da4fa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="da4fa-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="da4fa-115">Логическое значение, указывающее, включена ли поддержка маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="da4fa-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="da4fa-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="da4fa-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="da4fa-117">Целое число, указывающее максимальное количество принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="da4fa-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da4fa-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da4fa-118">Child Elements</span></span>  
  
|<span data-ttu-id="da4fa-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="da4fa-119">Element</span></span>|<span data-ttu-id="da4fa-120">Описание</span><span class="sxs-lookup"><span data-stu-id="da4fa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da4fa-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="da4fa-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="da4fa-122">Объект <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>, содержащий свойства пула каналов для текущего канала.</span><span class="sxs-lookup"><span data-stu-id="da4fa-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da4fa-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da4fa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="da4fa-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="da4fa-124">Element</span></span>|<span data-ttu-id="da4fa-125">Описание</span><span class="sxs-lookup"><span data-stu-id="da4fa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da4fa-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="da4fa-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="da4fa-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="da4fa-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da4fa-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="da4fa-128">Remarks</span></span>  
 <span data-ttu-id="da4fa-129">Чтобы включить поддержку маршрутизации пакетов, необходим уровень одностороннего преобразования, предоставляемый данным элементом.</span><span class="sxs-lookup"><span data-stu-id="da4fa-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="da4fa-130">Пользователь может создавать пользовательские привязки, которые выполняют наложение данной привязки на транспорт с поддержкой сеансов или типа «запрос-отклик», чтобы включить для него поддержку маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="da4fa-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="da4fa-131">Этот элемент также полезен, если необходимо предоставить односторонние методы более естественным образом.</span><span class="sxs-lookup"><span data-stu-id="da4fa-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="da4fa-132">К данному уровню могут применяться дополнительные преобразования, например Composite Duplex и Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="da4fa-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4fa-133">См. также</span><span class="sxs-lookup"><span data-stu-id="da4fa-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="da4fa-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="da4fa-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="da4fa-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="da4fa-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="da4fa-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="da4fa-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="da4fa-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="da4fa-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
