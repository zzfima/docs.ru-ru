---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: b717dc76d6226395e9e0345ead750901bb874e03
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738867"
---
# <a name="nethttpbinding"></a><span data-ttu-id="11a82-101">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="11a82-101">\<netHttpBinding></span></span>
<span data-ttu-id="11a82-102">Представляет привязку, которую служба Windows Communication Foundation (WCF) может использовать для настройки и предоставления конечных точек, которые могут взаимодействовать по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="11a82-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="11a82-103">При использовании с дуплексным контрактом будут использоваться веб-сокеты, в противном случае будет использоваться HTTP.</span><span class="sxs-lookup"><span data-stu-id="11a82-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
<span data-ttu-id="11a82-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11a82-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="11a82-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="11a82-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="11a82-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="11a82-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="11a82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="11a82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a82-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a82-108">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
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
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="11a82-109">Type</span><span class="sxs-lookup"><span data-stu-id="11a82-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11a82-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="11a82-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11a82-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11a82-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11a82-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11a82-112">Attributes</span></span>  
  
|<span data-ttu-id="11a82-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="11a82-113">Attribute</span></span>|<span data-ttu-id="11a82-114">Описание</span><span class="sxs-lookup"><span data-stu-id="11a82-114">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="11a82-115">Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="11a82-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="11a82-116">Значение по умолчанию: `false`.</span><span class="sxs-lookup"><span data-stu-id="11a82-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="11a82-117">Это свойство можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie.</span><span class="sxs-lookup"><span data-stu-id="11a82-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="11a82-118">В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.</span><span class="sxs-lookup"><span data-stu-id="11a82-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="11a82-119">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="11a82-119">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="11a82-120">Значение по умолчанию: `false`.</span><span class="sxs-lookup"><span data-stu-id="11a82-120">The default is `false`.</span></span><br /><br /> <span data-ttu-id="11a82-121">Интернет-ресурс является локальным, если у него локальный адрес.</span><span class="sxs-lookup"><span data-stu-id="11a82-121">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="11a82-122">Локальный адрес — это тот же компьютер, локальная локальная сеть или интрасеть, который идентифицируется в синтаксических случаях за счет отсутствия точки (.), как в URI "http://webserver/" и "http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="11a82-122">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="11a82-123">Этот атрибут определяет, будут ли конечные точки, настроенные с помощью привязки BasicHttpBinding, использовать прокси-сервер при доступе к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="11a82-123">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="11a82-124">Если значение этого атрибута `true`, запросы к локальным интернет-ресурсам не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="11a82-124">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="11a82-125">Используйте имя узла (а не localhost), если необходимо, чтобы клиенты проходили через прокси-сервер при взаимодействии со службами на том же компьютере, когда для этого атрибута задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="11a82-125">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="11a82-126">Если атрибут имеет значение `false`, все интернет-запросы выполняются через данный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="11a82-126">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="11a82-127">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="11a82-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="11a82-128">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11a82-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11a82-129">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11a82-129">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="11a82-130">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="11a82-130">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="11a82-131">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="11a82-131">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="11a82-132">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="11a82-132">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="11a82-133">Целое значение, определяющее максимальный объем памяти, выделяемой для диспетчера буферов сообщений, получающих сообщения из канала.</span><span class="sxs-lookup"><span data-stu-id="11a82-133">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="11a82-134">Значение по умолчанию - 524 288 (0x80 000) байт.</span><span class="sxs-lookup"><span data-stu-id="11a82-134">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="11a82-135">Диспетчер буферов сокращает затраты ресурсов на использование буферов с помощью буферного пула.</span><span class="sxs-lookup"><span data-stu-id="11a82-135">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="11a82-136">Буферы требуются для обработки службой сообщений, приходящих из канала.</span><span class="sxs-lookup"><span data-stu-id="11a82-136">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="11a82-137">Если в буферном пуле недостаточно памяти для обработки потока сообщений, диспетчер буферов сообщений должен выделить дополнительную память из кучи CLR, что увеличивает нагрузку по сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="11a82-137">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="11a82-138">Значительное выделение памяти из мусорной кучи CLR указывает на то, что размер буферного пула слишком мал и производительность можно повысить за счет выделения большего объема памяти путем увеличения значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="11a82-138">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="11a82-139">Целое значение, указывающее максимальный размер (в байтах) буфера, хранящего сообщения во время их обработки для конечной точки, настроенной с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-139">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="11a82-140">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="11a82-140">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="11a82-141">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-141">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="11a82-142">Отправитель получает ошибку SOAP, если размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="11a82-142">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="11a82-143">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="11a82-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="11a82-144">Значение по умолчанию - 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="11a82-144">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="11a82-145">Определяет кодировщик, используемый для кодировки сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="11a82-145">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="11a82-146">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="11a82-146">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11a82-147">-Text: использование кодировщика текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="11a82-147">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="11a82-148">-MTOM: используйте кодировщик обмена сообщениями, механизм передачи сообщений 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="11a82-148">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="11a82-149">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="11a82-149">The default is Text.</span></span> <span data-ttu-id="11a82-150">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="11a82-150">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="11a82-151">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="11a82-152">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="11a82-153">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="11a82-153">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="11a82-154">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="11a82-154">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="11a82-155">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="11a82-155">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="11a82-156">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="11a82-156">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="11a82-157">Задает пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-157">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="11a82-158">Значение по умолчанию — http://tempuri.org/Bindings.</span><span class="sxs-lookup"><span data-stu-id="11a82-158">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="11a82-159">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="11a82-159">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="11a82-160">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="11a82-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="11a82-161">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11a82-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11a82-162">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11a82-162">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="11a82-163">Универсальный код ресурса (URI) содержит адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="11a82-163">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="11a82-164">Если для параметра `useSystemWebProxy` задано значение `true`, этот параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="11a82-164">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="11a82-165">Значение по умолчанию: `null`.</span><span class="sxs-lookup"><span data-stu-id="11a82-165">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="11a82-166">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="11a82-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="11a82-167">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11a82-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11a82-168">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="11a82-168">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="11a82-169">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="11a82-169">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="11a82-170">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11a82-170">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11a82-171">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11a82-171">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="11a82-172">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="11a82-172">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="11a82-173">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="11a82-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11a82-174">-BigEndianUnicode: Юникод байтов Encoding.</span><span class="sxs-lookup"><span data-stu-id="11a82-174">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="11a82-175">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="11a82-175">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="11a82-176">-UTF8:8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="11a82-176">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="11a82-177">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="11a82-177">The default is UTF8.</span></span> <span data-ttu-id="11a82-178">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="11a82-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="11a82-179">Допустимое значение <xref:System.ServiceModel.TransferMode>, указывающее, следует ли буферизировать сообщения или передавать их потоком по запросу или отклику.</span><span class="sxs-lookup"><span data-stu-id="11a82-179">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="11a82-180">Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="11a82-180">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="11a82-181">Значение по умолчанию: `true`.</span><span class="sxs-lookup"><span data-stu-id="11a82-181">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="11a82-182">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11a82-182">Child Elements</span></span>  
  
|<span data-ttu-id="11a82-183">Элемент</span><span class="sxs-lookup"><span data-stu-id="11a82-183">Element</span></span>|<span data-ttu-id="11a82-184">Описание</span><span class="sxs-lookup"><span data-stu-id="11a82-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11a82-185">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="11a82-185">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="11a82-186">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-186">Defines the security settings for the binding.</span></span> <span data-ttu-id="11a82-187">Это элемент типа <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="11a82-187">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="11a82-188">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11a82-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="11a82-189">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="11a82-190">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="11a82-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11a82-191">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11a82-191">Parent Elements</span></span>  
  
|<span data-ttu-id="11a82-192">Элемент</span><span class="sxs-lookup"><span data-stu-id="11a82-192">Element</span></span>|<span data-ttu-id="11a82-193">Описание</span><span class="sxs-lookup"><span data-stu-id="11a82-193">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11a82-194">привязки\<</span><span class="sxs-lookup"><span data-stu-id="11a82-194">\<bindings></span></span>](bindings.md)|<span data-ttu-id="11a82-195">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="11a82-195">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a82-196">Заметки</span><span class="sxs-lookup"><span data-stu-id="11a82-196">Remarks</span></span>  
 <span data-ttu-id="11a82-197">Привязка NetHttpBinding использует протокол HTTP в качестве транспорта для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="11a82-197">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="11a82-198">При использовании с дуплексным контрактом будут использоваться веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="11a82-198">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="11a82-199">При использовании контракта типа «запрос-ответ» привязка NetHttpBinding будет работать как BasicHttpBinding с двоичным кодировщиком.</span><span class="sxs-lookup"><span data-stu-id="11a82-199">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="11a82-200">По умолчанию безопасность отключена, но ее можно добавить, установив для атрибута mode элемента [\<security >](security-of-basichttpbinding.md) дочерний элемент значение, отличное от `None`.</span><span class="sxs-lookup"><span data-stu-id="11a82-200">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="11a82-201">По умолчанию используется кодировка сообщений «Text» и кодировка текста «UTF-8».</span><span class="sxs-lookup"><span data-stu-id="11a82-201">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11a82-202">Пример</span><span class="sxs-lookup"><span data-stu-id="11a82-202">Example</span></span>  
 <span data-ttu-id="11a82-203">В следующем примере показано использование привязки <xref:System.ServiceModel.NetHttpBinding>, которая обеспечивает связь по протоколу HTTP и максимальные возможности взаимодействия с веб-службами первого и второго поколений.</span><span class="sxs-lookup"><span data-stu-id="11a82-203">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="11a82-204">Привязка задается в файлах конфигурации для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="11a82-204">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="11a82-205">Тип привязки задан в атрибуте `binding` элемента `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="11a82-205">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="11a82-206">Если необходимо настроить основную привязку и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-206">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="11a82-207">Конечная точка должна ссылаться на конфигурацию привязки по имени с помощью атрибута `bindingConfiguration` элемента `<endpoint>`, как показано в следующем примере кода конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="11a82-207">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="11a82-208">Пример</span><span class="sxs-lookup"><span data-stu-id="11a82-208">Example</span></span>  
 <span data-ttu-id="11a82-209">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="11a82-209">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="11a82-210">Функции из предыдущего примера можно выполнить, удалив bindingConfiguration из адреса конечной точки и имени из привязки.</span><span class="sxs-lookup"><span data-stu-id="11a82-210">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding hostNameComparisonMode="StrongWildcard"
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="11a82-211">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="11a82-211">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a82-212">См. также</span><span class="sxs-lookup"><span data-stu-id="11a82-212">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="11a82-213">Привязки</span><span class="sxs-lookup"><span data-stu-id="11a82-213">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11a82-214">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="11a82-214">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11a82-215">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="11a82-215">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11a82-216">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="11a82-216">\<binding></span></span>](bindings.md)
