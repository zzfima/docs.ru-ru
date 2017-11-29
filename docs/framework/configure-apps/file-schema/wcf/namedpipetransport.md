---
title: '&lt;namedPipeTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d2d4be08012c1d33341ddd17713903782027c31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="a134b-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="a134b-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="a134b-103">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="a134b-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="a134b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a134b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a134b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a134b-105">\<bindings></span></span>  
<span data-ttu-id="a134b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a134b-106">\<customBinding></span></span>  
<span data-ttu-id="a134b-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a134b-107">\<binding></span></span>  
<span data-ttu-id="a134b-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="a134b-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a134b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a134b-109">Syntax</span></span>  
  
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
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a134b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a134b-110">Attributes and Elements</span></span>  
<span data-ttu-id="a134b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a134b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a134b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a134b-112">Attributes</span></span>  
<span data-ttu-id="a134b-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a134b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a134b-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a134b-114">Child Elements</span></span>  
  
|<span data-ttu-id="a134b-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a134b-115">Element</span></span>|<span data-ttu-id="a134b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a134b-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a134b-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="a134b-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="a134b-118">Возвращает или задает <xref:System.TimeSpan> , определяет максимальное время, канал может находиться в состоянии инициализации перед отключением.</span><span class="sxs-lookup"><span data-stu-id="a134b-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="a134b-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="a134b-119">ConnectionBufferSize</span></span>|<span data-ttu-id="a134b-120">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="a134b-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="a134b-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="a134b-121">hostNameComparisonMode</span></span>|<span data-ttu-id="a134b-122">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="a134b-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="a134b-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="a134b-123">manualAddressing</span></span>|<span data-ttu-id="a134b-124">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="a134b-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="a134b-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="a134b-125">maxBufferPoolSize</span></span>|<span data-ttu-id="a134b-126">Возвращает или задает максимальный размер в байтах, буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="a134b-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="a134b-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="a134b-127">maxBufferSize</span></span>|<span data-ttu-id="a134b-128">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="a134b-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="a134b-129">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="a134b-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="a134b-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="a134b-130">maxOutputDelay</span></span>|<span data-ttu-id="a134b-131">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="a134b-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="a134b-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="a134b-132">maxPendingAccepts</span></span>|<span data-ttu-id="a134b-133">Возвращает или задает максимальное число каналов, служба может иметь ожидание прослушивателя для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="a134b-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="a134b-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="a134b-134">maxPendingConnections</span></span>|<span data-ttu-id="a134b-135">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="a134b-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="a134b-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="a134b-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="a134b-137">Возвращает и задает максимально допустимый размер сообщения, в байтах, которые могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="a134b-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="a134b-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="a134b-138">transferMode</span></span>|<span data-ttu-id="a134b-139">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="a134b-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="a134b-140">\<connectionPoolSettings > для \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="a134b-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="a134b-141">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="a134b-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a134b-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a134b-142">Parent Elements</span></span>  
  
|<span data-ttu-id="a134b-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="a134b-143">Element</span></span>|<span data-ttu-id="a134b-144">Описание</span><span class="sxs-lookup"><span data-stu-id="a134b-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a134b-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a134b-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a134b-146">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a134b-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a134b-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="a134b-147">Remarks</span></span>  
<span data-ttu-id="a134b-148">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="a134b-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="a134b-149">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="a134b-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="a134b-150">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a134b-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="a134b-151">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a134b-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a134b-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a134b-152">See Also</span></span>  
<span data-ttu-id="a134b-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span><span class="sxs-lookup"><span data-stu-id="a134b-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span></span>   
<span data-ttu-id="a134b-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="a134b-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span></span>   
<span data-ttu-id="a134b-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="a134b-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span></span>   
<span data-ttu-id="a134b-156"><xref:System.ServiceModel.Channels.CustomBinding></span><span class="sxs-lookup"><span data-stu-id="a134b-156"><xref:System.ServiceModel.Channels.CustomBinding></span></span>   
<span data-ttu-id="a134b-157">[Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="a134b-157">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="a134b-158">[Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="a134b-158">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="a134b-159">[Привязки](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="a134b-159">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="a134b-160">[Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="a134b-160">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="a134b-161">[Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="a134b-161">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="a134b-162">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a134b-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
