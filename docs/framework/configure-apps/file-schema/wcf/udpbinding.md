---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: b0945169c5fb237bbc937fca54c4d321156cd2dd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269514"
---
# <a name="udpbinding"></a><span data-ttu-id="36b2a-101">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="36b2a-101">\<udpBinding></span></span>
<span data-ttu-id="36b2a-102">Элемент конфигурации, который используется для настройки привязки <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="36b2a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36b2a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="36b2a-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="36b2a-104">\<bindings></span></span>  
<span data-ttu-id="36b2a-105">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="36b2a-105">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b2a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36b2a-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36b2a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36b2a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="36b2a-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="36b2a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36b2a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36b2a-109">Attributes</span></span>  
  
|<span data-ttu-id="36b2a-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="36b2a-110">Attribute</span></span>|<span data-ttu-id="36b2a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="36b2a-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="36b2a-112">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="36b2a-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="36b2a-113">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36b2a-114">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36b2a-114">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="36b2a-115">Целочисленное значение, указывающее длину журнала повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="36b2a-115">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="36b2a-116">Целое значение, определяющее максимальный объем памяти, выделяемой для диспетчера буферов сообщений, получающих сообщения из канала.</span><span class="sxs-lookup"><span data-stu-id="36b2a-116">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="36b2a-117">Значение по умолчанию - 524 288 (0x80 000) байт.</span><span class="sxs-lookup"><span data-stu-id="36b2a-117">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="36b2a-118">Целое значение, указывающее максимальный размер (в байтах) буфера, хранящего сообщения во время их обработки для конечной точки, настроенной с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-118">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="36b2a-119">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="36b2a-119">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="36b2a-120">Целочисленное значение, задающее для отдельно взятого экземпляра канала максимальное число сообщений, полученных, но еще не удаленных из входной очереди.</span><span class="sxs-lookup"><span data-stu-id="36b2a-120">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="36b2a-121">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-121">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="36b2a-122">Отправитель получает ошибку SOAP, если размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="36b2a-122">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="36b2a-123">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-123">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="36b2a-124">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="36b2a-124">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="36b2a-125">Целое число, указывающее максимальное число сообщений для пересылки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-125">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="36b2a-126">Целочисленное значение, указывающее идентификатор интерфейса для многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-126">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="36b2a-127">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-127">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="36b2a-128">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-128">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="36b2a-129">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="36b2a-129">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="36b2a-130">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="36b2a-130">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="36b2a-131">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="36b2a-131">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="36b2a-132">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="36b2a-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="36b2a-133">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="36b2a-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="36b2a-134">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36b2a-135">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36b2a-135">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="36b2a-136">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="36b2a-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="36b2a-137">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36b2a-138">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="36b2a-138">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="36b2a-139">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-139">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="36b2a-140">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-140">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36b2a-141">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36b2a-141">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="36b2a-142">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="36b2a-142">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="36b2a-143">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="36b2a-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="36b2a-144">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="36b2a-144">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="36b2a-145">-Юникод. 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="36b2a-145">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="36b2a-146">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="36b2a-146">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="36b2a-147">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="36b2a-147">The default is UTF8.</span></span> <span data-ttu-id="36b2a-148">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-148">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="36b2a-149">Значение интервала времени, указывающее срок жизни для привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-149">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36b2a-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36b2a-150">Child Elements</span></span>  
  
|<span data-ttu-id="36b2a-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="36b2a-151">Element</span></span>|<span data-ttu-id="36b2a-152">Описание:</span><span class="sxs-lookup"><span data-stu-id="36b2a-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36b2a-153">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="36b2a-153">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="36b2a-154">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="36b2a-154">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="36b2a-155">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-155">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36b2a-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36b2a-156">Parent Elements</span></span>  
  
|<span data-ttu-id="36b2a-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="36b2a-157">Element</span></span>|<span data-ttu-id="36b2a-158">Описание:</span><span class="sxs-lookup"><span data-stu-id="36b2a-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36b2a-159">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="36b2a-159">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="36b2a-160">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="36b2a-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36b2a-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="36b2a-161">Remarks</span></span>  
 <span data-ttu-id="36b2a-162">UdpBinding позволяет службам WCF обмениваться данными через транспорт определяемой пользователем процедуры.</span><span class="sxs-lookup"><span data-stu-id="36b2a-162">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="36b2a-163">Он позволяет «отправить и забыть» обмен сообщениями, когда клиент отправляет сообщение службе и не ожидает ответа.</span><span class="sxs-lookup"><span data-stu-id="36b2a-163">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36b2a-164">Пример</span><span class="sxs-lookup"><span data-stu-id="36b2a-164">Example</span></span>  
 <span data-ttu-id="36b2a-165">В следующем примере показано, как настроить <xref:System.ServiceModel.UdpBinding> с помощью элемента <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="36b2a-165">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36b2a-166">См. также</span><span class="sxs-lookup"><span data-stu-id="36b2a-166">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="36b2a-167">Привязки</span><span class="sxs-lookup"><span data-stu-id="36b2a-167">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="36b2a-168">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="36b2a-168">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="36b2a-169">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="36b2a-169">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="36b2a-170">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="36b2a-170">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
