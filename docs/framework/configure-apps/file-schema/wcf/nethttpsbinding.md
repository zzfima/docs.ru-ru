---
title: "&lt;Привязка netHttpsBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 315420a6561d68ff714cefedf5161892342b3ff1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltnethttpsbindinggt"></a><span data-ttu-id="43489-102">&lt;Привязка netHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="43489-102">&lt;netHttpsBinding&gt;</span></span>
<span data-ttu-id="43489-103">Представляет привязку, которую служба [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] может использовать для настройки и доступа к конечным точкам, которые способны вести обмен данными через HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43489-103">Represents a binding that a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="43489-104">При использовании с дуплексным контрактом будут использоваться веб-сокеты, в противном случае будет использоваться протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43489-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="43489-105">Корневой элемент</span><span class="sxs-lookup"><span data-stu-id="43489-105">Root Element</span></span>  
<span data-ttu-id="43489-106">Следующий элемент</span><span class="sxs-lookup"><span data-stu-id="43489-106">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43489-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43489-107">Syntax</span></span>  

```xml
<netHttpsBinding>  
  <binding allowCookies="Boolean"  
           bypassProxyOnLocal="Boolean"  
           closeTimeout="TimeSpan"   
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
           maxBufferPoolSize="Integer"  
           maxBufferSize="Integer"  
           maxReceivedMessageSize="Integer"  
           messageEncoding="Binary/Text/Mtom"  
           name="string"   
           openTimeout="TimeSpan"   
           proxyAddress="URI"  
           receiveTimeout="TimeSpan"  
           sendTimeout="TimeSpan"  
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                 realm="string" />  
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" 
               clientCredentialType="UserName/Certificate"/>  
    </security>  
    <readerQuotas maxArrayLength="Integer" 
                  maxBytesPerRead="Integer" 
                  maxDepth="Integer" 
                  maxNameTableCharCount="Integer" 
                  maxStringContentLength="Integer" />  
  </binding>  
</netHttpsBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="43489-108">Тип</span><span class="sxs-lookup"><span data-stu-id="43489-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43489-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43489-109">Attributes and Elements</span></span>  
 <span data-ttu-id="43489-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43489-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43489-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43489-111">Attributes</span></span>  
  
|<span data-ttu-id="43489-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="43489-112">Attribute</span></span>|<span data-ttu-id="43489-113">Описание</span><span class="sxs-lookup"><span data-stu-id="43489-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="43489-114">Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="43489-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="43489-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="43489-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="43489-116">Это свойство можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie.</span><span class="sxs-lookup"><span data-stu-id="43489-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="43489-117">В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.</span><span class="sxs-lookup"><span data-stu-id="43489-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="43489-118">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="43489-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="43489-119">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="43489-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="43489-120">Интернет-ресурс является локальным, если у него локальный адрес.</span><span class="sxs-lookup"><span data-stu-id="43489-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="43489-121">Локальный адрес — это адрес, расположенный на том же компьютере, в той же локальной сети или интрасети, синтаксически идентифицируемый отсутствием точки (.), как в универсальных кодах ресурсов http://webserver/ и http://localhost/.</span><span class="sxs-lookup"><span data-stu-id="43489-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="43489-122">Этот атрибут определяет, будут ли конечные точки, настроенные с помощью привязки BasicHttpBinding, использовать прокси-сервер при доступе к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="43489-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="43489-123">Если значение этого атрибута `true`, запросы к локальным интернет-ресурсам не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="43489-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="43489-124">Используйте имя узла (а не localhost), если необходимо, чтобы клиенты проходили через прокси-сервер при взаимодействии со службами на том же компьютере, когда для этого атрибута задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="43489-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="43489-125">Если атрибут имеет значение `false`, все интернет-запросы выполняются через данный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="43489-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="43489-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="43489-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="43489-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="43489-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="43489-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="43489-128">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="43489-129">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="43489-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="43489-130">Это атрибут типа `HostnameComparisonMode`, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="43489-130">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="43489-131">Значение по умолчанию — `StrongWildcard`, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="43489-131">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="43489-132">Целое значение, определяющее максимальный объем памяти, выделяемой для диспетчера буферов сообщений, получающих сообщения из канала.</span><span class="sxs-lookup"><span data-stu-id="43489-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="43489-133">Значение по умолчанию - 524 288 (0x80 000) байт.</span><span class="sxs-lookup"><span data-stu-id="43489-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="43489-134">Диспетчер буферов сокращает затраты ресурсов на использование буферов с помощью буферного пула.</span><span class="sxs-lookup"><span data-stu-id="43489-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="43489-135">Буферы требуются для обработки службой сообщений, приходящих из канала.</span><span class="sxs-lookup"><span data-stu-id="43489-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="43489-136">Если в буферном пуле недостаточно памяти для обработки потока сообщений, диспетчер буферов сообщений должен выделить дополнительную память из кучи CLR, что увеличивает нагрузку по сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="43489-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="43489-137">Значительное выделение памяти из мусорной кучи CLR указывает на то, что размер буферного пула слишком мал и производительность можно повысить за счет выделения большего объема памяти путем увеличения значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="43489-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="43489-138">Целое значение, указывающее максимальный размер (в байтах) буфера, хранящего сообщения во время их обработки для конечной точки, настроенной с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="43489-139">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="43489-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="43489-140">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="43489-141">Отправитель получает ошибку SOAP, если размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="43489-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="43489-142">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="43489-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="43489-143">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="43489-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="43489-144">Определяет кодировщик, используемый для кодировки сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="43489-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="43489-145">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="43489-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="43489-146">-Text: Используется кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="43489-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="43489-147">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="43489-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="43489-148">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="43489-148">The default is Text.</span></span> <span data-ttu-id="43489-149">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="43489-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="43489-150">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="43489-151">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="43489-152">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="43489-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="43489-153">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="43489-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="43489-154">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="43489-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="43489-155">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="43489-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="43489-156">Задает пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="43489-157">Значение по умолчанию - «http://tempuri.org/Bindings».</span><span class="sxs-lookup"><span data-stu-id="43489-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="43489-158">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="43489-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="43489-159">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="43489-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="43489-160">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="43489-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="43489-161">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="43489-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="43489-162">Универсальный код ресурса (URI) содержит адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="43489-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="43489-163">Если для параметра `useSystemWebProxy` задано значение `true`, этот параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="43489-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="43489-164">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="43489-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="43489-165">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="43489-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="43489-166">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="43489-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="43489-167">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="43489-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="43489-168">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="43489-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="43489-169">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="43489-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="43489-170">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="43489-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="43489-171">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="43489-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="43489-172">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="43489-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="43489-173">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="43489-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="43489-174">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="43489-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="43489-175">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="43489-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="43489-176">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="43489-176">The default is UTF8.</span></span> <span data-ttu-id="43489-177">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="43489-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="43489-178">Допустимое значение <xref:System.ServiceModel.TransferMode>, указывающее, следует ли буферизировать сообщения или передавать их потоком по запросу или отклику.</span><span class="sxs-lookup"><span data-stu-id="43489-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="43489-179">Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="43489-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="43489-180">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="43489-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="43489-181">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43489-181">Child Elements</span></span>  
  
|<span data-ttu-id="43489-182">Элемент</span><span class="sxs-lookup"><span data-stu-id="43489-182">Element</span></span>|<span data-ttu-id="43489-183">Описание:</span><span class="sxs-lookup"><span data-stu-id="43489-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43489-184">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="43489-184">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="43489-185">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="43489-186">Это элемент типа <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="43489-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="43489-187">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="43489-187">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="43489-188">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="43489-189">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="43489-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43489-190">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43489-190">Parent Elements</span></span>  
  
|<span data-ttu-id="43489-191">Элемент</span><span class="sxs-lookup"><span data-stu-id="43489-191">Element</span></span>|<span data-ttu-id="43489-192">Описание:</span><span class="sxs-lookup"><span data-stu-id="43489-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43489-193">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="43489-193">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="43489-194">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="43489-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43489-195">Примечания</span><span class="sxs-lookup"><span data-stu-id="43489-195">Remarks</span></span>  
 <span data-ttu-id="43489-196">Привязка NetHttpsBinding использует протокол HTTPS в качестве транспорта для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="43489-196">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="43489-197">При использовании с дуплексным контрактом будут использоваться веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="43489-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="43489-198">При использовании контракта типа «запрос-ответ» привязка NetHttpsBinding будет работать как BasicHttpsBinding с двоичным кодировщиком.</span><span class="sxs-lookup"><span data-stu-id="43489-198">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="43489-199">Система безопасности отключена по умолчанию, но может быть добавлена присвоением атрибута mode [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) дочернего элемента значение, отличное от `None`.</span><span class="sxs-lookup"><span data-stu-id="43489-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="43489-200">По умолчанию используется кодировка сообщений «Text» и кодировка текста «UTF-8».</span><span class="sxs-lookup"><span data-stu-id="43489-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43489-201">Пример</span><span class="sxs-lookup"><span data-stu-id="43489-201">Example</span></span>  
 <span data-ttu-id="43489-202">В следующем примере показано использование привязки <xref:System.ServiceModel.NetHttpBinding>, которая обеспечивает связь по протоколу HTTPS и максимальные возможности взаимодействия с веб-службами первого и второго поколений.</span><span class="sxs-lookup"><span data-stu-id="43489-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="43489-203">Привязка задается в файлах конфигурации для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="43489-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="43489-204">Тип привязки задан в атрибуте `binding` элемента `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="43489-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="43489-205">Если необходимо настроить основную привязку и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="43489-206">Конечная точка должна ссылаться на конфигурацию привязки по имени с помощью атрибута `bindingConfiguration` элемента `<endpoint>`, как показано в следующем примере кода конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="43489-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpsBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpsBinding>  
      <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard" 
               receiveTimeout="00:10:00" 
               sendTimeout="00:10:00" 
               openTimeout="00:10:00" 
               closeTimeout="00:10:00" 
               maxReceivedMessageSize="65536" 
               maxBufferSize="65536" 
               maxBufferPoolSize="524288" 
               transferMode="Buffered" 
               messageEncoding="Binary" 
               textEncoding="utf-8" 
               bypassProxyOnLocal="false" 
               useDefaultWebProxy="true">  
        <security mode="None" />  
      </binding>  
    </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="43489-207">Пример</span><span class="sxs-lookup"><span data-stu-id="43489-207">Example</span></span>  
 <span data-ttu-id="43489-208">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="43489-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="43489-209">Задачи предыдущего примера можно выполнить, удалив bindingConfiguration из адреса конечной точки и имя frm из привязки.</span><span class="sxs-lookup"><span data-stu-id="43489-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpsBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpsBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="43489-210">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="43489-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43489-211">См. также</span><span class="sxs-lookup"><span data-stu-id="43489-211">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="43489-212">Привязки</span><span class="sxs-lookup"><span data-stu-id="43489-212">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="43489-213">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="43489-213">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="43489-214">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="43489-214">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="43489-215">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="43489-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
