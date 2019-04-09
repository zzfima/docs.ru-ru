---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 6059bc91588492afdd1f205398e6cdfdba0be7ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177467"
---
# <a name="wshttpbinding"></a><span data-ttu-id="735e3-101">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="735e3-101">\<wsHttpBinding></span></span>
<span data-ttu-id="735e3-102">Определяет безопасную, надежную, привязку с возможностью взаимодействия, которая может использоваться для недуплексных контрактов службы.</span><span class="sxs-lookup"><span data-stu-id="735e3-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="735e3-103">В привязке реализованы следующие возможности: WS-ReliableMessaging для надежности и WS-Security для проверки подлинности и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="735e3-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="735e3-104">В качестве транспорта используется HTTP, а для кодировки сообщений — кодировка Text/XML.</span><span class="sxs-lookup"><span data-stu-id="735e3-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="735e3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="735e3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="735e3-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="735e3-106">\<bindings></span></span>  
<span data-ttu-id="735e3-107">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="735e3-107">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735e3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="735e3-108">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
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
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="735e3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="735e3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="735e3-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="735e3-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="735e3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="735e3-111">Attributes</span></span>  
  
|<span data-ttu-id="735e3-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="735e3-112">Attribute</span></span>|<span data-ttu-id="735e3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="735e3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="735e3-114">allowCookies</span><span class="sxs-lookup"><span data-stu-id="735e3-114">allowCookies</span></span>|<span data-ttu-id="735e3-115">Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="735e3-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="735e3-116">Значение по умолчанию – false.</span><span class="sxs-lookup"><span data-stu-id="735e3-116">The default is false.</span></span><br /><br /> <span data-ttu-id="735e3-117">Это свойство можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie.</span><span class="sxs-lookup"><span data-stu-id="735e3-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="735e3-118">В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.</span><span class="sxs-lookup"><span data-stu-id="735e3-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="735e3-119">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="735e3-119">bypassProxyOnLocal</span></span>|<span data-ttu-id="735e3-120">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="735e3-120">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="735e3-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="735e3-121">The default is `false`.</span></span>|  
|<span data-ttu-id="735e3-122">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="735e3-122">closeTimeout</span></span>|<span data-ttu-id="735e3-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="735e3-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="735e3-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="735e3-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="735e3-125">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="735e3-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="735e3-126">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="735e3-126">hostnameComparisonMode</span></span>|<span data-ttu-id="735e3-127">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="735e3-127">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="735e3-128">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="735e3-128">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="735e3-129">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="735e3-129">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="735e3-130">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="735e3-130">maxBufferPoolSize</span></span>|<span data-ttu-id="735e3-131">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-131">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="735e3-132">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="735e3-132">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="735e3-133">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="735e3-133">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="735e3-134">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="735e3-134">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="735e3-135">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="735e3-135">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="735e3-136">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="735e3-136">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="735e3-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="735e3-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="735e3-138">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-138">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="735e3-139">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="735e3-139">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="735e3-140">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="735e3-140">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="735e3-141">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="735e3-141">The default is 65536.</span></span>|  
|<span data-ttu-id="735e3-142">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="735e3-142">messageEncoding</span></span>|<span data-ttu-id="735e3-143">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="735e3-143">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="735e3-144">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="735e3-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="735e3-145">-Текст: Используйте кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="735e3-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="735e3-146">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="735e3-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="735e3-147">-Значение по умолчанию — текст.</span><span class="sxs-lookup"><span data-stu-id="735e3-147">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="735e3-148">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="735e3-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="735e3-149">имя</span><span class="sxs-lookup"><span data-stu-id="735e3-149">name</span></span>|<span data-ttu-id="735e3-150">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="735e3-151">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="735e3-152">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="735e3-152">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="735e3-153">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="735e3-153">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="735e3-154">openTimeout</span><span class="sxs-lookup"><span data-stu-id="735e3-154">openTimeout</span></span>|<span data-ttu-id="735e3-155">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="735e3-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="735e3-156">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="735e3-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="735e3-157">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="735e3-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="735e3-158">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="735e3-158">proxyAddress</span></span>|<span data-ttu-id="735e3-159">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="735e3-159">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="735e3-160">Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="735e3-160">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="735e3-161">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="735e3-161">The default is `null`.</span></span>|  
|<span data-ttu-id="735e3-162">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="735e3-162">receiveTimeout</span></span>|<span data-ttu-id="735e3-163">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="735e3-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="735e3-164">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="735e3-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="735e3-165">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="735e3-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="735e3-166">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="735e3-166">sendTimeout</span></span>|<span data-ttu-id="735e3-167">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="735e3-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="735e3-168">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="735e3-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="735e3-169">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="735e3-169">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="735e3-170">textEncoding</span><span class="sxs-lookup"><span data-stu-id="735e3-170">textEncoding</span></span>|<span data-ttu-id="735e3-171">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="735e3-171">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="735e3-172">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="735e3-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="735e3-173">-   UnicodeFffeTextEncoding: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="735e3-173">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="735e3-174">-   Utf16TextEncoding: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="735e3-174">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="735e3-175">-   Utf8TextEncoding: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="735e3-175">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="735e3-176">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="735e3-176">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="735e3-177">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="735e3-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="735e3-178">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="735e3-178">transactionFlow</span></span>|<span data-ttu-id="735e3-179">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="735e3-179">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="735e3-180">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="735e3-180">The default is `false`.</span></span>|  
|<span data-ttu-id="735e3-181">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="735e3-181">useDefaultWebProxy</span></span>|<span data-ttu-id="735e3-182">Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="735e3-182">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="735e3-183">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="735e3-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="735e3-184">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="735e3-184">Child Elements</span></span>  
  
|<span data-ttu-id="735e3-185">Элемент</span><span class="sxs-lookup"><span data-stu-id="735e3-185">Element</span></span>|<span data-ttu-id="735e3-186">Описание</span><span class="sxs-lookup"><span data-stu-id="735e3-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="735e3-187">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="735e3-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="735e3-188">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="735e3-189">Это элемент типа <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="735e3-189">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="735e3-190">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="735e3-190">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="735e3-191">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="735e3-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="735e3-192">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="735e3-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="735e3-193">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="735e3-193">\<reliableSession></span></span>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="735e3-194">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="735e3-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="735e3-195">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="735e3-195">Parent Elements</span></span>  
  
|<span data-ttu-id="735e3-196">Элемент</span><span class="sxs-lookup"><span data-stu-id="735e3-196">Element</span></span>|<span data-ttu-id="735e3-197">Описание</span><span class="sxs-lookup"><span data-stu-id="735e3-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="735e3-198">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="735e3-198">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="735e3-199">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="735e3-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="735e3-200">Примечания</span><span class="sxs-lookup"><span data-stu-id="735e3-200">Remarks</span></span>  
 <span data-ttu-id="735e3-201">Привязка `WSHttpBinding` аналогична привязке `BasicHttpBinding`, но при этом предоставляет больше функциональных возможностей веб-служб.</span><span class="sxs-lookup"><span data-stu-id="735e3-201">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="735e3-202">В ней используется транспорт HTTP и обеспечивается безопасность сообщения, как и в привязке BasicHttpBinding, но вместе с тем также предоставляются транзакции, надежный обмен сообщениями и WS-Addressing, включенные по умолчанию или доступные посредством одного управляющего параметра.</span><span class="sxs-lookup"><span data-stu-id="735e3-202">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="735e3-203">Пример</span><span class="sxs-lookup"><span data-stu-id="735e3-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
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
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="735e3-204">См. также</span><span class="sxs-lookup"><span data-stu-id="735e3-204">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="735e3-205">Привязки</span><span class="sxs-lookup"><span data-stu-id="735e3-205">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="735e3-206">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="735e3-206">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="735e3-207">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="735e3-207">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="735e3-208">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="735e3-208">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
