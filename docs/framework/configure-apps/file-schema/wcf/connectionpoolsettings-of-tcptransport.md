---
title: <connectionPoolSettings> из <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398094"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="9b81c-102">\<коннектионпулсеттингс > \<tcpTransport платформы ></span><span class="sxs-lookup"><span data-stu-id="9b81c-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="9b81c-103">Задает дополнительные параметры пула подключений для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="9b81c-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="9b81c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b81c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b81c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b81c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9b81c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9b81c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9b81c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="9b81c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="9b81c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="9b81c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9b81c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tcpTransport платформы >** ](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="9b81c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="9b81c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Коннектионпулсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="9b81c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b81c-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b81c-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b81c-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b81c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9b81c-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b81c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b81c-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b81c-114">Attributes</span></span>  
  
|<span data-ttu-id="9b81c-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9b81c-115">Attribute</span></span>|<span data-ttu-id="9b81c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9b81c-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="9b81c-117">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="9b81c-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="9b81c-118">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="9b81c-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="9b81c-119">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="9b81c-119">The default is a "default" string.</span></span> <span data-ttu-id="9b81c-120">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="9b81c-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="9b81c-121">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="9b81c-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="9b81c-122">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="9b81c-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="9b81c-123">Параметр <xref:System.TimeSpan>, задающий время ожидания перед закрытием активного подключения.</span><span class="sxs-lookup"><span data-stu-id="9b81c-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="9b81c-124">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="9b81c-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="9b81c-125">Подключение закрывается после возврата в кэш подключений, а не во время активной передачи.</span><span class="sxs-lookup"><span data-stu-id="9b81c-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="9b81c-126">Кэш подключений, используемый транспортом TCP, по мере необходимости создает новые подключения для каждой конечной точки, до достижения лимита кэша, который задается параметром `maxOutboundConnectionsPerEndpoint.`</span><span class="sxs-lookup"><span data-stu-id="9b81c-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="9b81c-127">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="9b81c-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="9b81c-128">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9b81c-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="9b81c-129">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="9b81c-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="9b81c-130">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="9b81c-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="9b81c-131">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="9b81c-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="9b81c-132">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="9b81c-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="9b81c-133">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="9b81c-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b81c-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b81c-134">Child Elements</span></span>  
 <span data-ttu-id="9b81c-135">Нет.</span><span class="sxs-lookup"><span data-stu-id="9b81c-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b81c-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b81c-136">Parent Elements</span></span>  
  
|<span data-ttu-id="9b81c-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b81c-137">Element</span></span>|<span data-ttu-id="9b81c-138">Описание</span><span class="sxs-lookup"><span data-stu-id="9b81c-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b81c-139">\<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="9b81c-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="9b81c-140">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="9b81c-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b81c-141">См. также</span><span class="sxs-lookup"><span data-stu-id="9b81c-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9b81c-142">Транспорты</span><span class="sxs-lookup"><span data-stu-id="9b81c-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="9b81c-143">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="9b81c-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="9b81c-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="9b81c-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9b81c-145">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="9b81c-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9b81c-146">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="9b81c-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9b81c-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9b81c-147">\<customBinding></span></span>](custombinding.md)
