---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 134a233a337c40d21f7547fe385ec788cef2165b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150062"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="d927c-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="d927c-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="d927c-103">Элемент конфигурации, который служит для задания параметров веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="d927c-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="d927c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d927c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d927c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d927c-105">\<bindings></span></span>  
<span data-ttu-id="d927c-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d927c-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d927c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d927c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d927c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d927c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d927c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d927c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d927c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d927c-110">Attributes</span></span>  
  
|<span data-ttu-id="d927c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d927c-111">Attribute</span></span>|<span data-ttu-id="d927c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d927c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d927c-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="d927c-113">createNotificationOnConnection</span></span>|<span data-ttu-id="d927c-114">Определяет, следует ли отправлять уведомления при соединении.</span><span class="sxs-lookup"><span data-stu-id="d927c-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="d927c-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="d927c-115">disablePayloadMasking</span></span>|<span data-ttu-id="d927c-116">Определяет, отключено ли маскирование веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="d927c-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="d927c-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="d927c-117">keepAliveInterval</span></span>|<span data-ttu-id="d927c-118">Определяет интервал поддержки активности канала.</span><span class="sxs-lookup"><span data-stu-id="d927c-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="d927c-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d927c-119">maxPendingConnections</span></span>|<span data-ttu-id="d927c-120">Определяет максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="d927c-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d927c-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="d927c-121">receiveBufferSize</span></span>|<span data-ttu-id="d927c-122">Определяет размер буфера приема.</span><span class="sxs-lookup"><span data-stu-id="d927c-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="d927c-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="d927c-123">sendBufferSize</span></span>|<span data-ttu-id="d927c-124">Определяет размер буфера отправки.</span><span class="sxs-lookup"><span data-stu-id="d927c-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="d927c-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="d927c-125">subProtocol</span></span>|<span data-ttu-id="d927c-126">Определяет подпротокол веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="d927c-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="d927c-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="d927c-127">transportUsage</span></span>|<span data-ttu-id="d927c-128">Указывает, когда использовать веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="d927c-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="d927c-129">Атрибут transportUsage</span><span class="sxs-lookup"><span data-stu-id="d927c-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="d927c-130">Значение</span><span class="sxs-lookup"><span data-stu-id="d927c-130">Value</span></span>|<span data-ttu-id="d927c-131">Описание</span><span class="sxs-lookup"><span data-stu-id="d927c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d927c-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="d927c-132">WhenDuplex</span></span>|<span data-ttu-id="d927c-133">Использовать протокол веб-сокета, если контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="d927c-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="d927c-134">Всегда</span><span class="sxs-lookup"><span data-stu-id="d927c-134">Always</span></span>|<span data-ttu-id="d927c-135">Всегда использовать протокол веб-сокетов независимо от контракта.</span><span class="sxs-lookup"><span data-stu-id="d927c-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="d927c-136">Никогда</span><span class="sxs-lookup"><span data-stu-id="d927c-136">Never</span></span>|<span data-ttu-id="d927c-137">Никогда не использовать протокол веб-сокетов.</span><span class="sxs-lookup"><span data-stu-id="d927c-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d927c-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d927c-138">Child Elements</span></span>  
 <span data-ttu-id="d927c-139">Нет</span><span class="sxs-lookup"><span data-stu-id="d927c-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d927c-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d927c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="d927c-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="d927c-141">Element</span></span>|<span data-ttu-id="d927c-142">Описание:</span><span class="sxs-lookup"><span data-stu-id="d927c-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d927c-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d927c-143">\<netHttpBinding></span></span>|<span data-ttu-id="d927c-144">Определяет привязку NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d927c-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d927c-145">Пример</span><span class="sxs-lookup"><span data-stu-id="d927c-145">Example</span></span>  
 <span data-ttu-id="d927c-146">В следующем примере показано, как использовать \<webSocketSettings > элемента.</span><span class="sxs-lookup"><span data-stu-id="d927c-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d927c-147">См. также</span><span class="sxs-lookup"><span data-stu-id="d927c-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="d927c-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="d927c-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d927c-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d927c-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d927c-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d927c-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="d927c-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d927c-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
