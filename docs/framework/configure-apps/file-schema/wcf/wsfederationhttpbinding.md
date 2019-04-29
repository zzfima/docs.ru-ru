---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 8ed8f62f9415ed556a61ca53f27442a9355d8d7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698854"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="93ff1-101">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="93ff1-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="93ff1-102">Определяет привязку, которая поддерживает спецификацию WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="93ff1-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="93ff1-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="93ff1-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="93ff1-104">\<привязки > \\</span><span class="sxs-lookup"><span data-stu-id="93ff1-104">\<bindings>\\</span></span>
<span data-ttu-id="93ff1-105">wsFederationBinding, элемент</span><span class="sxs-lookup"><span data-stu-id="93ff1-105">wsFederationBinding element</span></span>

## <a name="syntax"></a><span data-ttu-id="93ff1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93ff1-106">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
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
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
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
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
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
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93ff1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93ff1-107">Attributes and Elements</span></span>

<span data-ttu-id="93ff1-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="93ff1-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="93ff1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93ff1-109">Attributes</span></span>

|<span data-ttu-id="93ff1-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="93ff1-110">Attribute</span></span>|<span data-ttu-id="93ff1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="93ff1-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="93ff1-112">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="93ff1-112">bypassProxyOnLocal</span></span>|<span data-ttu-id="93ff1-113">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="93ff1-113">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="93ff1-114">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="93ff1-114">The default is `false`.</span></span>|
|<span data-ttu-id="93ff1-115">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="93ff1-115">closeTimeout</span></span>|<span data-ttu-id="93ff1-116">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="93ff1-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="93ff1-117">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93ff1-118">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93ff1-118">The default is 00:01:00.</span></span>|
|<span data-ttu-id="93ff1-119">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="93ff1-119">hostnameComparisonMode</span></span>|<span data-ttu-id="93ff1-120">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="93ff1-120">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="93ff1-121">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="93ff1-121">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="93ff1-122">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="93ff1-122">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="93ff1-123">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="93ff1-123">maxBufferPoolSize</span></span>|<span data-ttu-id="93ff1-124">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-124">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="93ff1-125">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="93ff1-125">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="93ff1-126">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="93ff1-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="93ff1-127">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="93ff1-127">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="93ff1-128">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="93ff1-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="93ff1-129">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="93ff1-129">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="93ff1-130">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="93ff1-130">maxReceivedMessageSize</span></span>|<span data-ttu-id="93ff1-131">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-131">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="93ff1-132">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="93ff1-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="93ff1-133">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="93ff1-134">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="93ff1-134">The default is 65536.</span></span>|
|<span data-ttu-id="93ff1-135">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="93ff1-135">messageEncoding</span></span>|<span data-ttu-id="93ff1-136">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="93ff1-136">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="93ff1-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="93ff1-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="93ff1-138">-Текст: Используйте кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="93ff1-138">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="93ff1-139">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="93ff1-139">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="93ff1-140">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="93ff1-140">The default is Text.</span></span><br /><br /> <span data-ttu-id="93ff1-141">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-141">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="93ff1-142">имя</span><span class="sxs-lookup"><span data-stu-id="93ff1-142">name</span></span>|<span data-ttu-id="93ff1-143">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="93ff1-144">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="93ff1-145">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="93ff1-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="93ff1-146">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="93ff1-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="93ff1-147">openTimeout</span><span class="sxs-lookup"><span data-stu-id="93ff1-147">openTimeout</span></span>|<span data-ttu-id="93ff1-148">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="93ff1-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="93ff1-149">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93ff1-150">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93ff1-150">The default is 00:01:00.</span></span>|
|<span data-ttu-id="93ff1-151">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="93ff1-151">privacyNoticeAt</span></span>|<span data-ttu-id="93ff1-152">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="93ff1-152">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="93ff1-153">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="93ff1-153">privacyNoticeVersion</span></span>|<span data-ttu-id="93ff1-154">Целое число, определяющее версию текущего уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="93ff1-154">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="93ff1-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="93ff1-155">proxyAddress</span></span>|<span data-ttu-id="93ff1-156">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="93ff1-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="93ff1-157">Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="93ff1-157">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="93ff1-158">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="93ff1-158">The default is `null`.</span></span>|
|<span data-ttu-id="93ff1-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="93ff1-159">receiveTimeout</span></span>|<span data-ttu-id="93ff1-160">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="93ff1-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="93ff1-161">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93ff1-162">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="93ff1-162">The default is 00:10:00.</span></span>|
|<span data-ttu-id="93ff1-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="93ff1-163">sendTimeout</span></span>|<span data-ttu-id="93ff1-164">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="93ff1-165">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93ff1-166">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93ff1-166">The default is 00:01:00.</span></span>|
|<span data-ttu-id="93ff1-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="93ff1-167">textEncoding</span></span>|<span data-ttu-id="93ff1-168">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="93ff1-168">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="93ff1-169">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="93ff1-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="93ff1-170">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="93ff1-170">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="93ff1-171">-Юникод. 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="93ff1-171">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="93ff1-172">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="93ff1-172">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="93ff1-173">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="93ff1-173">The default is UTF8.</span></span> <span data-ttu-id="93ff1-174">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-174">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="93ff1-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="93ff1-175">transactionFlow</span></span>|<span data-ttu-id="93ff1-176">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="93ff1-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="93ff1-177">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="93ff1-177">The default is `false`.</span></span>|
|<span data-ttu-id="93ff1-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="93ff1-178">useDefaultWebProxy</span></span>|<span data-ttu-id="93ff1-179">Логическое значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="93ff1-179">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="93ff1-180">Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан).</span><span class="sxs-lookup"><span data-stu-id="93ff1-180">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="93ff1-181">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="93ff1-181">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="93ff1-182">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93ff1-182">Child Elements</span></span>

|<span data-ttu-id="93ff1-183">Элемент</span><span class="sxs-lookup"><span data-stu-id="93ff1-183">Element</span></span>|<span data-ttu-id="93ff1-184">Описание</span><span class="sxs-lookup"><span data-stu-id="93ff1-184">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93ff1-185">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="93ff1-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="93ff1-186">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="93ff1-186">Defines the security settings for the message.</span></span> <span data-ttu-id="93ff1-187">Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-187">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="93ff1-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="93ff1-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="93ff1-189">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="93ff1-190">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="93ff1-191">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="93ff1-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="93ff1-192">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="93ff1-192">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="93ff1-193">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93ff1-193">Parent Elements</span></span>

|<span data-ttu-id="93ff1-194">Элемент</span><span class="sxs-lookup"><span data-stu-id="93ff1-194">Element</span></span>|<span data-ttu-id="93ff1-195">Описание</span><span class="sxs-lookup"><span data-stu-id="93ff1-195">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93ff1-196">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="93ff1-196">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="93ff1-197">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="93ff1-197">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93ff1-198">Примечания</span><span class="sxs-lookup"><span data-stu-id="93ff1-198">Remarks</span></span>

<span data-ttu-id="93ff1-199">Федерация - это возможность совместного использования удостоверений в нескольких системах в целях проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="93ff1-199">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="93ff1-200">Эти удостоверения могут ссылаться на пользователей или на компьютеры.</span><span class="sxs-lookup"><span data-stu-id="93ff1-200">These identities can refer to users or to machines.</span></span> <span data-ttu-id="93ff1-201">Федеративный протокол HTTP поддерживает безопасность SOAP и безопасность в смешанном режиме, но не поддерживает использование исключительно безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="93ff1-201">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="93ff1-202">Эта привязка обеспечивает поддержку Windows Communication Foundation (WCF) для протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="93ff1-202">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="93ff1-203">Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.</span><span class="sxs-lookup"><span data-stu-id="93ff1-203">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="93ff1-204">Привязки состоят из стека элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-204">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="93ff1-205">Стек элементов привязки в</span><span class="sxs-lookup"><span data-stu-id="93ff1-205">The stack of binding elements in</span></span>

<span data-ttu-id="93ff1-206">`wsFederationHttpBinding` идентичен тому, что содержится в `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="93ff1-206">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="93ff1-207">Когда [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) присваивается значение по умолчанию <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="93ff1-207">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="93ff1-208">`wsFederationHttpBinding` Управляет сведениями о параметрах безопасности сообщений в [ \<сообщения >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="93ff1-208">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="93ff1-209">Обратите внимание, что [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) элемент обеспечивает доступ на получение только в том случае, как безопасность, используемый привязкой, нельзя изменить после создания привязки.</span><span class="sxs-lookup"><span data-stu-id="93ff1-209">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="93ff1-210">`wsFederationHttpBinding` Также предоставляет атрибут privacyNoticeAt задание и получение URI, по которому находится уведомление о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="93ff1-210">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="93ff1-211">Обеспечение безопасности политики особенно важно в федеративных сценариях.</span><span class="sxs-lookup"><span data-stu-id="93ff1-211">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="93ff1-212">Для защиты политики от злоумышленников рекомендуется использовать определенную систему безопасности, например протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93ff1-212">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="93ff1-213">В федеративных сценариях с использованием этой привязки политика службы потенциально содержит важные сведения, например ключ для шифрования выдаваемого маркера (SAML), тип утверждений, помещаемых в маркер, и так далее.</span><span class="sxs-lookup"><span data-stu-id="93ff1-213">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="93ff1-214">Если политика подделана, атакующий может обнаружить ключ выданного маркера, что приводит к дальнейшим подделкам, раскрытию сведений и другим вредоносным действиям.</span><span class="sxs-lookup"><span data-stu-id="93ff1-214">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="93ff1-215">Чтобы предупредить злонамеренные действия, политика должна быть получена от службы безопасным способом (например, с помощью протокола HTTPS).</span><span class="sxs-lookup"><span data-stu-id="93ff1-215">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="93ff1-216">Дополнительные сведения об этой привязке см. в разделе [как: Создание WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="93ff1-216">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="93ff1-217">Пример</span><span class="sxs-lookup"><span data-stu-id="93ff1-217">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
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

## <a name="see-also"></a><span data-ttu-id="93ff1-218">См. также</span><span class="sxs-lookup"><span data-stu-id="93ff1-218">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="93ff1-219">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="93ff1-219">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="93ff1-220">Привязки</span><span class="sxs-lookup"><span data-stu-id="93ff1-220">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="93ff1-221">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="93ff1-221">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="93ff1-222">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="93ff1-222">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="93ff1-223">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="93ff1-223">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
