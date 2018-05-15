---
title: '&lt;Издатель&gt;'
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 638b206f5372a654eca68d2f6ebb69bb0ac9e241
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuergt"></a><span data-ttu-id="8073e-102">&lt;Издатель&gt;</span><span class="sxs-lookup"><span data-stu-id="8073e-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="8073e-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="8073e-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="8073e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8073e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8073e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8073e-105">\<bindings></span></span>  
<span data-ttu-id="8073e-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8073e-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="8073e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8073e-107">\<binding></span></span>  
<span data-ttu-id="8073e-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="8073e-108">\<security></span></span>  
<span data-ttu-id="8073e-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="8073e-109">\<message></span></span>  
<span data-ttu-id="8073e-110">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="8073e-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8073e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8073e-111">Syntax</span></span>  
  
```xml  
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
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8073e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8073e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8073e-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8073e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8073e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8073e-114">Attributes</span></span>  
  
|<span data-ttu-id="8073e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8073e-115">Attribute</span></span>|<span data-ttu-id="8073e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8073e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8073e-117">address</span><span class="sxs-lookup"><span data-stu-id="8073e-117">address</span></span>|<span data-ttu-id="8073e-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="8073e-118">Required string.</span></span> <span data-ttu-id="8073e-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="8073e-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8073e-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8073e-120">Child Elements</span></span>  
  
|<span data-ttu-id="8073e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="8073e-121">Element</span></span>|<span data-ttu-id="8073e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8073e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8073e-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="8073e-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8073e-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="8073e-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="8073e-125">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8073e-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8073e-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="8073e-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8073e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8073e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8073e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="8073e-128">Element</span></span>|<span data-ttu-id="8073e-129">Описание</span><span class="sxs-lookup"><span data-stu-id="8073e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8073e-130">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="8073e-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="8073e-131">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="8073e-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8073e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8073e-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="8073e-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="8073e-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8073e-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="8073e-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="8073e-135">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="8073e-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8073e-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="8073e-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="8073e-137">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="8073e-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="8073e-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="8073e-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
