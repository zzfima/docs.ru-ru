---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929374"
---
# <a name="issuer"></a><span data-ttu-id="ab919-101">\<> издателя</span><span class="sxs-lookup"><span data-stu-id="ab919-101">\<issuer></span></span>
<span data-ttu-id="ab919-102">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab919-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="ab919-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="ab919-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ab919-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ab919-104">\<bindings></span></span>  
<span data-ttu-id="ab919-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ab919-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="ab919-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ab919-106">\<binding></span></span>  
<span data-ttu-id="ab919-107">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="ab919-107">\<security></span></span>  
<span data-ttu-id="ab919-108">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="ab919-108">\<message></span></span>  
<span data-ttu-id="ab919-109">\<> издателя</span><span class="sxs-lookup"><span data-stu-id="ab919-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab919-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab919-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab919-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ab919-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ab919-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ab919-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab919-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ab919-113">Attributes</span></span>  
  
|<span data-ttu-id="ab919-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ab919-114">Attribute</span></span>|<span data-ttu-id="ab919-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ab919-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab919-116">адрес</span><span class="sxs-lookup"><span data-stu-id="ab919-116">address</span></span>|<span data-ttu-id="ab919-117">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="ab919-117">Required string.</span></span> <span data-ttu-id="ab919-118">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab919-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab919-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ab919-119">Child Elements</span></span>  
  
|<span data-ttu-id="ab919-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab919-120">Element</span></span>|<span data-ttu-id="ab919-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ab919-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab919-122">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="ab919-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="ab919-123">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="ab919-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="ab919-124">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="ab919-124">\<identity></span></span>](identity.md)|<span data-ttu-id="ab919-125">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="ab919-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab919-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ab919-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ab919-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab919-127">Element</span></span>|<span data-ttu-id="ab919-128">Описание</span><span class="sxs-lookup"><span data-stu-id="ab919-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab919-129">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="ab919-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="ab919-130">Определяет параметры безопасности на уровне сообщений для [ \<элемента WSFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ab919-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab919-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ab919-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="ab919-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="ab919-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ab919-133">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ab919-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ab919-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="ab919-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ab919-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ab919-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ab919-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="ab919-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ab919-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ab919-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
