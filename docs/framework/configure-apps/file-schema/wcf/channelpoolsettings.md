---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398160"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="b6467-101">\<Чаннелпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="b6467-101">\<channelPoolSettings></span></span>
<span data-ttu-id="b6467-102">Задает параметры пула каналов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b6467-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
<span data-ttu-id="b6467-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6467-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6467-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b6467-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6467-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b6467-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b6467-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6467-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b6467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="b6467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b6467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> oneWay**](oneway.md)</span><span class="sxs-lookup"><span data-stu-id="b6467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)</span></span>\
<span data-ttu-id="b6467-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Чаннелпулсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="b6467-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6467-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6467-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6467-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6467-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b6467-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6467-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6467-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6467-113">Attributes</span></span>  
  
|<span data-ttu-id="b6467-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6467-114">Attribute</span></span>|<span data-ttu-id="b6467-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b6467-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="b6467-116">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением.</span><span class="sxs-lookup"><span data-stu-id="b6467-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="b6467-117">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="b6467-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="b6467-118">Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул.</span><span class="sxs-lookup"><span data-stu-id="b6467-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="b6467-119">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="b6467-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="b6467-120">Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b6467-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="b6467-121">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="b6467-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6467-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6467-122">Child Elements</span></span>  
 <span data-ttu-id="b6467-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="b6467-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6467-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6467-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b6467-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6467-125">Element</span></span>|<span data-ttu-id="b6467-126">Описание</span><span class="sxs-lookup"><span data-stu-id="b6467-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6467-127">\<> oneWay</span><span class="sxs-lookup"><span data-stu-id="b6467-127">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="b6467-128">Включает маршрутизацию пакетов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b6467-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6467-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6467-129">Remarks</span></span>  
 <span data-ttu-id="b6467-130">Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="b6467-131">Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS).</span><span class="sxs-lookup"><span data-stu-id="b6467-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="b6467-132">Этот элемент используется при установке квот на пользовательском канале.</span><span class="sxs-lookup"><span data-stu-id="b6467-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="b6467-133">`ChannelPoolSettings` задает три квоты.</span><span class="sxs-lookup"><span data-stu-id="b6467-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="b6467-134">Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени.</span><span class="sxs-lookup"><span data-stu-id="b6467-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="b6467-135">На клиенте установка правильного значения может повысить надежность соединения со службой.</span><span class="sxs-lookup"><span data-stu-id="b6467-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="b6467-136">Значение по умолчанию основано на консервативно умеренном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="b6467-137">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="b6467-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b6467-138">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="b6467-139">Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="b6467-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="b6467-140">Значение по умолчанию основано на консервативном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="b6467-141">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="b6467-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b6467-142">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="b6467-143">Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="b6467-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="b6467-144">Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок.</span><span class="sxs-lookup"><span data-stu-id="b6467-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b6467-145">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6467-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6467-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b6467-146">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b6467-147">\<> oneWay</span><span class="sxs-lookup"><span data-stu-id="b6467-147">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="b6467-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="b6467-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b6467-149">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b6467-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b6467-150">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b6467-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b6467-151">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b6467-151">\<customBinding></span></span>](custombinding.md)
