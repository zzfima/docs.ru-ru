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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28746481bd24eb0d80304456ea8f34f505a016b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="de547-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="de547-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="de547-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="de547-103">\<system.serviceModel></span></span>  
<span data-ttu-id="de547-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="de547-104">\<bindings></span></span>  
<span data-ttu-id="de547-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="de547-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="de547-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="de547-106">\<binding></span></span>  
<span data-ttu-id="de547-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="de547-107">\<security></span></span>  
<span data-ttu-id="de547-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="de547-108">\<message></span></span>  
<span data-ttu-id="de547-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="de547-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de547-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de547-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de547-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de547-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de547-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="de547-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de547-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de547-113">Attributes</span></span>  
  
|<span data-ttu-id="de547-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="de547-114">Attribute</span></span>|<span data-ttu-id="de547-115">Описание</span><span class="sxs-lookup"><span data-stu-id="de547-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de547-116">address</span><span class="sxs-lookup"><span data-stu-id="de547-116">address</span></span>|<span data-ttu-id="de547-117">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="de547-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="de547-118">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="de547-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="de547-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="de547-119">The address must be an absolute URI.</span></span> <span data-ttu-id="de547-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="de547-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de547-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de547-121">Child Elements</span></span>  
  
|<span data-ttu-id="de547-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="de547-122">Element</span></span>|<span data-ttu-id="de547-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="de547-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de547-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="de547-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="de547-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="de547-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="de547-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="de547-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="de547-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="de547-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de547-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de547-128">Parent Elements</span></span>  
  
|<span data-ttu-id="de547-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="de547-129">Element</span></span>|<span data-ttu-id="de547-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="de547-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de547-131">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="de547-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="de547-132">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="de547-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de547-133">См. также</span><span class="sxs-lookup"><span data-stu-id="de547-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="de547-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="de547-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="de547-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="de547-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="de547-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="de547-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="de547-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="de547-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
