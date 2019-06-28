---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 819639eabf0332a34d6a7250159d24e42552f874
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423092"
---
# <a name="namedpipetransport"></a><span data-ttu-id="0ce1a-101">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-101">\<namedPipeTransport></span></span>
<span data-ttu-id="0ce1a-102">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="0ce1a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0ce1a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0ce1a-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-104">\<bindings></span></span>  
<span data-ttu-id="0ce1a-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-105">\<customBinding></span></span>  
<span data-ttu-id="0ce1a-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-106">\<binding></span></span>  
<span data-ttu-id="0ce1a-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="0ce1a-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce1a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ce1a-108">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ce1a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0ce1a-109">Attributes and Elements</span></span>  
<span data-ttu-id="0ce1a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ce1a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0ce1a-111">Attributes</span></span>  
<span data-ttu-id="0ce1a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ce1a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0ce1a-113">Child Elements</span></span>  
  
|<span data-ttu-id="0ce1a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0ce1a-114">Element</span></span>|<span data-ttu-id="0ce1a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0ce1a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ce1a-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="0ce1a-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="0ce1a-117">Возвращает или задает <xref:System.TimeSpan> , определяет максимальное время канал может находиться в состоянии инициализации перед отключением.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="0ce1a-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="0ce1a-118">ConnectionBufferSize</span></span>|<span data-ttu-id="0ce1a-119">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="0ce1a-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="0ce1a-120">hostNameComparisonMode</span></span>|<span data-ttu-id="0ce1a-121">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="0ce1a-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="0ce1a-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="0ce1a-122">manualAddressing</span></span>|<span data-ttu-id="0ce1a-123">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="0ce1a-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="0ce1a-124">maxBufferPoolSize</span></span>|<span data-ttu-id="0ce1a-125">Получает или задает максимальный размер в байтах, буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="0ce1a-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="0ce1a-126">maxBufferSize</span></span>|<span data-ttu-id="0ce1a-127">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="0ce1a-128">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="0ce1a-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="0ce1a-129">maxOutputDelay</span></span>|<span data-ttu-id="0ce1a-130">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="0ce1a-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="0ce1a-131">maxPendingAccepts</span></span>|<span data-ttu-id="0ce1a-132">Возвращает или задает максимальное число каналов, служба может иметь ожидающих на прослушивателе для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="0ce1a-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="0ce1a-133">maxPendingConnections</span></span>|<span data-ttu-id="0ce1a-134">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="0ce1a-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0ce1a-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="0ce1a-136">Возвращает и задает максимально допустимый размер сообщения, в байтах, которые могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="0ce1a-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="0ce1a-137">transferMode</span></span>|<span data-ttu-id="0ce1a-138">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="0ce1a-139">\<connectionPoolSettings > из \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="0ce1a-140">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ce1a-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0ce1a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="0ce1a-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="0ce1a-142">Element</span></span>|<span data-ttu-id="0ce1a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="0ce1a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ce1a-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0ce1a-145">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ce1a-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ce1a-146">Remarks</span></span>  
<span data-ttu-id="0ce1a-147">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="0ce1a-148">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="0ce1a-149">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="0ce1a-150">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0ce1a-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce1a-151">См. также</span><span class="sxs-lookup"><span data-stu-id="0ce1a-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0ce1a-152">Транспорты</span><span class="sxs-lookup"><span data-stu-id="0ce1a-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="0ce1a-153">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="0ce1a-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="0ce1a-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="0ce1a-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0ce1a-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="0ce1a-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0ce1a-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="0ce1a-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0ce1a-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0ce1a-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
