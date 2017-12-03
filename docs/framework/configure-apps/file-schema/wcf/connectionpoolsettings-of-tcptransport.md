---
title: "&lt;connectionPoolSettings&gt; для &lt;tcpTransport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b0bd7303f714847228bcd8bfed7134fe9942c1a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltconnectionpoolsettingsgt-of-lttcptransportgt"></a><span data-ttu-id="26641-102">&lt;connectionPoolSettings&gt; для &lt;tcpTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="26641-102">&lt;connectionPoolSettings&gt; of &lt;tcpTransport&gt;</span></span>
<span data-ttu-id="26641-103">Задает дополнительные параметры пула подключений для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="26641-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="26641-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="26641-104">\<system.serviceModel></span></span>  
<span data-ttu-id="26641-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="26641-105">\<bindings></span></span>  
<span data-ttu-id="26641-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="26641-106">\<customBinding></span></span>  
<span data-ttu-id="26641-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="26641-107">\<binding></span></span>  
<span data-ttu-id="26641-108">\<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="26641-108">\<tcpTransport></span></span>  
<span data-ttu-id="26641-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="26641-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26641-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26641-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
    groupName="String"  
    idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26641-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="26641-111">Attributes and Elements</span></span>  
 <span data-ttu-id="26641-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="26641-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26641-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="26641-113">Attributes</span></span>  
  
|<span data-ttu-id="26641-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="26641-114">Attribute</span></span>|<span data-ttu-id="26641-115">Описание</span><span class="sxs-lookup"><span data-stu-id="26641-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="26641-116">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="26641-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="26641-117">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="26641-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="26641-118">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="26641-118">The default is a "default" string.</span></span> <span data-ttu-id="26641-119">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="26641-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="26641-120">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="26641-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="26641-121">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="26641-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="26641-122">Параметр <xref:System.TimeSpan>, задающий время ожидания перед закрытием активного подключения.</span><span class="sxs-lookup"><span data-stu-id="26641-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="26641-123">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="26641-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="26641-124">Подключение закрывается после возврата в кэш подключений, а не во время активной передачи.</span><span class="sxs-lookup"><span data-stu-id="26641-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="26641-125">Кэш подключений, используемый транспортом TCP, по мере необходимости создает новые подключения для каждой конечной точки, до достижения лимита кэша, который задается параметром `maxOutboundConnectionsPerEndpoint.`</span><span class="sxs-lookup"><span data-stu-id="26641-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="26641-126">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="26641-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="26641-127">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="26641-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="26641-128">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="26641-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="26641-129">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="26641-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="26641-130">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="26641-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="26641-131">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="26641-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="26641-132">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="26641-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26641-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="26641-133">Child Elements</span></span>  
 <span data-ttu-id="26641-134">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="26641-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26641-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="26641-135">Parent Elements</span></span>  
  
|<span data-ttu-id="26641-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="26641-136">Element</span></span>|<span data-ttu-id="26641-137">Описание</span><span class="sxs-lookup"><span data-stu-id="26641-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26641-138">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="26641-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="26641-139">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="26641-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26641-140">См. также</span><span class="sxs-lookup"><span data-stu-id="26641-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="26641-141">Транспорты</span><span class="sxs-lookup"><span data-stu-id="26641-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="26641-142">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="26641-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="26641-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="26641-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="26641-144">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="26641-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="26641-145">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="26641-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="26641-146">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="26641-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
