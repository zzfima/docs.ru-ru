---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756264"
---
# <a name="issuer"></a><span data-ttu-id="9fd5a-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="9fd5a-101">\<issuer></span></span>
<span data-ttu-id="9fd5a-102">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="9fd5a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9fd5a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9fd5a-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-104">\<bindings></span></span>  
<span data-ttu-id="9fd5a-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="9fd5a-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-106">\<binding></span></span>  
<span data-ttu-id="9fd5a-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-107">\<security></span></span>  
<span data-ttu-id="9fd5a-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-108">\<message></span></span>  
<span data-ttu-id="9fd5a-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="9fd5a-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd5a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fd5a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fd5a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9fd5a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9fd5a-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fd5a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fd5a-113">Attributes</span></span>  
  
|<span data-ttu-id="9fd5a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9fd5a-114">Attribute</span></span>|<span data-ttu-id="9fd5a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd5a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fd5a-116">адрес</span><span class="sxs-lookup"><span data-stu-id="9fd5a-116">address</span></span>|<span data-ttu-id="9fd5a-117">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-117">Required string.</span></span> <span data-ttu-id="9fd5a-118">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fd5a-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fd5a-119">Child Elements</span></span>  
  
|<span data-ttu-id="9fd5a-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fd5a-120">Element</span></span>|<span data-ttu-id="9fd5a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd5a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fd5a-122">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="9fd5a-123">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="9fd5a-124">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9fd5a-125">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fd5a-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9fd5a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9fd5a-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fd5a-127">Element</span></span>|<span data-ttu-id="9fd5a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="9fd5a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fd5a-129">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="9fd5a-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="9fd5a-130">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fd5a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9fd5a-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="9fd5a-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="9fd5a-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9fd5a-133">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9fd5a-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9fd5a-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="9fd5a-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9fd5a-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9fd5a-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9fd5a-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="9fd5a-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="9fd5a-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9fd5a-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
