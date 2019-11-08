---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736505"
---
# <a name="peertransport"></a><span data-ttu-id="39f83-101">\<Пиртранспорт ></span><span class="sxs-lookup"><span data-stu-id="39f83-101">\<peerTransport></span></span>
<span data-ttu-id="39f83-102">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="39f83-102">Defines a peer transport for a custom binding.</span></span>  
  
<span data-ttu-id="39f83-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39f83-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39f83-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39f83-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39f83-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="39f83-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="39f83-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="39f83-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="39f83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="39f83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="39f83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<пиртранспорт >**</span><span class="sxs-lookup"><span data-stu-id="39f83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f83-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39f83-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39f83-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="39f83-110">Attributes and Elements</span></span>  
 <span data-ttu-id="39f83-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="39f83-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39f83-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="39f83-112">Attributes</span></span>  
  
|<span data-ttu-id="39f83-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="39f83-113">Attribute</span></span>|<span data-ttu-id="39f83-114">Описание</span><span class="sxs-lookup"><span data-stu-id="39f83-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39f83-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="39f83-115">listenIpAddress</span></span>|<span data-ttu-id="39f83-116">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="39f83-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="39f83-117">Значение по умолчанию: `null`.</span><span class="sxs-lookup"><span data-stu-id="39f83-117">The default is `null`.</span></span>|  
|<span data-ttu-id="39f83-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="39f83-118">maxBufferPoolSize</span></span>|<span data-ttu-id="39f83-119">Положительное целое число, указывающее максимальный размер буферного пула.</span><span class="sxs-lookup"><span data-stu-id="39f83-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="39f83-120">Значение по умолчанию — 524288.</span><span class="sxs-lookup"><span data-stu-id="39f83-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="39f83-121">Многие элементы WCF используют буферы.</span><span class="sxs-lookup"><span data-stu-id="39f83-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="39f83-122">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="39f83-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="39f83-123">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="39f83-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="39f83-124">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="39f83-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="39f83-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="39f83-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="39f83-126">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки.</span><span class="sxs-lookup"><span data-stu-id="39f83-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="39f83-127">Отправитель сообщения получает ошибку протокола SOAP, когда размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="39f83-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="39f83-128">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="39f83-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="39f83-129">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="39f83-129">The default is 65536.</span></span>|  
|<span data-ttu-id="39f83-130">порт</span><span class="sxs-lookup"><span data-stu-id="39f83-130">port</span></span>|<span data-ttu-id="39f83-131">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="39f83-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="39f83-132">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="39f83-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="39f83-133">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="39f83-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39f83-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="39f83-134">Child Elements</span></span>  
  
|<span data-ttu-id="39f83-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="39f83-135">Element</span></span>|<span data-ttu-id="39f83-136">Описание</span><span class="sxs-lookup"><span data-stu-id="39f83-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39f83-137">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="39f83-137">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="39f83-138">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="39f83-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="39f83-139">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="39f83-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39f83-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="39f83-140">Parent Elements</span></span>  
  
|<span data-ttu-id="39f83-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="39f83-141">Element</span></span>|<span data-ttu-id="39f83-142">Описание</span><span class="sxs-lookup"><span data-stu-id="39f83-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39f83-143">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="39f83-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="39f83-144">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="39f83-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39f83-145">Заметки</span><span class="sxs-lookup"><span data-stu-id="39f83-145">Remarks</span></span>  
 <span data-ttu-id="39f83-146">Данный транспорт нельзя использовать с контрактами, имеющими операции запроса-ответа.</span><span class="sxs-lookup"><span data-stu-id="39f83-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f83-147">См. также</span><span class="sxs-lookup"><span data-stu-id="39f83-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="39f83-148">Транспорты</span><span class="sxs-lookup"><span data-stu-id="39f83-148">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="39f83-149">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="39f83-149">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="39f83-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="39f83-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="39f83-151">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="39f83-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="39f83-152">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="39f83-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="39f83-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="39f83-153">\<customBinding></span></span>](custombinding.md)
