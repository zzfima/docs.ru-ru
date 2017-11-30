---
title: '&lt;udpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8eb4d28885308c400c445ae71019373ec92ed27a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="8eb12-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8eb12-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="8eb12-103">Элемент конфигурации, который используется для настройки привязки <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="8eb12-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8eb12-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8eb12-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8eb12-105">\<bindings></span></span>  
<span data-ttu-id="8eb12-106">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="8eb12-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb12-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eb12-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8eb12-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8eb12-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8eb12-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8eb12-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8eb12-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8eb12-110">Attributes</span></span>  
  
|<span data-ttu-id="8eb12-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8eb12-111">Attribute</span></span>|<span data-ttu-id="8eb12-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb12-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8eb12-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="8eb12-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8eb12-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8eb12-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8eb12-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="8eb12-116">Целочисленное значение, указывающее длину журнала повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="8eb12-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="8eb12-117">Целое значение, определяющее максимальный объем памяти, выделяемой для диспетчера буферов сообщений, получающих сообщения из канала.</span><span class="sxs-lookup"><span data-stu-id="8eb12-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="8eb12-118">Значение по умолчанию - 524 288 (0x80 000) байт.</span><span class="sxs-lookup"><span data-stu-id="8eb12-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="8eb12-119">Целое значение, указывающее максимальный размер (в байтах) буфера, хранящего сообщения во время их обработки для конечной точки, настроенной с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="8eb12-120">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="8eb12-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="8eb12-121">Целочисленное значение, задающее для отдельно взятого экземпляра канала максимальное число сообщений, полученных, но еще не удаленных из входной очереди.</span><span class="sxs-lookup"><span data-stu-id="8eb12-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="8eb12-122">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="8eb12-123">Отправитель получает ошибку SOAP, если размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="8eb12-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="8eb12-124">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="8eb12-125">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="8eb12-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="8eb12-126">Целое число, указывающее максимальное число сообщений для пересылки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="8eb12-127">Целочисленное значение, указывающее идентификатор интерфейса для многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="8eb12-128">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8eb12-129">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8eb12-130">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8eb12-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8eb12-131">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="8eb12-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8eb12-132">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="8eb12-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8eb12-133">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8eb12-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8eb12-134">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="8eb12-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8eb12-135">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8eb12-136">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8eb12-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8eb12-137">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="8eb12-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8eb12-138">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8eb12-139">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="8eb12-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8eb12-140">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8eb12-141">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8eb12-142">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8eb12-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="8eb12-143">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="8eb12-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="8eb12-144">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8eb12-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8eb12-145">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="8eb12-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="8eb12-146">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="8eb12-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="8eb12-147">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="8eb12-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="8eb12-148">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="8eb12-148">The default is UTF8.</span></span> <span data-ttu-id="8eb12-149">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="8eb12-150">Значение интервала времени, указывающее срок жизни для привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8eb12-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8eb12-151">Child Elements</span></span>  
  
|<span data-ttu-id="8eb12-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="8eb12-152">Element</span></span>|<span data-ttu-id="8eb12-153">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb12-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8eb12-154">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="8eb12-154">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="8eb12-155">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb12-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8eb12-156">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8eb12-157">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8eb12-157">Parent Elements</span></span>  
  
|<span data-ttu-id="8eb12-158">Элемент</span><span class="sxs-lookup"><span data-stu-id="8eb12-158">Element</span></span>|<span data-ttu-id="8eb12-159">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb12-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8eb12-160">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8eb12-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8eb12-161">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="8eb12-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eb12-162">Примечания</span><span class="sxs-lookup"><span data-stu-id="8eb12-162">Remarks</span></span>  
 <span data-ttu-id="8eb12-163">UdpBinding позволяет службам WCF обмениваться данными через транспорт определяемой пользователем процедуры.</span><span class="sxs-lookup"><span data-stu-id="8eb12-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="8eb12-164">Это позволяет «отправить и забыть» обмен сообщениями, когда клиент отправляет сообщение службе и не ожидает ответа.</span><span class="sxs-lookup"><span data-stu-id="8eb12-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb12-165">Пример</span><span class="sxs-lookup"><span data-stu-id="8eb12-165">Example</span></span>  
 <span data-ttu-id="8eb12-166">В следующем примере показано, как настроить <xref:System.ServiceModel.UdpBinding> с помощью элемента <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="8eb12-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8eb12-167">См. также</span><span class="sxs-lookup"><span data-stu-id="8eb12-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="8eb12-168">Привязки</span><span class="sxs-lookup"><span data-stu-id="8eb12-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8eb12-169">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="8eb12-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8eb12-170">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="8eb12-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8eb12-171">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8eb12-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
