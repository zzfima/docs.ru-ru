---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397915"
---
# <a name="issuer"></a><span data-ttu-id="b6d96-101">\<> издателя</span><span class="sxs-lookup"><span data-stu-id="b6d96-101">\<issuer></span></span>
<span data-ttu-id="b6d96-102">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6d96-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="b6d96-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6d96-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6d96-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b6d96-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b6d96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="b6d96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b6d96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b6d96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> сообщения**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6d96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b6d96-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> издателя**</span><span class="sxs-lookup"><span data-stu-id="b6d96-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d96-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6d96-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6d96-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6d96-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b6d96-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6d96-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6d96-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6d96-114">Attributes</span></span>  
  
|<span data-ttu-id="b6d96-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6d96-115">Attribute</span></span>|<span data-ttu-id="b6d96-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b6d96-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6d96-117">адрес</span><span class="sxs-lookup"><span data-stu-id="b6d96-117">address</span></span>|<span data-ttu-id="b6d96-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="b6d96-118">Required string.</span></span> <span data-ttu-id="b6d96-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6d96-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6d96-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6d96-120">Child Elements</span></span>  
  
|<span data-ttu-id="b6d96-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6d96-121">Element</span></span>|<span data-ttu-id="b6d96-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b6d96-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6d96-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="b6d96-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="b6d96-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="b6d96-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="b6d96-125">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="b6d96-125">\<identity></span></span>](identity.md)|<span data-ttu-id="b6d96-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="b6d96-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6d96-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6d96-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b6d96-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6d96-128">Element</span></span>|<span data-ttu-id="b6d96-129">Описание</span><span class="sxs-lookup"><span data-stu-id="b6d96-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6d96-130">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="b6d96-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="b6d96-131">Определяет параметры безопасности на уровне сообщений для [ \<элемента WSFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b6d96-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6d96-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b6d96-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="b6d96-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="b6d96-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b6d96-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b6d96-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b6d96-135">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="b6d96-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b6d96-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b6d96-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b6d96-137">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="b6d96-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="b6d96-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b6d96-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
