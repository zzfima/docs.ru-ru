---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d48f3b304b337ba61f53bbd81cac8601bc68cb0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="63c88-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="63c88-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="63c88-103">Задает параметры пула каналов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="63c88-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="63c88-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="63c88-104">\<system.serviceModel></span></span>  
<span data-ttu-id="63c88-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="63c88-105">\<bindings></span></span>  
<span data-ttu-id="63c88-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="63c88-106">\<customBinding></span></span>  
<span data-ttu-id="63c88-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="63c88-107">\<binding></span></span>  
<span data-ttu-id="63c88-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="63c88-108">\<oneWay></span></span>  
<span data-ttu-id="63c88-109">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="63c88-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63c88-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63c88-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63c88-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="63c88-111">Attributes and Elements</span></span>  
 <span data-ttu-id="63c88-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="63c88-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63c88-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="63c88-113">Attributes</span></span>  
  
|<span data-ttu-id="63c88-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="63c88-114">Attribute</span></span>|<span data-ttu-id="63c88-115">Описание</span><span class="sxs-lookup"><span data-stu-id="63c88-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="63c88-116">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением.</span><span class="sxs-lookup"><span data-stu-id="63c88-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="63c88-117">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="63c88-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="63c88-118">Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул.</span><span class="sxs-lookup"><span data-stu-id="63c88-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="63c88-119">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="63c88-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="63c88-120">Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="63c88-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="63c88-121">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="63c88-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63c88-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="63c88-122">Child Elements</span></span>  
 <span data-ttu-id="63c88-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="63c88-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63c88-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="63c88-124">Parent Elements</span></span>  
  
|<span data-ttu-id="63c88-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="63c88-125">Element</span></span>|<span data-ttu-id="63c88-126">Описание</span><span class="sxs-lookup"><span data-stu-id="63c88-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63c88-127">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="63c88-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="63c88-128">Включает маршрутизацию пакетов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="63c88-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63c88-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="63c88-129">Remarks</span></span>  
 <span data-ttu-id="63c88-130">Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="63c88-131">Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS).</span><span class="sxs-lookup"><span data-stu-id="63c88-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="63c88-132">Этот элемент используется при установке квот на пользовательском канале.</span><span class="sxs-lookup"><span data-stu-id="63c88-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="63c88-133">`ChannelPoolSettings` задает три квоты.</span><span class="sxs-lookup"><span data-stu-id="63c88-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="63c88-134">Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени.</span><span class="sxs-lookup"><span data-stu-id="63c88-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="63c88-135">На клиенте установка правильного значения может повысить надежность соединения со службой.</span><span class="sxs-lookup"><span data-stu-id="63c88-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="63c88-136">Значение по умолчанию основано на консервативно умеренном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="63c88-137">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="63c88-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="63c88-138">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="63c88-139">Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="63c88-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="63c88-140">Значение по умолчанию основано на консервативном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="63c88-141">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="63c88-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="63c88-142">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="63c88-143">Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="63c88-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="63c88-144">Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок.</span><span class="sxs-lookup"><span data-stu-id="63c88-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="63c88-145">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="63c88-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c88-146">См. также</span><span class="sxs-lookup"><span data-stu-id="63c88-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="63c88-147">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="63c88-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [<span data-ttu-id="63c88-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="63c88-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="63c88-149">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="63c88-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="63c88-150">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="63c88-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="63c88-151">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="63c88-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
