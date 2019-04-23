---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 9caba8dfc848a2463b1fa482ccaf55288d96af29
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182153"
---
# <a name="ws2007httpbinding"></a><span data-ttu-id="06ec6-101">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="06ec6-101">\<ws2007HttpBinding></span></span>
<span data-ttu-id="06ec6-102">Определяет привязку с возможностью взаимодействия, которая обеспечивает поддержку для правильных версий элементов привязки <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> и <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-102">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="06ec6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06ec6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="06ec6-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="06ec6-104">\<bindings></span></span>  
<span data-ttu-id="06ec6-105">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="06ec6-105">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ec6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06ec6-106">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06ec6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06ec6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="06ec6-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06ec6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06ec6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06ec6-109">Attributes</span></span>  
  
|<span data-ttu-id="06ec6-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="06ec6-110">Attribute</span></span>|<span data-ttu-id="06ec6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="06ec6-111">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="06ec6-112">Значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="06ec6-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="06ec6-113">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="06ec6-114">Это свойство можно использовать при взаимодействии с веб-службами ASP.NET (ASMX), которые используют файлы Cookie.</span><span class="sxs-lookup"><span data-stu-id="06ec6-114">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="06ec6-115">Это гарантирует, что эти файлы Cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.</span><span class="sxs-lookup"><span data-stu-id="06ec6-115">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="06ec6-116">Значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="06ec6-116">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="06ec6-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-117">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="06ec6-118">Значение <xref:System.TimeSpan>, которое задает длительность временного интервала для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="06ec6-118">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="06ec6-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06ec6-120">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06ec6-120">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="06ec6-121">Задает режим сравнения имен узлов HTTP для анализа универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="06ec6-121">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="06ec6-122">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="06ec6-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="06ec6-123">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="06ec6-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="06ec6-124">Максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-124">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="06ec6-125">Значение по умолчанию - 524 288 байт (512 × 1024).</span><span class="sxs-lookup"><span data-stu-id="06ec6-125">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="06ec6-126">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="06ec6-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="06ec6-127">Создание буферов при каждом использовании и их последующее уничтожение требует слишком много ресурсов; также много ресурсов расходуется при сборке мусора для буферов.</span><span class="sxs-lookup"><span data-stu-id="06ec6-127">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="06ec6-128">Буферные пулы позволяют забирать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="06ec6-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="06ec6-129">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="06ec6-129">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="06ec6-130">Максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-130">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="06ec6-131">Отправитель сообщения, которое превысит это ограничение, получает ошибку протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="06ec6-131">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="06ec6-132">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="06ec6-133">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="06ec6-133">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="06ec6-134">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="06ec6-134">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="06ec6-135">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="06ec6-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06ec6-136">-   `Text`: Используйте кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="06ec6-136">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="06ec6-137">-   `Mtom`: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="06ec6-137">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="06ec6-138">Значение по умолчанию — `Text`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-138">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="06ec6-139">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-139">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="06ec6-140">Имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-140">The configuration name of the binding.</span></span> <span data-ttu-id="06ec6-141">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="06ec6-142">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="06ec6-142">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="06ec6-143">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="06ec6-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="06ec6-144">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="06ec6-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="06ec6-145">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06ec6-146">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06ec6-146">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="06ec6-147">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="06ec6-147">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="06ec6-148">Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-148">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="06ec6-149">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-149">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="06ec6-150">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="06ec6-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="06ec6-151">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06ec6-152">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06ec6-152">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="06ec6-153">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="06ec6-154">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06ec6-155">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06ec6-155">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="06ec6-156">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="06ec6-156">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="06ec6-157">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="06ec6-157">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06ec6-158">-   `UnicodeFffeTextEncoding`: Обратный порядок байтов кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="06ec6-158">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="06ec6-159">-   `Utf16TextEncoding`: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="06ec6-159">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="06ec6-160">-   `Utf8TextEncoding`: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="06ec6-160">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="06ec6-161">Значение по умолчанию — `Utf8TextEncoding`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-161">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="06ec6-162">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-162">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="06ec6-163">Значение, определяющее, поддерживает ли привязка потоки WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="06ec6-163">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="06ec6-164">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-164">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="06ec6-165">Значение, определяющее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="06ec6-165">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="06ec6-166">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="06ec6-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06ec6-167">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06ec6-167">Child Elements</span></span>  
  
|<span data-ttu-id="06ec6-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="06ec6-168">Element</span></span>|<span data-ttu-id="06ec6-169">Описание</span><span class="sxs-lookup"><span data-stu-id="06ec6-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06ec6-170">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="06ec6-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="06ec6-171">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-171">Defines the security settings for the binding.</span></span> <span data-ttu-id="06ec6-172">Это элемент типа <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-172">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="06ec6-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="06ec6-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="06ec6-174">Определяет ограничения по сложности сообщений протокола SOAP, которые могут обрабатываться конечными точками, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="06ec6-174">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="06ec6-175">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="06ec6-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="06ec6-176">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="06ec6-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="06ec6-177">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="06ec6-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06ec6-178">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06ec6-178">Parent Elements</span></span>  
  
|<span data-ttu-id="06ec6-179">Элемент</span><span class="sxs-lookup"><span data-stu-id="06ec6-179">Element</span></span>|<span data-ttu-id="06ec6-180">Описание</span><span class="sxs-lookup"><span data-stu-id="06ec6-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06ec6-181">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="06ec6-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="06ec6-182">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="06ec6-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ec6-183">Примечания</span><span class="sxs-lookup"><span data-stu-id="06ec6-183">Remarks</span></span>  
 <span data-ttu-id="06ec6-184">Привязка `WS2007HttpBinding` добавляет системную привязку, аналогичную `WSHttpBinding`, однако использует версии OASIS протоколов ReliableSession, Security и TransactionFlow.</span><span class="sxs-lookup"><span data-stu-id="06ec6-184">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="06ec6-185">При использовании этой привязки изменение объектной модели или настроек по умолчанию не требуется.</span><span class="sxs-lookup"><span data-stu-id="06ec6-185">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ec6-186">Пример</span><span class="sxs-lookup"><span data-stu-id="06ec6-186">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="06ec6-187">См. также</span><span class="sxs-lookup"><span data-stu-id="06ec6-187">See also</span></span>

- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="06ec6-188">Привязки</span><span class="sxs-lookup"><span data-stu-id="06ec6-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="06ec6-189">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="06ec6-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="06ec6-190">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="06ec6-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="06ec6-191">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="06ec6-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
