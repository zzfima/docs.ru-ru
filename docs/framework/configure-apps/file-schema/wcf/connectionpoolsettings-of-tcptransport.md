---
title: <connectionPoolSettings> из <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 93363c5ff1753ff02956404da7697780078c9839
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129978"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="7b5df-102">\<connectionPoolSettings > из \<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="7b5df-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="7b5df-103">Задает дополнительные параметры пула подключений для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="7b5df-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="7b5df-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7b5df-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7b5df-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7b5df-105">\<bindings></span></span>  
<span data-ttu-id="7b5df-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="7b5df-106">\<customBinding></span></span>  
<span data-ttu-id="7b5df-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7b5df-107">\<binding></span></span>  
<span data-ttu-id="7b5df-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="7b5df-108">\<tcpTransport></span></span>  
<span data-ttu-id="7b5df-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="7b5df-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5df-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b5df-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b5df-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b5df-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b5df-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b5df-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b5df-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b5df-113">Attributes</span></span>  
  
|<span data-ttu-id="7b5df-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b5df-114">Attribute</span></span>|<span data-ttu-id="7b5df-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7b5df-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="7b5df-116">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="7b5df-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="7b5df-117">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="7b5df-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="7b5df-118">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="7b5df-118">The default is a "default" string.</span></span> <span data-ttu-id="7b5df-119">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="7b5df-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="7b5df-120">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="7b5df-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="7b5df-121">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="7b5df-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="7b5df-122">Параметр <xref:System.TimeSpan>, задающий время ожидания перед закрытием активного подключения.</span><span class="sxs-lookup"><span data-stu-id="7b5df-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="7b5df-123">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="7b5df-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="7b5df-124">Подключение закрывается после возврата в кэш подключений, а не во время активной передачи.</span><span class="sxs-lookup"><span data-stu-id="7b5df-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="7b5df-125">Кэш подключений, используемый транспортом TCP создает новые подключения, необходимые для каждой конечной точки, до достижения лимита кэша, который задается</span><span class="sxs-lookup"><span data-stu-id="7b5df-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by</span></span> `maxOutboundConnectionsPerEndpoint.`|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="7b5df-126">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="7b5df-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="7b5df-127">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7b5df-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="7b5df-128">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="7b5df-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="7b5df-129">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="7b5df-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="7b5df-130">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="7b5df-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="7b5df-131">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="7b5df-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="7b5df-132">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="7b5df-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b5df-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b5df-133">Child Elements</span></span>  
 <span data-ttu-id="7b5df-134">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7b5df-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b5df-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b5df-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7b5df-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b5df-136">Element</span></span>|<span data-ttu-id="7b5df-137">Описание</span><span class="sxs-lookup"><span data-stu-id="7b5df-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b5df-138">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="7b5df-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="7b5df-139">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="7b5df-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b5df-140">См. также</span><span class="sxs-lookup"><span data-stu-id="7b5df-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7b5df-141">Транспорты</span><span class="sxs-lookup"><span data-stu-id="7b5df-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="7b5df-142">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="7b5df-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="7b5df-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="7b5df-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7b5df-144">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="7b5df-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7b5df-145">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="7b5df-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7b5df-146">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="7b5df-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
