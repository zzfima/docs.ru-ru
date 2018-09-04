---
title: '&lt;customBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 514d0770bd94e55ef3eb7ce2421d1d031c90c3e9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527139"
---
# <a name="ltcustombindinggt"></a><span data-ttu-id="65199-102">&lt;customBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="65199-102">&lt;customBinding&gt;</span></span>
<span data-ttu-id="65199-103">Обеспечивает пользователю полный контроль над стеком обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="65199-103">Provides full control over the messaging stack for the user.</span></span>  
  
 <span data-ttu-id="65199-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="65199-104">\<system.serviceModel></span></span>  
<span data-ttu-id="65199-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="65199-105">\<bindings></span></span>  
<span data-ttu-id="65199-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="65199-106">\<customBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65199-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65199-107">Syntax</span></span>  
  
```xml  
<customBinding>  
    <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
       <compositeDuplex clientBaseAddress="Uri"/>  
       <reliableSession acknowledgementInterval="TimeSpan"  
           advancedFlowControl="Boolean"   
           bufferedMessagesQuota="Integer"  
           inactivityTimeout="TimeSpan"  
           maxPendingChannels="Integer"  
           maxRetryCount="Integer"   
           ordered="Boolean" />  
       <pnrpPeerResolver />  
       <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
       <sslStreamSecurity requireClientCertificate="Boolean" />  
              <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
       <security   
          defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
           authenticationMode="UserNameForAnonymous"  
           contextMode="Cookie"   
           defaultProtectionLevel="Sign"  
           enableKeyDerivation="false"  
           keyEntropyMode="ClientEntropy"   
                  messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"   
           securityVersion="WSSecurityXXX2005">  
           <localClientSettings cacheCookies="false"  
               detectReplays="false"  
               maxCookieCachingTime="00:07:24" />  
           <localServiceSettings replayCacheSize="9"  
               maxClockSkew="00:00:03"   
               replayWindow="00:07:22.2190000" />  
       </security>  
       <binaryMessageEncoding maxReadPoolSize="Integer"  
           maxWritePoolSize="Integer"  
           maxSessionSize="Integer" />  
       <httpsTransport manualAddressing="Boolean"  
           maxMessageSize="Integer"  
           authenticationScheme="Negotiate"   
           bypassProxyOnLocal="Boolean"  
           hostNameComparisonMode="Exact"   
           mapAddressingHeadersToHttpHeaders="Boolean"   
           proxyaddress="Uri"  
           realm="String"   
           requireClientCertificate="Boolean" />  
       <peerTransport manualAddressing="false"  
          maxMessageSize="20002"  
          listenIPAddress="202.10.1.9"   
          messageAuthentication="false"  
          peerNodeAuthenticationMode="None"  
          port="1000" />  
  
<security   
      defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
   authenticationMode="UserNameForAnonymous"  
   bootstrapBindingConfiguration="String"  
   bootstrapBindingSectionName="String"  
   defaultProtectionLevel="None/Sign/EncryptAndSign"  
      requireDerivedKeys="Boolean"  
   securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"  
   includeTimestamp="Boolean"  
   keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"   
   messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"   
   protectTokens="Boolean"  
   requireSecurityContextCancellation="Boolean"  
   securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"  
   requireSignatureConfirmation="Boolean" >  
   <localClientSettings cacheCookies="Boolean"  
      detectReplays="Boolean"  
      replayCacheSize="Integer"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      reconnectOnTransportFailure="Boolean"  
      timestampValidityDuration="TimeSpan"  
      cookieRenewalThresholdPercentage="Integer" />  
   <localServiceSettings detectReplays="Boolean"  
      issuedCookieLifeTime="TimeSpan"  
      maxStatefulNegotiations="Integer"  
            replayCacheSize="Integer"  
      maxClockSkew="TimeSpan"   
      negotiationTimeout="TimeSpan"  
      replayWindow="TimeSpan"  
      inactivityTimeout="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      reconnectOnTransportFailure="Boolean"  
      maxConcurrentSessions="Integer"  
      timestampValidityDuration="TimeSpan" />  
   <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />  
<security   
   defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
   authenticationMode="UserNameForAnonymous"  
   bootstrapBindingConfiguration="String"  
   bootstrapBindingSectionName="String"  
   defaultProtectionLevel="None/Sign/EncryptAndSign"  
      requireDerivedKeys="Boolean"  
   securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"  
   includeTimestamp="Boolean"  
   keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"   
   messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"   
   protectTokens="Boolean"  
   requireSecurityContextCancellation="Boolean"  
   securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"  
   requireSignatureConfirmation="Boolean" >  
   <localClientSettings cacheCookies="Boolean"  
      detectReplays="Boolean"  
      replayCacheSize="Integer"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      reconnectOnTransportFailure="Boolean"  
      timestampValidityDuration="TimeSpan"  
      cookieRenewalThresholdPercentage="Integer" />  
   <localServiceSettings detectReplays="Boolean"  
      issuedCookieLifeTime="TimeSpan"  
      maxStatefulNegotiations="Integer"  
            replayCacheSize="Integer"  
      maxClockSkew="TimeSpan"   
      negotiationTimeout="TimeSpan"  
      replayWindow="TimeSpan"  
      inactivityTimeout="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      reconnectOnTransportFailure="Boolean"  
      maxConcurrentSessions="Integer"  
      timestampValidityDuration="TimeSpan" />  
   <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />  
   <GenericIssuedTokenParameters>   
      <LocalIssuerIssuedTokenParameters keyType=" SymmeticKey/PublicKey"  
        keySize="Integer"  
        tokenType="String" />  
     <IssuedTokenParametersEndpointAddress address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
     <IssuedTokenClient localIssuerChannelBehaviors="String"  
        cacheIssuedTokens="Boolean"  
        maxIssuedTokenCachingTime="TimeSpan"  
        keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />  
     <IssuedTokenClientBehavior issuerAddress="String"  
        behaviorConfiguration="String" />  
     <IssuedTokenClientBehavior address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
   </GenericIssuedTokenParameters>   
</security>  
</binding>  
</customBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65199-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65199-108">Attributes and Elements</span></span>  
 <span data-ttu-id="65199-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="65199-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65199-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65199-110">Attributes</span></span>  
  
|<span data-ttu-id="65199-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="65199-111">Attribute</span></span>|<span data-ttu-id="65199-112">Описание</span><span class="sxs-lookup"><span data-stu-id="65199-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65199-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="65199-113">closeTimeout</span></span>|<span data-ttu-id="65199-114">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="65199-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="65199-115">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="65199-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="65199-116">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="65199-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="65199-117">имя</span><span class="sxs-lookup"><span data-stu-id="65199-117">name</span></span>|<span data-ttu-id="65199-118">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="65199-119">Это значение является определяемой пользователем строкой, которая используется как строка идентификации для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="65199-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="65199-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="65199-121">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="65199-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="65199-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="65199-122">openTimeout</span></span>|<span data-ttu-id="65199-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="65199-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="65199-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="65199-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="65199-125">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="65199-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="65199-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="65199-126">receiveTimeout</span></span>|<span data-ttu-id="65199-127">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="65199-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="65199-128">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="65199-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="65199-129">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="65199-129">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="65199-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="65199-130">sendTimeout</span></span>|<span data-ttu-id="65199-131">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="65199-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="65199-132">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="65199-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="65199-133">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="65199-133">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65199-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65199-134">Child Elements</span></span>  
  
|<span data-ttu-id="65199-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="65199-135">Element</span></span>|<span data-ttu-id="65199-136">Описание</span><span class="sxs-lookup"><span data-stu-id="65199-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65199-137">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="65199-137">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="65199-138">Определяет двусторонний обмен сообщениями в пользовательской привязке.</span><span class="sxs-lookup"><span data-stu-id="65199-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="65199-139">Используется транспортными протоколами, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="65199-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="65199-140">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="65199-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="65199-141">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="65199-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="65199-142">Этот адрес клиента предоставляется атрибутом `ClientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="65199-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="65199-143">Это элемент типа <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|  
|[<span data-ttu-id="65199-144">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="65199-144">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="65199-145">Определяет распознавателя имен узлов в протоколе однорангового разрешения имен (PNRP).</span><span class="sxs-lookup"><span data-stu-id="65199-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="65199-146">Это элемент типа <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|  
|[<span data-ttu-id="65199-147">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="65199-147">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="65199-148">Определяет параметры WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="65199-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="65199-149">Когда этот элемент добавляется к пользовательской привязке, получаемый канал может поддерживать гарантии доставки только один раз.</span><span class="sxs-lookup"><span data-stu-id="65199-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="65199-150">Это элемент типа <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|  
|[<span data-ttu-id="65199-151">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="65199-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="65199-152">Определяет параметры безопасности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="65199-153">Это элемент типа <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|  
|[<span data-ttu-id="65199-154">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="65199-154">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="65199-155">Определяет параметры безопасности привязки потока SSL.</span><span class="sxs-lookup"><span data-stu-id="65199-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="65199-156">Это элемент типа <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|  
|[<span data-ttu-id="65199-157">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="65199-157">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="65199-158">Указывает, что привязка поддерживает поток транзакций, и задает используемый протокол в атрибуте `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="65199-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="65199-159">Это элемент типа <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|  
|[<span data-ttu-id="65199-160">\<windowsstreamsecurity инициирует ></span><span class="sxs-lookup"><span data-stu-id="65199-160">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="65199-161">Определяет параметры для потоковой безопасности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="65199-162">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="65199-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65199-163">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65199-163">Parent Elements</span></span>  
  
|<span data-ttu-id="65199-164">Элемент</span><span class="sxs-lookup"><span data-stu-id="65199-164">Element</span></span>|<span data-ttu-id="65199-165">Описание</span><span class="sxs-lookup"><span data-stu-id="65199-165">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65199-166">привязки</span><span class="sxs-lookup"><span data-stu-id="65199-166">bindings</span></span>|<span data-ttu-id="65199-167">Содержит все привязки для приложений Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="65199-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65199-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="65199-168">Remarks</span></span>  
 <span data-ttu-id="65199-169">Пользовательские привязки предоставляют полный контроль над стеком обмена сообщениями WCF.</span><span class="sxs-lookup"><span data-stu-id="65199-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="65199-170">Путем добавления элементов конфигурации к определенным сущностям можно создавать специально настроенные привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="65199-171">Например, чтобы создать надежную и безопасную привязку на основе протокола HTTPS, пользователь может объединить разделы `httpsTransport`, `reliableSession` и `security`.</span><span class="sxs-lookup"><span data-stu-id="65199-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>  
  
 <span data-ttu-id="65199-172">Отдельная привязка определяет стек обмена сообщениями, задавая элементы конфигурации для элементов стека в том порядке, в котором они присутствуют в стеке.</span><span class="sxs-lookup"><span data-stu-id="65199-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="65199-173">Каждый элемент определяет и задает параметры одного элемента стека.</span><span class="sxs-lookup"><span data-stu-id="65199-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="65199-174">В каждой пользовательской привязке должен быть один и только один транспортный элемент.</span><span class="sxs-lookup"><span data-stu-id="65199-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="65199-175">Без этого элемента стек обмена сообщениями является неполным.</span><span class="sxs-lookup"><span data-stu-id="65199-175">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="65199-176">Важен порядок, в котором элементы присутствуют в стеке, поскольку именно в этом порядке к сообщению применяются операции.</span><span class="sxs-lookup"><span data-stu-id="65199-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="65199-177">Рекомендуется следующий порядок элементов стека:</span><span class="sxs-lookup"><span data-stu-id="65199-177">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="65199-178">Транзакции (необязательный)</span><span class="sxs-lookup"><span data-stu-id="65199-178">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="65199-179">Надежный обмен сообщениями (необязательный)</span><span class="sxs-lookup"><span data-stu-id="65199-179">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="65199-180">Безопасность (необязательный)</span><span class="sxs-lookup"><span data-stu-id="65199-180">Security (optional)</span></span>  
  
4.  <span data-ttu-id="65199-181">Transport</span><span class="sxs-lookup"><span data-stu-id="65199-181">Transport</span></span>  
  
5.  <span data-ttu-id="65199-182">Кодировщик (необязательный)</span><span class="sxs-lookup"><span data-stu-id="65199-182">Encoder (optional)</span></span>  
  
 <span data-ttu-id="65199-183">Используйте пользовательские привязки в случае, когда ни одна из системных привязок не соответствует требованиям службы.</span><span class="sxs-lookup"><span data-stu-id="65199-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="65199-184">Так, с помощью пользовательской привязки можно разрешить использование нового транспорта или нового кодировщика в конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="65199-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>  
  
 <span data-ttu-id="65199-185">Пользовательская привязка создается с использованием одного из <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> из коллекции элементов привязки, которые располагаются в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="65199-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="65199-186">Вверху расположен необязательный элемент <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, который разрешает поток транзакций.</span><span class="sxs-lookup"><span data-stu-id="65199-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="65199-187">Далее следует необязательный элемент <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, который предоставляет сеанс и механизм сортировки в соответствии со спецификацией WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="65199-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="65199-188">Это понятие сеанса может выходить за пределы посредников SOAP и транспорта.</span><span class="sxs-lookup"><span data-stu-id="65199-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="65199-189">Далее следует необязательный элемент привязки безопасности, который предоставляет возможности безопасности, например авторизацию, проверку подлинности, защиту и конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="65199-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="65199-190">Следующие элементы привязки безопасности, предоставляемых Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="65199-190">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
-   <span data-ttu-id="65199-191">Далее следуют необязательные шаблоны сообщений, задаваемые элементами привязки.</span><span class="sxs-lookup"><span data-stu-id="65199-191">Next are the optional message-patterns specified by binding elements:</span></span>  
  
-   <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
  
-   <span data-ttu-id="65199-192">Затем — необязательные элементы привязки обновлений/поддержки транспорта.</span><span class="sxs-lookup"><span data-stu-id="65199-192">Next are the optional transport upgrades/helpers binding elements:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="65199-193">Далее следует обязательный элемент привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="65199-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="65199-194">Можно использовать собственный транспорт или одну из следующих привязок кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="65199-194">You can use your own transport or use one of the following message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
-   <span data-ttu-id="65199-195">Внизу расположен обязательный элемент транспорта.</span><span class="sxs-lookup"><span data-stu-id="65199-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="65199-196">Можно использовать собственный транспорт или использовать один из элементов, предоставляемых Windows Communication Foundation (WCF) привязки транспорта:</span><span class="sxs-lookup"><span data-stu-id="65199-196">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
    -   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
 <span data-ttu-id="65199-197">В следующей таблице приведены сводные данные по параметрам каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="65199-197">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="65199-198">Уровень</span><span class="sxs-lookup"><span data-stu-id="65199-198">Layer</span></span>|<span data-ttu-id="65199-199">Параметры</span><span class="sxs-lookup"><span data-stu-id="65199-199">Options</span></span>|<span data-ttu-id="65199-200">Обязательно</span><span class="sxs-lookup"><span data-stu-id="65199-200">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="65199-201">Поток транзакций</span><span class="sxs-lookup"><span data-stu-id="65199-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="65199-202">Нет</span><span class="sxs-lookup"><span data-stu-id="65199-202">No</span></span>|  
|<span data-ttu-id="65199-203">Надежность</span><span class="sxs-lookup"><span data-stu-id="65199-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="65199-204">Нет</span><span class="sxs-lookup"><span data-stu-id="65199-204">No</span></span>|  
|<span data-ttu-id="65199-205">Безопасность</span><span class="sxs-lookup"><span data-stu-id="65199-205">Security</span></span>|<span data-ttu-id="65199-206">Симметричный, асимметричный, транспортного уровня</span><span class="sxs-lookup"><span data-stu-id="65199-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="65199-207">Нет</span><span class="sxs-lookup"><span data-stu-id="65199-207">No</span></span>|  
|<span data-ttu-id="65199-208">Изменение формы</span><span class="sxs-lookup"><span data-stu-id="65199-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="65199-209">Нет</span><span class="sxs-lookup"><span data-stu-id="65199-209">No</span></span>|  
|<span data-ttu-id="65199-210">Обновления транспорта</span><span class="sxs-lookup"><span data-stu-id="65199-210">Transport Upgrades</span></span>|<span data-ttu-id="65199-211">Поток SSL, поток Windows, распознаватель одноранговых узлов</span><span class="sxs-lookup"><span data-stu-id="65199-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="65199-212">Нет</span><span class="sxs-lookup"><span data-stu-id="65199-212">No</span></span>|  
|<span data-ttu-id="65199-213">кодировка</span><span class="sxs-lookup"><span data-stu-id="65199-213">Encoding</span></span>|<span data-ttu-id="65199-214">Текстовая, двоичная, MTOM, пользовательская</span><span class="sxs-lookup"><span data-stu-id="65199-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="65199-215">Да</span><span class="sxs-lookup"><span data-stu-id="65199-215">Yes</span></span>|  
|<span data-ttu-id="65199-216">Transport</span><span class="sxs-lookup"><span data-stu-id="65199-216">Transport</span></span>|<span data-ttu-id="65199-217">TCP, именованные каналы, HTTP, HTTPS, разновидности MSMQ, пользовательский</span><span class="sxs-lookup"><span data-stu-id="65199-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="65199-218">Да</span><span class="sxs-lookup"><span data-stu-id="65199-218">Yes</span></span>|  
  
 <span data-ttu-id="65199-219">Кроме того, можно определить собственные элементы привязки и вставить их между любыми из приведенных выше заданных уровней.</span><span class="sxs-lookup"><span data-stu-id="65199-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
 <span data-ttu-id="65199-220">Дополнительные сведения об использовании пользовательской привязки для изменения привязки, предоставляемой системой, см. в разделе [как: изменение привязки, предоставляемые системой](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="65199-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
1.  
  
## <a name="see-also"></a><span data-ttu-id="65199-221">См. также</span><span class="sxs-lookup"><span data-stu-id="65199-221">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="65199-222">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="65199-222">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="65199-223">Привязки</span><span class="sxs-lookup"><span data-stu-id="65199-223">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="65199-224">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="65199-224">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="65199-225">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="65199-225">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="65199-226">Элемент customBinding</span><span class="sxs-lookup"><span data-stu-id="65199-226">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="65199-227">Привязки</span><span class="sxs-lookup"><span data-stu-id="65199-227">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="65199-228">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="65199-228">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="65199-229">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="65199-229">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)
