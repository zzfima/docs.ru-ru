---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: dd6cf74560694e7e16103c624b33a4c590ce5d50
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266927"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="8f4da-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="8f4da-101">\<channelPoolSettings></span></span>
<span data-ttu-id="8f4da-102">Задает параметры пула каналов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8f4da-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="8f4da-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8f4da-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8f4da-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8f4da-104">\<bindings></span></span>  
<span data-ttu-id="8f4da-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8f4da-105">\<customBinding></span></span>  
<span data-ttu-id="8f4da-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8f4da-106">\<binding></span></span>  
<span data-ttu-id="8f4da-107">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="8f4da-107">\<oneWay></span></span>  
<span data-ttu-id="8f4da-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="8f4da-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4da-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f4da-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f4da-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8f4da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f4da-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8f4da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f4da-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f4da-112">Attributes</span></span>  
  
|<span data-ttu-id="8f4da-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8f4da-113">Attribute</span></span>|<span data-ttu-id="8f4da-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8f4da-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="8f4da-115">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением.</span><span class="sxs-lookup"><span data-stu-id="8f4da-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="8f4da-116">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="8f4da-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="8f4da-117">Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул.</span><span class="sxs-lookup"><span data-stu-id="8f4da-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="8f4da-118">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="8f4da-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="8f4da-119">Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f4da-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="8f4da-120">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="8f4da-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f4da-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f4da-121">Child Elements</span></span>  
 <span data-ttu-id="8f4da-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8f4da-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f4da-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8f4da-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8f4da-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f4da-124">Element</span></span>|<span data-ttu-id="8f4da-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="8f4da-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f4da-126">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="8f4da-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="8f4da-127">Включает маршрутизацию пакетов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8f4da-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f4da-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f4da-128">Remarks</span></span>  
 <span data-ttu-id="8f4da-129">Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="8f4da-130">Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS).</span><span class="sxs-lookup"><span data-stu-id="8f4da-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="8f4da-131">Этот элемент используется при установке квот на пользовательском канале.</span><span class="sxs-lookup"><span data-stu-id="8f4da-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="8f4da-132">`ChannelPoolSettings` задает три квоты.</span><span class="sxs-lookup"><span data-stu-id="8f4da-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="8f4da-133">Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени.</span><span class="sxs-lookup"><span data-stu-id="8f4da-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="8f4da-134">На клиенте установка правильного значения может повысить надежность соединения со службой.</span><span class="sxs-lookup"><span data-stu-id="8f4da-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="8f4da-135">Значение по умолчанию основано на консервативно умеренном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="8f4da-136">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="8f4da-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="8f4da-137">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="8f4da-138">Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="8f4da-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="8f4da-139">Значение по умолчанию основано на консервативном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="8f4da-140">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="8f4da-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="8f4da-141">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="8f4da-142">Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="8f4da-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="8f4da-143">Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок.</span><span class="sxs-lookup"><span data-stu-id="8f4da-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="8f4da-144">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8f4da-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4da-145">См. также</span><span class="sxs-lookup"><span data-stu-id="8f4da-145">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8f4da-146">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="8f4da-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="8f4da-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="8f4da-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8f4da-148">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8f4da-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8f4da-149">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8f4da-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8f4da-150">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8f4da-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
