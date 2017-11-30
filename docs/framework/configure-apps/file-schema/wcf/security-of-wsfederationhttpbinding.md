---
title: "&lt;security&gt; для &lt;wsFederationHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: dd4f517c17efce85f7a83d7d8545cf58322d5373
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="f6520-102">&lt;security&gt; для &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f6520-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="f6520-103">Определяет параметры безопасности [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f6520-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="f6520-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f6520-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6520-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f6520-105">\<bindings></span></span>  
<span data-ttu-id="f6520-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="f6520-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="f6520-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f6520-107">\<binding></span></span>  
<span data-ttu-id="f6520-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="f6520-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6520-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6520-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6520-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6520-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f6520-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6520-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6520-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6520-112">Attributes</span></span>  
  
|<span data-ttu-id="f6520-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f6520-113">Attribute</span></span>|<span data-ttu-id="f6520-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f6520-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6520-115">Mode</span><span class="sxs-lookup"><span data-stu-id="f6520-115">Mode</span></span>|<span data-ttu-id="f6520-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="f6520-116">Optional.</span></span> <span data-ttu-id="f6520-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6520-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="f6520-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="f6520-118">The default value is `Message`.</span></span> <span data-ttu-id="f6520-119">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f6520-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f6520-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="f6520-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="f6520-121">Значение</span><span class="sxs-lookup"><span data-stu-id="f6520-121">Value</span></span>|<span data-ttu-id="f6520-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f6520-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f6520-123">Нет</span><span class="sxs-lookup"><span data-stu-id="f6520-123">None</span></span>|<span data-ttu-id="f6520-124">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="f6520-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="f6520-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f6520-125">Message</span></span>|<span data-ttu-id="f6520-126">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="f6520-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="f6520-127">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="f6520-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="f6520-128">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="f6520-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="f6520-129">Проверка подлинности клиента осуществляется с использованием маркера, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6520-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="f6520-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="f6520-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="f6520-131">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f6520-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="f6520-132">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="f6520-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="f6520-133">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6520-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6520-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6520-134">Child Elements</span></span>  
  
|<span data-ttu-id="f6520-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6520-135">Element</span></span>|<span data-ttu-id="f6520-136">Описание</span><span class="sxs-lookup"><span data-stu-id="f6520-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6520-137">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="f6520-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="f6520-138">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="f6520-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="f6520-139">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="f6520-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6520-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6520-140">Parent Elements</span></span>  
  
|<span data-ttu-id="f6520-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6520-141">Element</span></span>|<span data-ttu-id="f6520-142">Описание</span><span class="sxs-lookup"><span data-stu-id="f6520-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6520-143">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f6520-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f6520-144">Определяет все возможности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f6520-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6520-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f6520-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="f6520-146">Как: создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f6520-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="f6520-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f6520-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f6520-148">При выборе типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="f6520-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="f6520-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="f6520-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f6520-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f6520-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f6520-151">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="f6520-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f6520-152">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f6520-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
