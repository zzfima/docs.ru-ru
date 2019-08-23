---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 473d0fbd543a056ec2b152f43a76a0417a18016f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933204"
---
# <a name="namedpipetransport"></a><span data-ttu-id="f4598-101">\<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="f4598-101">\<namedPipeTransport></span></span>
<span data-ttu-id="f4598-102">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="f4598-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="f4598-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="f4598-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f4598-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f4598-104">\<bindings></span></span>  
<span data-ttu-id="f4598-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f4598-105">\<customBinding></span></span>  
<span data-ttu-id="f4598-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f4598-106">\<binding></span></span>  
<span data-ttu-id="f4598-107">\<Намепипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="f4598-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4598-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4598-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4598-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4598-109">Attributes and Elements</span></span>  
<span data-ttu-id="f4598-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f4598-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4598-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4598-111">Attributes</span></span>  
<span data-ttu-id="f4598-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4598-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4598-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4598-113">Child Elements</span></span>  
  
|<span data-ttu-id="f4598-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4598-114">Element</span></span>|<span data-ttu-id="f4598-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f4598-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4598-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="f4598-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="f4598-117">Возвращает или задает значение <xref:System.TimeSpan> типа, которое определяет максимальное время, в течение которого канал может быть в состоянии инициализации до отключения.</span><span class="sxs-lookup"><span data-stu-id="f4598-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="f4598-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="f4598-118">ConnectionBufferSize</span></span>|<span data-ttu-id="f4598-119">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="f4598-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="f4598-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="f4598-120">hostNameComparisonMode</span></span>|<span data-ttu-id="f4598-121">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="f4598-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="f4598-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="f4598-122">manualAddressing</span></span>|<span data-ttu-id="f4598-123">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="f4598-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="f4598-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f4598-124">maxBufferPoolSize</span></span>|<span data-ttu-id="f4598-125">Возвращает или задает максимальный размер (в байтах) всех пулов буферов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="f4598-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="f4598-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="f4598-126">maxBufferSize</span></span>|<span data-ttu-id="f4598-127">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="f4598-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="f4598-128">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="f4598-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="f4598-129">максаутпутделай</span><span class="sxs-lookup"><span data-stu-id="f4598-129">maxOutputDelay</span></span>|<span data-ttu-id="f4598-130">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="f4598-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="f4598-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="f4598-131">maxPendingAccepts</span></span>|<span data-ttu-id="f4598-132">Возвращает или задает максимальное число каналов, которые служба может ожидать от прослушивателя для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="f4598-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="f4598-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="f4598-133">maxPendingConnections</span></span>|<span data-ttu-id="f4598-134">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="f4598-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="f4598-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f4598-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="f4598-136">Возвращает и задает максимально допустимый размер сообщения (в байтах), который может быть получен.</span><span class="sxs-lookup"><span data-stu-id="f4598-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="f4598-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="f4598-137">transferMode</span></span>|<span data-ttu-id="f4598-138">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="f4598-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="f4598-139">\<коннектионпулсеттингс > \<намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="f4598-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="f4598-140">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="f4598-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4598-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4598-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f4598-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4598-142">Element</span></span>|<span data-ttu-id="f4598-143">Описание</span><span class="sxs-lookup"><span data-stu-id="f4598-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4598-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f4598-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="f4598-145">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="f4598-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4598-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4598-146">Remarks</span></span>  
<span data-ttu-id="f4598-147">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="f4598-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="f4598-148">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="f4598-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="f4598-149">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4598-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="f4598-150">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f4598-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4598-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f4598-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f4598-152">Транспорты</span><span class="sxs-lookup"><span data-stu-id="f4598-152">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="f4598-153">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="f4598-153">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f4598-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="f4598-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f4598-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="f4598-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f4598-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="f4598-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f4598-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f4598-157">\<customBinding></span></span>](custombinding.md)
