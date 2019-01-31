---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e30fcd5952fadc3b6cf30cb352a3bb51c86cc117
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285935"
---
# <a name="namedpipetransport"></a><span data-ttu-id="3c1e8-101">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-101">\<namedPipeTransport></span></span>
<span data-ttu-id="3c1e8-102">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="3c1e8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c1e8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="3c1e8-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-104">\<bindings></span></span>  
<span data-ttu-id="3c1e8-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-105">\<customBinding></span></span>  
<span data-ttu-id="3c1e8-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-106">\<binding></span></span>  
<span data-ttu-id="3c1e8-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="3c1e8-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c1e8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c1e8-108">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c1e8-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3c1e8-109">Attributes and Elements</span></span>  
<span data-ttu-id="3c1e8-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c1e8-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3c1e8-111">Attributes</span></span>  
<span data-ttu-id="3c1e8-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c1e8-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3c1e8-113">Child Elements</span></span>  
  
|<span data-ttu-id="3c1e8-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c1e8-114">Element</span></span>|<span data-ttu-id="3c1e8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3c1e8-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c1e8-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="3c1e8-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="3c1e8-117">Возвращает или задает <xref:System.TimeSpan> , определяет максимальное время канал может находиться в состоянии инициализации перед отключением.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="3c1e8-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="3c1e8-118">ConnectionBufferSize</span></span>|<span data-ttu-id="3c1e8-119">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="3c1e8-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="3c1e8-120">hostNameComparisonMode</span></span>|<span data-ttu-id="3c1e8-121">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="3c1e8-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="3c1e8-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="3c1e8-122">manualAddressing</span></span>|<span data-ttu-id="3c1e8-123">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="3c1e8-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="3c1e8-124">maxBufferPoolSize</span></span>|<span data-ttu-id="3c1e8-125">Получает или задает максимальный размер в байтах, буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="3c1e8-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="3c1e8-126">maxBufferSize</span></span>|<span data-ttu-id="3c1e8-127">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="3c1e8-128">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="3c1e8-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="3c1e8-129">maxOutputDelay</span></span>|<span data-ttu-id="3c1e8-130">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="3c1e8-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="3c1e8-131">maxPendingAccepts</span></span>|<span data-ttu-id="3c1e8-132">Возвращает или задает максимальное число каналов, служба может иметь ожидающих на прослушивателе для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="3c1e8-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="3c1e8-133">maxPendingConnections</span></span>|<span data-ttu-id="3c1e8-134">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="3c1e8-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="3c1e8-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="3c1e8-136">Возвращает и задает максимально допустимый размер сообщения, в байтах, которые могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="3c1e8-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="3c1e8-137">transferMode</span></span>|<span data-ttu-id="3c1e8-138">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="3c1e8-139">\<connectionPoolSettings > из \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="3c1e8-140">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c1e8-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3c1e8-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3c1e8-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c1e8-142">Element</span></span>|<span data-ttu-id="3c1e8-143">Описание</span><span class="sxs-lookup"><span data-stu-id="3c1e8-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c1e8-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3c1e8-145">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c1e8-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c1e8-146">Remarks</span></span>  
<span data-ttu-id="3c1e8-147">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="3c1e8-148">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="3c1e8-149">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="3c1e8-150">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1e8-151">См. также</span><span class="sxs-lookup"><span data-stu-id="3c1e8-151">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3c1e8-152">Транспорты</span><span class="sxs-lookup"><span data-stu-id="3c1e8-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="3c1e8-153">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="3c1e8-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3c1e8-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="3c1e8-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3c1e8-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="3c1e8-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3c1e8-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="3c1e8-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3c1e8-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3c1e8-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
