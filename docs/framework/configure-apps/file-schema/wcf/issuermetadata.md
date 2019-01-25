---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 22e30e0962ec8d2eb0f7e52f4db143fba9bbf703
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491562"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="c9863-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="c9863-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="c9863-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c9863-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c9863-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c9863-104">\<bindings></span></span>  
<span data-ttu-id="c9863-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c9863-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="c9863-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c9863-106">\<binding></span></span>  
<span data-ttu-id="c9863-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c9863-107">\<security></span></span>  
<span data-ttu-id="c9863-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="c9863-108">\<message></span></span>  
<span data-ttu-id="c9863-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="c9863-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9863-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9863-110">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9863-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9863-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c9863-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9863-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9863-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9863-113">Attributes</span></span>  
  
|<span data-ttu-id="c9863-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9863-114">Attribute</span></span>|<span data-ttu-id="c9863-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c9863-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9863-116">address</span><span class="sxs-lookup"><span data-stu-id="c9863-116">address</span></span>|<span data-ttu-id="c9863-117">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="c9863-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="c9863-118">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c9863-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="c9863-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c9863-119">The address must be an absolute URI.</span></span> <span data-ttu-id="c9863-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c9863-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9863-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9863-121">Child Elements</span></span>  
  
|<span data-ttu-id="c9863-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9863-122">Element</span></span>|<span data-ttu-id="c9863-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="c9863-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9863-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="c9863-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="c9863-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="c9863-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="c9863-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="c9863-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c9863-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c9863-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9863-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9863-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c9863-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9863-129">Element</span></span>|<span data-ttu-id="c9863-130">Описание</span><span class="sxs-lookup"><span data-stu-id="c9863-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9863-131">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="c9863-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c9863-132">Определяет параметры безопасности уровня сообщений для [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c9863-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9863-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c9863-133">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="c9863-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="c9863-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c9863-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="c9863-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c9863-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="c9863-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c9863-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="c9863-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
