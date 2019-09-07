---
title: <security> из <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c07d1ca18837f66548411262b84b9a326f5ec4a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399733"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="ece86-102">\<> безопасности > \<WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ece86-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="ece86-103">Определяет параметры [ \<безопасности > WSFederationHttpBinding](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ece86-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="ece86-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ece86-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ece86-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ece86-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ece86-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ece86-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ece86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ece86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="ece86-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="ece86-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ece86-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="ece86-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece86-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ece86-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
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
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
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
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ece86-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ece86-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ece86-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ece86-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ece86-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ece86-113">Attributes</span></span>  
  
|<span data-ttu-id="ece86-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ece86-114">Attribute</span></span>|<span data-ttu-id="ece86-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ece86-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ece86-116">Mode</span><span class="sxs-lookup"><span data-stu-id="ece86-116">Mode</span></span>|<span data-ttu-id="ece86-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ece86-117">Optional.</span></span> <span data-ttu-id="ece86-118">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ece86-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ece86-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="ece86-119">The default value is `Message`.</span></span> <span data-ttu-id="ece86-120">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ece86-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ece86-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="ece86-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="ece86-122">Значение</span><span class="sxs-lookup"><span data-stu-id="ece86-122">Value</span></span>|<span data-ttu-id="ece86-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ece86-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ece86-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ece86-124">None</span></span>|<span data-ttu-id="ece86-125">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="ece86-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="ece86-126">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ece86-126">Message</span></span>|<span data-ttu-id="ece86-127">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="ece86-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="ece86-128">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="ece86-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="ece86-129">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="ece86-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="ece86-130">Проверка подлинности клиента осуществляется с использованием маркера, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ece86-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="ece86-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ece86-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="ece86-132">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ece86-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="ece86-133">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="ece86-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="ece86-134">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ece86-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ece86-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ece86-135">Child Elements</span></span>  
  
|<span data-ttu-id="ece86-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="ece86-136">Element</span></span>|<span data-ttu-id="ece86-137">Описание</span><span class="sxs-lookup"><span data-stu-id="ece86-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ece86-138">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="ece86-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="ece86-139">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="ece86-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="ece86-140">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="ece86-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ece86-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ece86-141">Parent Elements</span></span>  
  
|<span data-ttu-id="ece86-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="ece86-142">Element</span></span>|<span data-ttu-id="ece86-143">Описание</span><span class="sxs-lookup"><span data-stu-id="ece86-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ece86-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ece86-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ece86-145">Определяет все возможности [ \<привязки > WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ece86-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ece86-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ece86-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="ece86-147">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ece86-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="ece86-148">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ece86-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ece86-149">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="ece86-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="ece86-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="ece86-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ece86-151">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ece86-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ece86-152">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ece86-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ece86-153">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ece86-153">\<binding></span></span>](../../../misc/binding.md)
