---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783355"
---
# <a name="peertransport"></a><span data-ttu-id="de26e-101">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="de26e-101">\<peerTransport></span></span>
<span data-ttu-id="de26e-102">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="de26e-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="de26e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="de26e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="de26e-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="de26e-104">\<bindings></span></span>  
<span data-ttu-id="de26e-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="de26e-105">\<customBinding></span></span>  
<span data-ttu-id="de26e-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="de26e-106">\<binding></span></span>  
<span data-ttu-id="de26e-107">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="de26e-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de26e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de26e-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de26e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de26e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="de26e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="de26e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de26e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de26e-111">Attributes</span></span>  
  
|<span data-ttu-id="de26e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="de26e-112">Attribute</span></span>|<span data-ttu-id="de26e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="de26e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de26e-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="de26e-114">listenIpAddress</span></span>|<span data-ttu-id="de26e-115">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="de26e-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="de26e-116">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="de26e-116">The default is `null`.</span></span>|  
|<span data-ttu-id="de26e-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="de26e-117">maxBufferPoolSize</span></span>|<span data-ttu-id="de26e-118">Положительное целое число, указывающее максимальный размер буферного пула.</span><span class="sxs-lookup"><span data-stu-id="de26e-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="de26e-119">Значение по умолчанию — 524288.</span><span class="sxs-lookup"><span data-stu-id="de26e-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="de26e-120">Многие элементы WCF используют буферы.</span><span class="sxs-lookup"><span data-stu-id="de26e-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="de26e-121">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="de26e-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="de26e-122">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="de26e-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="de26e-123">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="de26e-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="de26e-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="de26e-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="de26e-125">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки.</span><span class="sxs-lookup"><span data-stu-id="de26e-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="de26e-126">Отправитель сообщения получает ошибку протокола SOAP, когда размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="de26e-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="de26e-127">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="de26e-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="de26e-128">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="de26e-128">The default is 65536.</span></span>|  
|<span data-ttu-id="de26e-129">порт</span><span class="sxs-lookup"><span data-stu-id="de26e-129">port</span></span>|<span data-ttu-id="de26e-130">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="de26e-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="de26e-131">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="de26e-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="de26e-132">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="de26e-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de26e-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de26e-133">Child Elements</span></span>  
  
|<span data-ttu-id="de26e-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="de26e-134">Element</span></span>|<span data-ttu-id="de26e-135">Описание</span><span class="sxs-lookup"><span data-stu-id="de26e-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de26e-136">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="de26e-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="de26e-137">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="de26e-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="de26e-138">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="de26e-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de26e-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de26e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="de26e-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="de26e-140">Element</span></span>|<span data-ttu-id="de26e-141">Описание</span><span class="sxs-lookup"><span data-stu-id="de26e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de26e-142">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="de26e-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="de26e-143">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="de26e-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de26e-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="de26e-144">Remarks</span></span>  
 <span data-ttu-id="de26e-145">Данный транспорт нельзя использовать с контрактами, имеющими операции запроса-ответа.</span><span class="sxs-lookup"><span data-stu-id="de26e-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de26e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="de26e-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="de26e-147">Транспорты</span><span class="sxs-lookup"><span data-stu-id="de26e-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="de26e-148">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="de26e-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="de26e-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="de26e-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="de26e-150">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="de26e-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="de26e-151">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="de26e-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="de26e-152">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="de26e-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
