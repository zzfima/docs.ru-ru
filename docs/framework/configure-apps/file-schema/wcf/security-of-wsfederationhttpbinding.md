---
title: '&lt;security&gt; для &lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
author: BrucePerlerMS
ms.openlocfilehash: 7c7868561ea4d41b308d3bcd963e10e9b81df314
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078244"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="dfbb2-102">&lt;security&gt; для &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="dfbb2-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="dfbb2-103">Определяет параметры безопасности [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dfbb2-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="dfbb2-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dfbb2-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-105">\<bindings></span></span>  
<span data-ttu-id="dfbb2-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="dfbb2-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-107">\<binding></span></span>  
<span data-ttu-id="dfbb2-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfbb2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfbb2-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
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
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
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
    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfbb2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dfbb2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dfbb2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfbb2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dfbb2-112">Attributes</span></span>  
  
|<span data-ttu-id="dfbb2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dfbb2-113">Attribute</span></span>|<span data-ttu-id="dfbb2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dfbb2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfbb2-115">Mode</span><span class="sxs-lookup"><span data-stu-id="dfbb2-115">Mode</span></span>|<span data-ttu-id="dfbb2-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-116">Optional.</span></span> <span data-ttu-id="dfbb2-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="dfbb2-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-118">The default value is `Message`.</span></span> <span data-ttu-id="dfbb2-119">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="dfbb2-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="dfbb2-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="dfbb2-121">Значение</span><span class="sxs-lookup"><span data-stu-id="dfbb2-121">Value</span></span>|<span data-ttu-id="dfbb2-122">Описание</span><span class="sxs-lookup"><span data-stu-id="dfbb2-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dfbb2-123">Нет</span><span class="sxs-lookup"><span data-stu-id="dfbb2-123">None</span></span>|<span data-ttu-id="dfbb2-124">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="dfbb2-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="dfbb2-125">Message</span></span>|<span data-ttu-id="dfbb2-126">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="dfbb2-127">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="dfbb2-128">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="dfbb2-129">Проверка подлинности клиента осуществляется с использованием маркера, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="dfbb2-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="dfbb2-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="dfbb2-131">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="dfbb2-132">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="dfbb2-133">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfbb2-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dfbb2-134">Child Elements</span></span>  
  
|<span data-ttu-id="dfbb2-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="dfbb2-135">Element</span></span>|<span data-ttu-id="dfbb2-136">Описание</span><span class="sxs-lookup"><span data-stu-id="dfbb2-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfbb2-137">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="dfbb2-138">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="dfbb2-139">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="dfbb2-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfbb2-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dfbb2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="dfbb2-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="dfbb2-141">Element</span></span>|<span data-ttu-id="dfbb2-142">Описание</span><span class="sxs-lookup"><span data-stu-id="dfbb2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfbb2-143">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="dfbb2-144">Определяет все возможности привязки [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dfbb2-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfbb2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="dfbb2-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="dfbb2-146">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="dfbb2-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="dfbb2-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dfbb2-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="dfbb2-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="dfbb2-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="dfbb2-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="dfbb2-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="dfbb2-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="dfbb2-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="dfbb2-151">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="dfbb2-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="dfbb2-152">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dfbb2-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
