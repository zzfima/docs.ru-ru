---
title: '&lt;issuerMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7e96c41348dea40806c2aca331d7f8ca9499a78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="b3289-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="b3289-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="b3289-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b3289-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b3289-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b3289-104">\<bindings></span></span>  
<span data-ttu-id="b3289-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b3289-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="b3289-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b3289-106">\<binding></span></span>  
<span data-ttu-id="b3289-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b3289-107">\<security></span></span>  
<span data-ttu-id="b3289-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="b3289-108">\<message></span></span>  
<span data-ttu-id="b3289-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="b3289-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3289-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3289-110">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3289-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3289-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3289-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3289-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3289-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3289-113">Attributes</span></span>  
  
|<span data-ttu-id="b3289-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3289-114">Attribute</span></span>|<span data-ttu-id="b3289-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b3289-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3289-116">address</span><span class="sxs-lookup"><span data-stu-id="b3289-116">address</span></span>|<span data-ttu-id="b3289-117">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="b3289-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="b3289-118">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b3289-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="b3289-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="b3289-119">The address must be an absolute URI.</span></span> <span data-ttu-id="b3289-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="b3289-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3289-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3289-121">Child Elements</span></span>  
  
|<span data-ttu-id="b3289-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3289-122">Element</span></span>|<span data-ttu-id="b3289-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b3289-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3289-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="b3289-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="b3289-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="b3289-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="b3289-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="b3289-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b3289-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b3289-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3289-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3289-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b3289-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3289-129">Element</span></span>|<span data-ttu-id="b3289-130">Описание</span><span class="sxs-lookup"><span data-stu-id="b3289-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3289-131">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="b3289-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="b3289-132">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="b3289-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3289-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b3289-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="b3289-134">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b3289-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b3289-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b3289-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b3289-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="b3289-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="b3289-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b3289-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
