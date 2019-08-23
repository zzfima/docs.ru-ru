---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913522"
---
# <a name="issuermetadata"></a><span data-ttu-id="74004-101">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="74004-101">\<issuerMetadata></span></span>
<span data-ttu-id="74004-102">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="74004-102">\<system.serviceModel></span></span>  
<span data-ttu-id="74004-103">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="74004-103">\<bindings></span></span>  
<span data-ttu-id="74004-104">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="74004-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="74004-105">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="74004-105">\<binding></span></span>  
<span data-ttu-id="74004-106">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="74004-106">\<security></span></span>  
<span data-ttu-id="74004-107">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="74004-107">\<message></span></span>  
<span data-ttu-id="74004-108">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="74004-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74004-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74004-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74004-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74004-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74004-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74004-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74004-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74004-112">Attributes</span></span>  
  
|<span data-ttu-id="74004-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="74004-113">Attribute</span></span>|<span data-ttu-id="74004-114">Описание</span><span class="sxs-lookup"><span data-stu-id="74004-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74004-115">адрес</span><span class="sxs-lookup"><span data-stu-id="74004-115">address</span></span>|<span data-ttu-id="74004-116">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="74004-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="74004-117">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="74004-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="74004-118">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="74004-118">The address must be an absolute URI.</span></span> <span data-ttu-id="74004-119">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="74004-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74004-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74004-120">Child Elements</span></span>  
  
|<span data-ttu-id="74004-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="74004-121">Element</span></span>|<span data-ttu-id="74004-122">Описание</span><span class="sxs-lookup"><span data-stu-id="74004-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74004-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="74004-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="74004-124">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="74004-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="74004-125">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="74004-125">\<identity></span></span>](identity.md)|<span data-ttu-id="74004-126">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="74004-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74004-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74004-127">Parent Elements</span></span>  
  
|<span data-ttu-id="74004-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="74004-128">Element</span></span>|<span data-ttu-id="74004-129">Описание</span><span class="sxs-lookup"><span data-stu-id="74004-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74004-130">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="74004-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="74004-131">Определяет параметры безопасности на уровне сообщений для [ \<элемента WSFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="74004-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74004-132">См. также</span><span class="sxs-lookup"><span data-stu-id="74004-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="74004-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="74004-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="74004-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="74004-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="74004-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="74004-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="74004-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="74004-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
