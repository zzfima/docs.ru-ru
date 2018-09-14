---
title: '&lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 943887dd2bf3b309c0663a9eb06e658ee5957844
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "44757150"
---
# <a name="ltwsfederationhttpbindinggt"></a><span data-ttu-id="47249-102">&lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="47249-102">&lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="47249-103">Определяет привязку, которая поддерживает спецификацию WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="47249-103">Defines a binding that supports WS-Federation.</span></span>  
  
 <span data-ttu-id="47249-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="47249-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="47249-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="47249-105">\<bindings></span></span>  
<span data-ttu-id="47249-106">wsFederationBinding, элемент</span><span class="sxs-lookup"><span data-stu-id="47249-106">wsFederationBinding element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47249-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47249-107">Syntax</span></span>  
  
```xml  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47249-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47249-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47249-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47249-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47249-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47249-110">Attributes</span></span>  
  
|<span data-ttu-id="47249-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="47249-111">Attribute</span></span>|<span data-ttu-id="47249-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47249-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47249-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="47249-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="47249-114">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="47249-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="47249-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="47249-115">The default is `false`.</span></span>|  
|<span data-ttu-id="47249-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="47249-116">closeTimeout</span></span>|<span data-ttu-id="47249-117">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="47249-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="47249-118">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="47249-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="47249-119">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="47249-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="47249-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="47249-120">hostnameComparisonMode</span></span>|<span data-ttu-id="47249-121">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="47249-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="47249-122">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="47249-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="47249-123">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="47249-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="47249-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="47249-124">maxBufferPoolSize</span></span>|<span data-ttu-id="47249-125">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="47249-126">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="47249-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="47249-127">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="47249-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="47249-128">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="47249-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="47249-129">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="47249-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="47249-130">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="47249-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="47249-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="47249-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="47249-132">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="47249-133">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="47249-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="47249-134">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="47249-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="47249-135">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="47249-135">The default is 65536.</span></span>|  
|<span data-ttu-id="47249-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="47249-136">messageEncoding</span></span>|<span data-ttu-id="47249-137">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="47249-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="47249-138">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="47249-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="47249-139">-Text: Используется кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="47249-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="47249-140">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="47249-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="47249-141">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="47249-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="47249-142">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="47249-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="47249-143">имя</span><span class="sxs-lookup"><span data-stu-id="47249-143">name</span></span>|<span data-ttu-id="47249-144">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="47249-145">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="47249-146">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="47249-146">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="47249-147">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="47249-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="47249-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="47249-148">openTimeout</span></span>|<span data-ttu-id="47249-149">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="47249-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="47249-150">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="47249-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="47249-151">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="47249-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="47249-152">privactyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="47249-152">privactyNoticeAt</span></span>|<span data-ttu-id="47249-153">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="47249-153">A String that specifies a URI at which the privacy notice is located.</span></span>|  
|<span data-ttu-id="47249-154">privactyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="47249-154">privactyNoticeVersion</span></span>|<span data-ttu-id="47249-155">Целое число, определяющее версию текущего уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="47249-155">An integer that specifies the version of the current privacy notice.</span></span>|  
|<span data-ttu-id="47249-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="47249-156">proxyAddress</span></span>|<span data-ttu-id="47249-157">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="47249-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="47249-158">Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="47249-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="47249-159">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="47249-159">The default is `null`.</span></span>|  
|<span data-ttu-id="47249-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="47249-160">receiveTimeout</span></span>|<span data-ttu-id="47249-161">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="47249-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="47249-162">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="47249-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="47249-163">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="47249-163">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="47249-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="47249-164">sendTimeout</span></span>|<span data-ttu-id="47249-165">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="47249-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="47249-166">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="47249-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="47249-167">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="47249-167">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="47249-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="47249-168">textEncoding</span></span>|<span data-ttu-id="47249-169">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="47249-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="47249-170">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="47249-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="47249-171">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="47249-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="47249-172">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="47249-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="47249-173">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="47249-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="47249-174">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="47249-174">The default is UTF8.</span></span> <span data-ttu-id="47249-175">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="47249-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|  
|<span data-ttu-id="47249-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="47249-176">transactionFlow</span></span>|<span data-ttu-id="47249-177">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="47249-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="47249-178">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="47249-178">The default is `false`.</span></span>|  
|<span data-ttu-id="47249-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="47249-179">useDefaultWebProxy</span></span>|<span data-ttu-id="47249-180">Логическое значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="47249-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="47249-181">Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан).</span><span class="sxs-lookup"><span data-stu-id="47249-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="47249-182">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47249-182">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47249-183">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47249-183">Child Elements</span></span>  
  
|<span data-ttu-id="47249-184">Элемент</span><span class="sxs-lookup"><span data-stu-id="47249-184">Element</span></span>|<span data-ttu-id="47249-185">Описание</span><span class="sxs-lookup"><span data-stu-id="47249-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47249-186">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="47249-186">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="47249-187">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="47249-187">Defines the security settings for the message.</span></span> <span data-ttu-id="47249-188">Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="47249-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="47249-189">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="47249-189">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="47249-190">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="47249-191">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="47249-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="47249-192">reliableSession</span><span class="sxs-lookup"><span data-stu-id="47249-192">reliableSession</span></span>](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="47249-193">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="47249-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47249-194">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47249-194">Parent Elements</span></span>  
  
|<span data-ttu-id="47249-195">Элемент</span><span class="sxs-lookup"><span data-stu-id="47249-195">Element</span></span>|<span data-ttu-id="47249-196">Описание</span><span class="sxs-lookup"><span data-stu-id="47249-196">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47249-197">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="47249-197">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="47249-198">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="47249-198">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47249-199">Примечания</span><span class="sxs-lookup"><span data-stu-id="47249-199">Remarks</span></span>  
 <span data-ttu-id="47249-200">Федерация - это возможность совместного использования удостоверений в нескольких системах в целях проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="47249-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="47249-201">Эти удостоверения могут ссылаться на пользователей или на компьютеры.</span><span class="sxs-lookup"><span data-stu-id="47249-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="47249-202">Федеративный протокол HTTP поддерживает безопасность SOAP и безопасность в смешанном режиме, но не поддерживает использование исключительно безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="47249-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="47249-203">Эта привязка обеспечивает поддержку Windows Communication Foundation (WCF) для протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="47249-203">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="47249-204">Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.</span><span class="sxs-lookup"><span data-stu-id="47249-204">Services configured with this binding must use the HTTP transport.</span></span>  
  
 <span data-ttu-id="47249-205">Привязки состоят из стека элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="47249-206">Стек элементов привязки в</span><span class="sxs-lookup"><span data-stu-id="47249-206">The stack of binding elements in</span></span>  
  
 <span data-ttu-id="47249-207">`wsFederationHttpBinding` идентичен тому, что содержится в `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="47249-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>  
  
 <span data-ttu-id="47249-208">Когда [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) присваивается значение по умолчанию <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="47249-208">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>  
  
 <span data-ttu-id="47249-209">`wsFederationHttpBinding` Управляет сведениями о параметрах безопасности сообщений в [ \<сообщения >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="47249-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="47249-210">Обратите внимание, что [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) элемент обеспечивает доступ на получение только в том случае, как безопасность, используемый привязкой, нельзя изменить после создания привязки.</span><span class="sxs-lookup"><span data-stu-id="47249-210">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>  
  
 <span data-ttu-id="47249-211">Привязка `wsFederationHttpBinding` также предоставляет атрибут privactyNoticeAt для установки и извлечения универсального кода ресурса (URI), определяющего расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="47249-211">The `wsFederationHttpBinding` also provides a privactyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>  
  
 <span data-ttu-id="47249-212">Обеспечение безопасности политики особенно важно в федеративных сценариях.</span><span class="sxs-lookup"><span data-stu-id="47249-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="47249-213">Для защиты политики от злоумышленников рекомендуется использовать определенную систему безопасности, например протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="47249-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>  
  
 <span data-ttu-id="47249-214">В федеративных сценариях с использованием этой привязки политика службы потенциально содержит важные сведения, например ключ для шифрования выдаваемого маркера (SAML), тип утверждений, помещаемых в маркер, и так далее.</span><span class="sxs-lookup"><span data-stu-id="47249-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="47249-215">Если политика подделана, атакующий может обнаружить ключ выданного маркера, что приводит к дальнейшим подделкам, раскрытию сведений и другим вредоносным действиям.</span><span class="sxs-lookup"><span data-stu-id="47249-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="47249-216">Чтобы предупредить злонамеренные действия, политика должна быть получена от службы безопасным способом (например, с помощью протокола HTTPS).</span><span class="sxs-lookup"><span data-stu-id="47249-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>  
  
 <span data-ttu-id="47249-217">Дополнительные сведения об этой привязке см. в разделе [как: создание WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="47249-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="47249-218">Пример</span><span class="sxs-lookup"><span data-stu-id="47249-218">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="saml"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</wsFederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47249-219">См. также</span><span class="sxs-lookup"><span data-stu-id="47249-219">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>  
 [<span data-ttu-id="47249-220">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="47249-220">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="47249-221">Привязки</span><span class="sxs-lookup"><span data-stu-id="47249-221">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="47249-222">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="47249-222">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="47249-223">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="47249-223">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="47249-224">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="47249-224">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
