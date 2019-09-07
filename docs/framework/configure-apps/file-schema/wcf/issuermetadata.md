---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397885"
---
# <a name="issuermetadata"></a><span data-ttu-id="7b16e-101">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="7b16e-101">\<issuerMetadata></span></span>

<span data-ttu-id="7b16e-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b16e-103">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7b16e-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7b16e-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="7b16e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="7b16e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7b16e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="7b16e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> сообщения**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b16e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="7b16e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="7b16e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b16e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b16e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b16e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b16e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b16e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b16e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b16e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b16e-113">Attributes</span></span>  
  
|<span data-ttu-id="7b16e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b16e-114">Attribute</span></span>|<span data-ttu-id="7b16e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7b16e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b16e-116">адрес</span><span class="sxs-lookup"><span data-stu-id="7b16e-116">address</span></span>|<span data-ttu-id="7b16e-117">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="7b16e-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="7b16e-118">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7b16e-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="7b16e-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="7b16e-119">The address must be an absolute URI.</span></span> <span data-ttu-id="7b16e-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="7b16e-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b16e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b16e-121">Child Elements</span></span>  
  
|<span data-ttu-id="7b16e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b16e-122">Element</span></span>|<span data-ttu-id="7b16e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7b16e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b16e-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="7b16e-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="7b16e-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="7b16e-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="7b16e-126">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="7b16e-126">\<identity></span></span>](identity.md)|<span data-ttu-id="7b16e-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7b16e-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b16e-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b16e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7b16e-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b16e-129">Element</span></span>|<span data-ttu-id="7b16e-130">Описание</span><span class="sxs-lookup"><span data-stu-id="7b16e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b16e-131">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="7b16e-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="7b16e-132">Определяет параметры безопасности на уровне сообщений для [ \<элемента WSFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7b16e-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b16e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7b16e-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="7b16e-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="7b16e-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7b16e-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="7b16e-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7b16e-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="7b16e-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="7b16e-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="7b16e-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
