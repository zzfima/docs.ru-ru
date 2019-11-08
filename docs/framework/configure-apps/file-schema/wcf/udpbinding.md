---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 95ce89aabb400c01002799fd8251383a2e5dd4c2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732704"
---
# <a name="udpbinding"></a><span data-ttu-id="8de3b-101">\<Удпбиндинг ></span><span class="sxs-lookup"><span data-stu-id="8de3b-101">\<udpBinding></span></span>
<span data-ttu-id="8de3b-102">Элемент конфигурации, который используется для настройки привязки <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
<span data-ttu-id="8de3b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8de3b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8de3b-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8de3b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8de3b-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8de3b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8de3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удпбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="8de3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de3b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8de3b-107">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8de3b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8de3b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8de3b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8de3b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8de3b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8de3b-110">Attributes</span></span>  
  
|<span data-ttu-id="8de3b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8de3b-111">Attribute</span></span>|<span data-ttu-id="8de3b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8de3b-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8de3b-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="8de3b-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8de3b-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8de3b-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8de3b-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="8de3b-116">Целочисленное значение, указывающее длину журнала повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="8de3b-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="8de3b-117">Целое значение, определяющее максимальный объем памяти, выделяемой для диспетчера буферов сообщений, получающих сообщения из канала.</span><span class="sxs-lookup"><span data-stu-id="8de3b-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="8de3b-118">Значение по умолчанию - 524 288 (0x80 000) байт.</span><span class="sxs-lookup"><span data-stu-id="8de3b-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="8de3b-119">Целое значение, указывающее максимальный размер (в байтах) буфера, хранящего сообщения во время их обработки для конечной точки, настроенной с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="8de3b-120">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="8de3b-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="8de3b-121">Целочисленное значение, задающее для отдельно взятого экземпляра канала максимальное число сообщений, полученных, но еще не удаленных из входной очереди.</span><span class="sxs-lookup"><span data-stu-id="8de3b-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="8de3b-122">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="8de3b-123">Отправитель получает ошибку SOAP, если размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="8de3b-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="8de3b-124">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="8de3b-125">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="8de3b-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="8de3b-126">Целое число, указывающее максимальное число сообщений для пересылки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="8de3b-127">Целочисленное значение, указывающее идентификатор интерфейса для многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="8de3b-128">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8de3b-129">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8de3b-130">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8de3b-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8de3b-131">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="8de3b-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8de3b-132">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="8de3b-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8de3b-133">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8de3b-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8de3b-134">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="8de3b-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8de3b-135">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8de3b-136">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8de3b-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8de3b-137">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="8de3b-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8de3b-138">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8de3b-139">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="8de3b-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8de3b-140">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8de3b-141">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8de3b-142">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8de3b-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="8de3b-143">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="8de3b-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="8de3b-144">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8de3b-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8de3b-145">-BigEndianUnicode: Юникод байтов Encoding.</span><span class="sxs-lookup"><span data-stu-id="8de3b-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="8de3b-146">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="8de3b-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="8de3b-147">-UTF8:8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="8de3b-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="8de3b-148">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="8de3b-148">The default is UTF8.</span></span> <span data-ttu-id="8de3b-149">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="8de3b-150">Значение интервала времени, указывающее срок жизни для привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8de3b-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8de3b-151">Child Elements</span></span>  
  
|<span data-ttu-id="8de3b-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="8de3b-152">Element</span></span>|<span data-ttu-id="8de3b-153">Описание</span><span class="sxs-lookup"><span data-stu-id="8de3b-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8de3b-154">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8de3b-154">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="8de3b-155">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8de3b-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8de3b-156">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8de3b-157">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8de3b-157">Parent Elements</span></span>  
  
|<span data-ttu-id="8de3b-158">Элемент</span><span class="sxs-lookup"><span data-stu-id="8de3b-158">Element</span></span>|<span data-ttu-id="8de3b-159">Описание</span><span class="sxs-lookup"><span data-stu-id="8de3b-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8de3b-160">привязки\<</span><span class="sxs-lookup"><span data-stu-id="8de3b-160">\<bindings></span></span>](bindings.md)|<span data-ttu-id="8de3b-161">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="8de3b-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8de3b-162">Заметки</span><span class="sxs-lookup"><span data-stu-id="8de3b-162">Remarks</span></span>  
 <span data-ttu-id="8de3b-163">UdpBinding позволяет службам WCF обмениваться данными через транспорт определяемой пользователем процедуры.</span><span class="sxs-lookup"><span data-stu-id="8de3b-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="8de3b-164">Он позволяет выполнять обмен сообщениями «пожара и забыть», когда клиент отправляет сообщение службе и не ожидает ответа.</span><span class="sxs-lookup"><span data-stu-id="8de3b-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8de3b-165">Пример</span><span class="sxs-lookup"><span data-stu-id="8de3b-165">Example</span></span>  
 <span data-ttu-id="8de3b-166">В следующем примере показано, как настроить <xref:System.ServiceModel.UdpBinding> с помощью элемента <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="8de3b-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>
  <binding  closeTimeout="00:10:00"
            duplicateMessageHistoryLength="100"
            maxBufferPoolSize="100"
            maxPendingMessagesTotalSize="100000"
            maxReceivedMessageSize="65536"
            maxRetransmitCount="10"
            multicastInterfaceId="00000"
            name="myUdpBinding"
            openTimeout="00:10:00"
            receiveTimeout="00:10:00"
            sendTimeout="00:10:00"
            textEncoding="utf-8"
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="8de3b-167">См. также</span><span class="sxs-lookup"><span data-stu-id="8de3b-167">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="8de3b-168">Привязки</span><span class="sxs-lookup"><span data-stu-id="8de3b-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8de3b-169">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="8de3b-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8de3b-170">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="8de3b-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8de3b-171">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="8de3b-171">\<binding></span></span>](bindings.md)
