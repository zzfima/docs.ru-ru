---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 00c6bc45f06d97d4f95bd6be1515d16141be4e1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565921"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="fc11b-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="fc11b-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="fc11b-103">Элемент конфигурации, который служит для задания параметров веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="fc11b-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="fc11b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc11b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc11b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="fc11b-105">\<bindings></span></span>  
<span data-ttu-id="fc11b-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fc11b-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc11b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc11b-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc11b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc11b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fc11b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc11b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc11b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc11b-110">Attributes</span></span>  
  
|<span data-ttu-id="fc11b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fc11b-111">Attribute</span></span>|<span data-ttu-id="fc11b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fc11b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc11b-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="fc11b-113">createNotificationOnConnection</span></span>|<span data-ttu-id="fc11b-114">Определяет, следует ли отправлять уведомления при соединении.</span><span class="sxs-lookup"><span data-stu-id="fc11b-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="fc11b-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="fc11b-115">disablePayloadMasking</span></span>|<span data-ttu-id="fc11b-116">Определяет, отключено ли маскирование веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="fc11b-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="fc11b-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="fc11b-117">keepAliveInterval</span></span>|<span data-ttu-id="fc11b-118">Определяет интервал поддержки активности канала.</span><span class="sxs-lookup"><span data-stu-id="fc11b-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="fc11b-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="fc11b-119">maxPendingConnections</span></span>|<span data-ttu-id="fc11b-120">Определяет максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="fc11b-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="fc11b-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="fc11b-121">receiveBufferSize</span></span>|<span data-ttu-id="fc11b-122">Определяет размер буфера приема.</span><span class="sxs-lookup"><span data-stu-id="fc11b-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="fc11b-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="fc11b-123">sendBufferSize</span></span>|<span data-ttu-id="fc11b-124">Определяет размер буфера отправки.</span><span class="sxs-lookup"><span data-stu-id="fc11b-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="fc11b-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="fc11b-125">subProtocol</span></span>|<span data-ttu-id="fc11b-126">Определяет подпротокол веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="fc11b-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="fc11b-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="fc11b-127">transportUsage</span></span>|<span data-ttu-id="fc11b-128">Указывает, когда использовать веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="fc11b-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="fc11b-129">Атрибут transportUsage</span><span class="sxs-lookup"><span data-stu-id="fc11b-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="fc11b-130">Значение</span><span class="sxs-lookup"><span data-stu-id="fc11b-130">Value</span></span>|<span data-ttu-id="fc11b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="fc11b-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc11b-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="fc11b-132">WhenDuplex</span></span>|<span data-ttu-id="fc11b-133">Использовать протокол веб-сокета, если контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="fc11b-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="fc11b-134">Всегда</span><span class="sxs-lookup"><span data-stu-id="fc11b-134">Always</span></span>|<span data-ttu-id="fc11b-135">Всегда использовать протокол веб-сокетов независимо от контракта.</span><span class="sxs-lookup"><span data-stu-id="fc11b-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="fc11b-136">Никогда</span><span class="sxs-lookup"><span data-stu-id="fc11b-136">Never</span></span>|<span data-ttu-id="fc11b-137">Никогда не использовать протокол веб-сокетов.</span><span class="sxs-lookup"><span data-stu-id="fc11b-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc11b-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc11b-138">Child Elements</span></span>  
 <span data-ttu-id="fc11b-139">Нет</span><span class="sxs-lookup"><span data-stu-id="fc11b-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc11b-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc11b-140">Parent Elements</span></span>  
  
|<span data-ttu-id="fc11b-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc11b-141">Element</span></span>|<span data-ttu-id="fc11b-142">Описание:</span><span class="sxs-lookup"><span data-stu-id="fc11b-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc11b-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fc11b-143">\<netHttpBinding></span></span>|<span data-ttu-id="fc11b-144">Определяет привязку NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fc11b-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc11b-145">Пример</span><span class="sxs-lookup"><span data-stu-id="fc11b-145">Example</span></span>  
 <span data-ttu-id="fc11b-146">В следующем примере показано, как использовать \<webSocketSettings > элемента.</span><span class="sxs-lookup"><span data-stu-id="fc11b-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc11b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="fc11b-147">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="fc11b-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="fc11b-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fc11b-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="fc11b-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fc11b-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="fc11b-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fc11b-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="fc11b-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
