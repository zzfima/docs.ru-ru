---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 70f7452a22ae08d6eccd7d3644bdc8df45087ae0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423189"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="20289-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="20289-101">\<channelPoolSettings></span></span>
<span data-ttu-id="20289-102">Задает параметры пула каналов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="20289-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="20289-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20289-103">\<system.serviceModel></span></span>  
<span data-ttu-id="20289-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="20289-104">\<bindings></span></span>  
<span data-ttu-id="20289-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="20289-105">\<customBinding></span></span>  
<span data-ttu-id="20289-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="20289-106">\<binding></span></span>  
<span data-ttu-id="20289-107">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="20289-107">\<oneWay></span></span>  
<span data-ttu-id="20289-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="20289-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20289-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20289-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20289-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="20289-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20289-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20289-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20289-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20289-112">Attributes</span></span>  
  
|<span data-ttu-id="20289-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="20289-113">Attribute</span></span>|<span data-ttu-id="20289-114">Описание</span><span class="sxs-lookup"><span data-stu-id="20289-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="20289-115">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением.</span><span class="sxs-lookup"><span data-stu-id="20289-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="20289-116">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="20289-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="20289-117">Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул.</span><span class="sxs-lookup"><span data-stu-id="20289-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="20289-118">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="20289-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="20289-119">Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="20289-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="20289-120">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="20289-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20289-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20289-121">Child Elements</span></span>  
 <span data-ttu-id="20289-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="20289-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20289-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20289-123">Parent Elements</span></span>  
  
|<span data-ttu-id="20289-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="20289-124">Element</span></span>|<span data-ttu-id="20289-125">Описание</span><span class="sxs-lookup"><span data-stu-id="20289-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20289-126">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="20289-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="20289-127">Включает маршрутизацию пакетов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="20289-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20289-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="20289-128">Remarks</span></span>  
 <span data-ttu-id="20289-129">Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="20289-130">Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS).</span><span class="sxs-lookup"><span data-stu-id="20289-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="20289-131">Этот элемент используется при установке квот на пользовательском канале.</span><span class="sxs-lookup"><span data-stu-id="20289-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="20289-132">`ChannelPoolSettings` задает три квоты.</span><span class="sxs-lookup"><span data-stu-id="20289-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="20289-133">Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени.</span><span class="sxs-lookup"><span data-stu-id="20289-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="20289-134">На клиенте установка правильного значения может повысить надежность соединения со службой.</span><span class="sxs-lookup"><span data-stu-id="20289-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="20289-135">Значение по умолчанию основано на консервативно умеренном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="20289-136">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="20289-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="20289-137">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="20289-138">Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="20289-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="20289-139">Значение по умолчанию основано на консервативном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="20289-140">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="20289-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="20289-141">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="20289-142">Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="20289-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="20289-143">Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок.</span><span class="sxs-lookup"><span data-stu-id="20289-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="20289-144">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20289-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20289-145">См. также</span><span class="sxs-lookup"><span data-stu-id="20289-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="20289-146">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="20289-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="20289-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="20289-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="20289-148">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="20289-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="20289-149">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="20289-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="20289-150">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="20289-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
