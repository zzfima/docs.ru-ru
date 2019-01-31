---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 298bf27b171772bb039b11b5e5de70e7d45b061d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258459"
---
# <a name="websocketsettings"></a><span data-ttu-id="4d6a8-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="4d6a8-101">\<webSocketSettings></span></span>
<span data-ttu-id="4d6a8-102">Элемент конфигурации, который служит для задания параметров веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="4d6a8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4d6a8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d6a8-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4d6a8-104">\<bindings></span></span>  
<span data-ttu-id="4d6a8-105">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4d6a8-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6a8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d6a8-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d6a8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d6a8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4d6a8-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d6a8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d6a8-109">Attributes</span></span>  
  
|<span data-ttu-id="4d6a8-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d6a8-110">Attribute</span></span>|<span data-ttu-id="4d6a8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4d6a8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d6a8-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="4d6a8-112">createNotificationOnConnection</span></span>|<span data-ttu-id="4d6a8-113">Определяет, следует ли отправлять уведомления при соединении.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="4d6a8-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="4d6a8-114">disablePayloadMasking</span></span>|<span data-ttu-id="4d6a8-115">Определяет, отключено ли маскирование веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="4d6a8-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="4d6a8-116">keepAliveInterval</span></span>|<span data-ttu-id="4d6a8-117">Определяет интервал поддержки активности канала.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="4d6a8-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="4d6a8-118">maxPendingConnections</span></span>|<span data-ttu-id="4d6a8-119">Определяет максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="4d6a8-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="4d6a8-120">receiveBufferSize</span></span>|<span data-ttu-id="4d6a8-121">Определяет размер буфера приема.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="4d6a8-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="4d6a8-122">sendBufferSize</span></span>|<span data-ttu-id="4d6a8-123">Определяет размер буфера отправки.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="4d6a8-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="4d6a8-124">subProtocol</span></span>|<span data-ttu-id="4d6a8-125">Определяет подпротокол веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="4d6a8-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="4d6a8-126">transportUsage</span></span>|<span data-ttu-id="4d6a8-127">Указывает, когда использовать веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="4d6a8-128">Атрибут transportUsage</span><span class="sxs-lookup"><span data-stu-id="4d6a8-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="4d6a8-129">Значение</span><span class="sxs-lookup"><span data-stu-id="4d6a8-129">Value</span></span>|<span data-ttu-id="4d6a8-130">Описание</span><span class="sxs-lookup"><span data-stu-id="4d6a8-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d6a8-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="4d6a8-131">WhenDuplex</span></span>|<span data-ttu-id="4d6a8-132">Использовать протокол веб-сокета, если контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="4d6a8-133">Всегда</span><span class="sxs-lookup"><span data-stu-id="4d6a8-133">Always</span></span>|<span data-ttu-id="4d6a8-134">Всегда использовать протокол веб-сокетов независимо от контракта.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="4d6a8-135">Никогда</span><span class="sxs-lookup"><span data-stu-id="4d6a8-135">Never</span></span>|<span data-ttu-id="4d6a8-136">Никогда не использовать протокол веб-сокетов.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d6a8-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d6a8-137">Child Elements</span></span>  
 <span data-ttu-id="4d6a8-138">Нет</span><span class="sxs-lookup"><span data-stu-id="4d6a8-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d6a8-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d6a8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="4d6a8-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d6a8-140">Element</span></span>|<span data-ttu-id="4d6a8-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d6a8-142">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4d6a8-142">\<netHttpBinding></span></span>|<span data-ttu-id="4d6a8-143">Определяет привязку NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4d6a8-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d6a8-144">Пример</span><span class="sxs-lookup"><span data-stu-id="4d6a8-144">Example</span></span>  
 <span data-ttu-id="4d6a8-145">В следующем примере показано, как использовать \<webSocketSettings > элемента.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d6a8-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4d6a8-146">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="4d6a8-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="4d6a8-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4d6a8-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4d6a8-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4d6a8-149">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4d6a8-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4d6a8-150">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4d6a8-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
