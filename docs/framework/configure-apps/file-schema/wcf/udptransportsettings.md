---
title: '&lt;udpTransportSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88b38fc7c67c404446000ca79d2c6191bfc7eed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltudptransportsettingsgt"></a><span data-ttu-id="4f223-102">&lt;udpTransportSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="4f223-102">&lt;udpTransportSettings&gt;</span></span>
<span data-ttu-id="4f223-103">Этот элемент конфигурации предоставляет параметры транспорта UDP для [ \<точка udpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md).</span><span class="sxs-lookup"><span data-stu-id="4f223-103">This configuration element exposes UDP transport settings for [\<udpDiscoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md).</span></span>  
  
<span data-ttu-id="4f223-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4f223-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f223-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4f223-105">\<standardEndpoints></span></span>  
<span data-ttu-id="4f223-106">\<точка udpDiscoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="4f223-106">\<udpDiscoveryEndpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f223-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f223-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer" 
                              maxBufferPoolSize="Integer" 
                              maxMulticastRetransmitCount="Integer" 
                              maxPendingMessageCount="Integer" 
                              maxReceivedMessageSize="Integer" 
                              maxUnicastRetransmitCount="Integer" 
                              multicastInterfaceId="String" 
                              socketReceiveBufferSize="Integer" 
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f223-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f223-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f223-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f223-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f223-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f223-110">Attributes</span></span>  
  
|<span data-ttu-id="4f223-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4f223-111">Attribute</span></span>|<span data-ttu-id="4f223-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4f223-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f223-113">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="4f223-113">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="4f223-114">Целое число, указывающее максимальное количество хэшей сообщений, используемых транспортом для идентификации повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="4f223-114">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="4f223-115">Обнаружение повторяющихся сообщений выполняется на уровне TransportManager.</span><span class="sxs-lookup"><span data-stu-id="4f223-115">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="4f223-116">Если этому свойству задать значение 0, обнаружение повторяющихся сообщений будет отключено.</span><span class="sxs-lookup"><span data-stu-id="4f223-116">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="4f223-117">Этот атрибут позволяет системным администраторам и разработчикам выключать алгоритмы обнаружения повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="4f223-117">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="4f223-118">Это полезно, если требуется реализовать собственный алгоритм обнаружения повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="4f223-118">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="4f223-119">Значение по умолчанию — 4112.</span><span class="sxs-lookup"><span data-stu-id="4f223-119">The default is 4112.</span></span>|  
|<span data-ttu-id="4f223-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="4f223-120">maxBufferPoolSize</span></span>|<span data-ttu-id="4f223-121">Целое число, задающее максимальный размер буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="4f223-121">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="4f223-122">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="4f223-122">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="4f223-123">Целое число, задающее максимальное число отправок сообщения (помимо первой отправки).</span><span class="sxs-lookup"><span data-stu-id="4f223-123">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="4f223-124">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="4f223-124">The default is 2.</span></span>|  
|<span data-ttu-id="4f223-125">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="4f223-125">maxPendingMessageCount</span></span>|<span data-ttu-id="4f223-126">Целое число, задающее для отдельно взятого экземпляра канала максимальное число сообщений, полученных, но еще не удаленных из очереди InputQueue.</span><span class="sxs-lookup"><span data-stu-id="4f223-126">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="4f223-127">Если очередь InputQueue достигает верхнего предела числа ожидающих сообщений, сообщение будет удалено.</span><span class="sxs-lookup"><span data-stu-id="4f223-127">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="4f223-128">Значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="4f223-128">The default is 32.</span></span>|  
|<span data-ttu-id="4f223-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="4f223-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="4f223-130">Целое число, указывающее максимальный размер сообщения, которое может быть обработано привязкой.</span><span class="sxs-lookup"><span data-stu-id="4f223-130">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="4f223-131">Значение по умолчанию — 65507.</span><span class="sxs-lookup"><span data-stu-id="4f223-131">The default value is 65507.</span></span>|  
|<span data-ttu-id="4f223-132">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="4f223-132">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="4f223-133">Целое число, задающее максимальное число отправок сообщения (помимо первой отправки).</span><span class="sxs-lookup"><span data-stu-id="4f223-133">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="4f223-134">Если сообщение отправлено по адресу одноадресной рассылки и получено ответное сообщение с соответствующим заголовком RelatesTo, повторная передача может завершиться рано (до того, как будет повторно отправлено заданное число сообщений).</span><span class="sxs-lookup"><span data-stu-id="4f223-134">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="4f223-135">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="4f223-135">The default value is 1.</span></span>|  
|<span data-ttu-id="4f223-136">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="4f223-136">multicastInterfaceId</span></span>|<span data-ttu-id="4f223-137">Строка, служащая уникальным идентификатором сетевого адаптера, который должен использоваться при отправке и получении многоадресного трафика на многосетевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4f223-137">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="4f223-138">Во время выполнения транспорт использует это значение атрибута для поиска индекса интерфейса, который, в свою очередь, используется для установки параметров сокета `IP_MULTICAST_IF` и `IPV6_MULTICAST_IF`.</span><span class="sxs-lookup"><span data-stu-id="4f223-138">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="4f223-139">Этот же индекс интерфейса, если это применимо, используется при присоединении к многоадресной группе.</span><span class="sxs-lookup"><span data-stu-id="4f223-139">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="4f223-140">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="4f223-140">The default value is `null`.</span></span>|  
|<span data-ttu-id="4f223-141">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="4f223-141">socketReceiveBufferSize</span></span>|<span data-ttu-id="4f223-142">Целое число, задающее максимальный размер буфера получения в базовом сокете WinSock.</span><span class="sxs-lookup"><span data-stu-id="4f223-142">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="4f223-143">Пользователь канала получения может использовать этот атрибут на привязке для управления поведением системы при получении данных.</span><span class="sxs-lookup"><span data-stu-id="4f223-143">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="4f223-144">Например, если приложение получает максимальное количество входящих сообщений WCF, то использование большего значения для этого атрибута позволит сообщениям накапливаться в буфере WinSock в ожидании обработки со стороны приложения.</span><span class="sxs-lookup"><span data-stu-id="4f223-144">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="4f223-145">А использование меньшего значения в схожей ситуации приведет к удалению сообщений. Этот атрибут открывает доступ к базовому параметру сокета WinSock `SO_RCVBUF`. Значение этого атрибута должно быть, как минимум, равно размеру `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="4f223-145">Using a lower value in the same situation would result in messages getting dropped.This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="4f223-146">Если задать атрибуту значение, меньшее, чем `maxReceivedMessageSize`, то во время выполнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="4f223-146">Setting it to a value smaller than the `maxReceivedMessageSize` will result in runtime exception.</span></span><br /><br /> <span data-ttu-id="4f223-147">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="4f223-147">The default value is 65536.</span></span>|  
|<span data-ttu-id="4f223-148">timeToLive</span><span class="sxs-lookup"><span data-stu-id="4f223-148">timeToLive</span></span>|<span data-ttu-id="4f223-149">Целое число, указывающее количество прыжков между сетевыми сегментами, которые может выполнить многоадресный пакет.</span><span class="sxs-lookup"><span data-stu-id="4f223-149">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="4f223-150">Этот атрибут предоставляет функции, связанные с параметрами сокета `IP_MULTICAST_TTL` и `IP_TTL`.</span><span class="sxs-lookup"><span data-stu-id="4f223-150">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="4f223-151">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="4f223-151">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f223-152">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f223-152">Child Elements</span></span>  
 <span data-ttu-id="4f223-153">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4f223-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f223-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f223-154">Parent Elements</span></span>  
  
|<span data-ttu-id="4f223-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f223-155">Element</span></span>|<span data-ttu-id="4f223-156">Описание:</span><span class="sxs-lookup"><span data-stu-id="4f223-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f223-157">\<точка udpDiscoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="4f223-157">\<udpDiscoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|<span data-ttu-id="4f223-158">Стандартная конечная точка, имеющая фиксированный контракт обнаружения и транспортную привязку UDP.</span><span class="sxs-lookup"><span data-stu-id="4f223-158">A standard endpoint that has fixed discovery contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f223-159">См. также</span><span class="sxs-lookup"><span data-stu-id="4f223-159">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>
