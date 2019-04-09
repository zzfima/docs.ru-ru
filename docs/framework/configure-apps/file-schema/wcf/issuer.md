---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160827"
---
# <a name="issuer"></a><span data-ttu-id="fbcc5-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="fbcc5-101">\<issuer></span></span>
<span data-ttu-id="fbcc5-102">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="fbcc5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fbcc5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fbcc5-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-104">\<bindings></span></span>  
<span data-ttu-id="fbcc5-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="fbcc5-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-106">\<binding></span></span>  
<span data-ttu-id="fbcc5-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-107">\<security></span></span>  
<span data-ttu-id="fbcc5-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-108">\<message></span></span>  
<span data-ttu-id="fbcc5-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="fbcc5-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbcc5-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbcc5-110">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
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
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbcc5-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fbcc5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fbcc5-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbcc5-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fbcc5-113">Attributes</span></span>  
  
|<span data-ttu-id="fbcc5-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fbcc5-114">Attribute</span></span>|<span data-ttu-id="fbcc5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fbcc5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbcc5-116">адрес</span><span class="sxs-lookup"><span data-stu-id="fbcc5-116">address</span></span>|<span data-ttu-id="fbcc5-117">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-117">Required string.</span></span> <span data-ttu-id="fbcc5-118">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbcc5-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fbcc5-119">Child Elements</span></span>  
  
|<span data-ttu-id="fbcc5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbcc5-120">Element</span></span>|<span data-ttu-id="fbcc5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fbcc5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbcc5-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="fbcc5-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="fbcc5-123">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="fbcc5-124">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="fbcc5-125">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fbcc5-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fbcc5-126">Parent Elements</span></span>  
  
|<span data-ttu-id="fbcc5-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbcc5-127">Element</span></span>|<span data-ttu-id="fbcc5-128">Описание</span><span class="sxs-lookup"><span data-stu-id="fbcc5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbcc5-129">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="fbcc5-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="fbcc5-130">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbcc5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fbcc5-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="fbcc5-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="fbcc5-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fbcc5-133">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="fbcc5-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fbcc5-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="fbcc5-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fbcc5-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="fbcc5-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fbcc5-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="fbcc5-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="fbcc5-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="fbcc5-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
