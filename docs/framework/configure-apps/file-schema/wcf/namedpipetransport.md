---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736585"
---
# <a name="namedpipetransport"></a><span data-ttu-id="52d32-101">\<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="52d32-101">\<namedPipeTransport></span></span>
<span data-ttu-id="52d32-102">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="52d32-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="52d32-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52d32-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52d32-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="52d32-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="52d32-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="52d32-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="52d32-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="52d32-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="52d32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="52d32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="52d32-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<намедпипетранспорт >**</span><span class="sxs-lookup"><span data-stu-id="52d32-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d32-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52d32-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52d32-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52d32-110">Attributes and Elements</span></span>  
<span data-ttu-id="52d32-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52d32-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52d32-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52d32-112">Attributes</span></span>  
<span data-ttu-id="52d32-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="52d32-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52d32-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52d32-114">Child Elements</span></span>  
  
|<span data-ttu-id="52d32-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="52d32-115">Element</span></span>|<span data-ttu-id="52d32-116">Описание</span><span class="sxs-lookup"><span data-stu-id="52d32-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52d32-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="52d32-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="52d32-118">Возвращает или задает <xref:System.TimeSpan>, определяющее максимальное время, в течение которого канал может быть в состоянии инициализации до отключения.</span><span class="sxs-lookup"><span data-stu-id="52d32-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="52d32-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="52d32-119">ConnectionBufferSize</span></span>|<span data-ttu-id="52d32-120">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="52d32-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="52d32-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="52d32-121">hostNameComparisonMode</span></span>|<span data-ttu-id="52d32-122">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="52d32-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="52d32-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="52d32-123">manualAddressing</span></span>|<span data-ttu-id="52d32-124">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="52d32-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="52d32-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="52d32-125">maxBufferPoolSize</span></span>|<span data-ttu-id="52d32-126">Возвращает или задает максимальный размер (в байтах) всех пулов буферов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="52d32-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="52d32-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="52d32-127">maxBufferSize</span></span>|<span data-ttu-id="52d32-128">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="52d32-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="52d32-129">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="52d32-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="52d32-130">максаутпутделай</span><span class="sxs-lookup"><span data-stu-id="52d32-130">maxOutputDelay</span></span>|<span data-ttu-id="52d32-131">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="52d32-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="52d32-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="52d32-132">maxPendingAccepts</span></span>|<span data-ttu-id="52d32-133">Возвращает или задает максимальное число каналов, которые служба может ожидать от прослушивателя для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="52d32-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="52d32-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="52d32-134">maxPendingConnections</span></span>|<span data-ttu-id="52d32-135">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="52d32-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="52d32-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="52d32-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="52d32-137">Возвращает и задает максимально допустимый размер сообщения (в байтах), который может быть получен.</span><span class="sxs-lookup"><span data-stu-id="52d32-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="52d32-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="52d32-138">transferMode</span></span>|<span data-ttu-id="52d32-139">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="52d32-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="52d32-140">\<Коннектионпулсеттингс > \<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="52d32-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="52d32-141">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="52d32-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52d32-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52d32-142">Parent Elements</span></span>  
  
|<span data-ttu-id="52d32-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="52d32-143">Element</span></span>|<span data-ttu-id="52d32-144">Описание</span><span class="sxs-lookup"><span data-stu-id="52d32-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52d32-145">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="52d32-145">\<binding></span></span>](bindings.md)|<span data-ttu-id="52d32-146">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="52d32-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52d32-147">Заметки</span><span class="sxs-lookup"><span data-stu-id="52d32-147">Remarks</span></span>  
<span data-ttu-id="52d32-148">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="52d32-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="52d32-149">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="52d32-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="52d32-150">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52d32-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="52d32-151">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="52d32-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d32-152">См. также</span><span class="sxs-lookup"><span data-stu-id="52d32-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="52d32-153">Транспорты</span><span class="sxs-lookup"><span data-stu-id="52d32-153">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="52d32-154">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="52d32-154">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="52d32-155">Привязки</span><span class="sxs-lookup"><span data-stu-id="52d32-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="52d32-156">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="52d32-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="52d32-157">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="52d32-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="52d32-158">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="52d32-158">\<customBinding></span></span>](custombinding.md)
