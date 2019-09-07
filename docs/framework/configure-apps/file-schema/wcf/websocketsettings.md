---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 80784f40130e572ae374bd9b26e701360dbfcaa5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399137"
---
# <a name="websocketsettings"></a><span data-ttu-id="cb11b-101">\<Вебсоккетсеттингс ></span><span class="sxs-lookup"><span data-stu-id="cb11b-101">\<webSocketSettings></span></span>
<span data-ttu-id="cb11b-102">Элемент конфигурации, который служит для задания параметров веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="cb11b-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="cb11b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb11b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cb11b-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cb11b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cb11b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cb11b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cb11b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cb11b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="cb11b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="cb11b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cb11b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Вебсоккетсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="cb11b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb11b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb11b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb11b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb11b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb11b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb11b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb11b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb11b-112">Attributes</span></span>  
  
|<span data-ttu-id="cb11b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cb11b-113">Attribute</span></span>|<span data-ttu-id="cb11b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cb11b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb11b-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="cb11b-115">createNotificationOnConnection</span></span>|<span data-ttu-id="cb11b-116">Определяет, следует ли отправлять уведомления при соединении.</span><span class="sxs-lookup"><span data-stu-id="cb11b-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="cb11b-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="cb11b-117">disablePayloadMasking</span></span>|<span data-ttu-id="cb11b-118">Определяет, отключено ли маскирование веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="cb11b-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="cb11b-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="cb11b-119">keepAliveInterval</span></span>|<span data-ttu-id="cb11b-120">Определяет интервал поддержки активности канала.</span><span class="sxs-lookup"><span data-stu-id="cb11b-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="cb11b-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="cb11b-121">maxPendingConnections</span></span>|<span data-ttu-id="cb11b-122">Определяет максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="cb11b-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="cb11b-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="cb11b-123">receiveBufferSize</span></span>|<span data-ttu-id="cb11b-124">Определяет размер буфера приема.</span><span class="sxs-lookup"><span data-stu-id="cb11b-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="cb11b-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="cb11b-125">sendBufferSize</span></span>|<span data-ttu-id="cb11b-126">Определяет размер буфера отправки.</span><span class="sxs-lookup"><span data-stu-id="cb11b-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="cb11b-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="cb11b-127">subProtocol</span></span>|<span data-ttu-id="cb11b-128">Определяет подпротокол веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="cb11b-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="cb11b-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="cb11b-129">transportUsage</span></span>|<span data-ttu-id="cb11b-130">Указывает, когда использовать веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="cb11b-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="cb11b-131">Атрибут transportUsage</span><span class="sxs-lookup"><span data-stu-id="cb11b-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="cb11b-132">Значение</span><span class="sxs-lookup"><span data-stu-id="cb11b-132">Value</span></span>|<span data-ttu-id="cb11b-133">Описание</span><span class="sxs-lookup"><span data-stu-id="cb11b-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb11b-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="cb11b-134">WhenDuplex</span></span>|<span data-ttu-id="cb11b-135">Использовать протокол веб-сокета, если контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="cb11b-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="cb11b-136">Всегда</span><span class="sxs-lookup"><span data-stu-id="cb11b-136">Always</span></span>|<span data-ttu-id="cb11b-137">Всегда использовать протокол веб-сокетов независимо от контракта.</span><span class="sxs-lookup"><span data-stu-id="cb11b-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="cb11b-138">Никогда</span><span class="sxs-lookup"><span data-stu-id="cb11b-138">Never</span></span>|<span data-ttu-id="cb11b-139">Никогда не использовать протокол веб-сокетов.</span><span class="sxs-lookup"><span data-stu-id="cb11b-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb11b-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb11b-140">Child Elements</span></span>  
 <span data-ttu-id="cb11b-141">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="cb11b-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb11b-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb11b-142">Parent Elements</span></span>  
  
|<span data-ttu-id="cb11b-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb11b-143">Element</span></span>|<span data-ttu-id="cb11b-144">Описание</span><span class="sxs-lookup"><span data-stu-id="cb11b-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb11b-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cb11b-145">\<netHttpBinding></span></span>|<span data-ttu-id="cb11b-146">Определяет привязку NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cb11b-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb11b-147">Пример</span><span class="sxs-lookup"><span data-stu-id="cb11b-147">Example</span></span>  
 <span data-ttu-id="cb11b-148">В следующем примере показано, \<как использовать элемент > вебсоккетсеттингс.</span><span class="sxs-lookup"><span data-stu-id="cb11b-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cb11b-149">См. также</span><span class="sxs-lookup"><span data-stu-id="cb11b-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="cb11b-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="cb11b-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cb11b-151">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cb11b-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cb11b-152">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cb11b-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cb11b-153">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cb11b-153">\<binding></span></span>](../../../misc/binding.md)
