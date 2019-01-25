---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: cdb2863ff376a92f7c4b679f4812b895ac3f2234
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518843"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="03916-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="03916-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="03916-103">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="03916-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="03916-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="03916-104">\<system.serviceModel></span></span>  
<span data-ttu-id="03916-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="03916-105">\<bindings></span></span>  
<span data-ttu-id="03916-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="03916-106">\<customBinding></span></span>  
<span data-ttu-id="03916-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="03916-107">\<binding></span></span>  
<span data-ttu-id="03916-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="03916-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03916-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03916-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03916-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="03916-110">Attributes and Elements</span></span>  
<span data-ttu-id="03916-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03916-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03916-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03916-112">Attributes</span></span>  
<span data-ttu-id="03916-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="03916-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03916-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03916-114">Child Elements</span></span>  
  
|<span data-ttu-id="03916-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="03916-115">Element</span></span>|<span data-ttu-id="03916-116">Описание</span><span class="sxs-lookup"><span data-stu-id="03916-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03916-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="03916-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="03916-118">Возвращает или задает <xref:System.TimeSpan> , определяет максимальное время канал может находиться в состоянии инициализации перед отключением.</span><span class="sxs-lookup"><span data-stu-id="03916-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="03916-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="03916-119">ConnectionBufferSize</span></span>|<span data-ttu-id="03916-120">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="03916-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="03916-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="03916-121">hostNameComparisonMode</span></span>|<span data-ttu-id="03916-122">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="03916-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="03916-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="03916-123">manualAddressing</span></span>|<span data-ttu-id="03916-124">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="03916-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="03916-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="03916-125">maxBufferPoolSize</span></span>|<span data-ttu-id="03916-126">Получает или задает максимальный размер в байтах, буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="03916-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="03916-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="03916-127">maxBufferSize</span></span>|<span data-ttu-id="03916-128">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="03916-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="03916-129">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="03916-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="03916-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="03916-130">maxOutputDelay</span></span>|<span data-ttu-id="03916-131">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="03916-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="03916-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="03916-132">maxPendingAccepts</span></span>|<span data-ttu-id="03916-133">Возвращает или задает максимальное число каналов, служба может иметь ожидающих на прослушивателе для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="03916-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="03916-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="03916-134">maxPendingConnections</span></span>|<span data-ttu-id="03916-135">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="03916-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="03916-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="03916-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="03916-137">Возвращает и задает максимально допустимый размер сообщения, в байтах, которые могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="03916-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="03916-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="03916-138">transferMode</span></span>|<span data-ttu-id="03916-139">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="03916-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="03916-140">\<connectionPoolSettings > из \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="03916-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="03916-141">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="03916-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03916-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03916-142">Parent Elements</span></span>  
  
|<span data-ttu-id="03916-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="03916-143">Element</span></span>|<span data-ttu-id="03916-144">Описание:</span><span class="sxs-lookup"><span data-stu-id="03916-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03916-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="03916-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="03916-146">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="03916-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03916-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="03916-147">Remarks</span></span>  
<span data-ttu-id="03916-148">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="03916-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="03916-149">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="03916-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="03916-150">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="03916-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="03916-151">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="03916-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03916-152">См. также</span><span class="sxs-lookup"><span data-stu-id="03916-152">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="03916-153">Транспорты</span><span class="sxs-lookup"><span data-stu-id="03916-153">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="03916-154">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="03916-154">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="03916-155">Привязки</span><span class="sxs-lookup"><span data-stu-id="03916-155">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="03916-156">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="03916-156">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="03916-157">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="03916-157">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="03916-158">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="03916-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
