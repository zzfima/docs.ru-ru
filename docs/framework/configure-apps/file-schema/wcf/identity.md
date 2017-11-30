---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa6bfdf72bd292599867bf7a9571ecd6b408a2c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="a5529-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="a5529-102">&lt;identity&gt;</span></span>
<span data-ttu-id="a5529-103">Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы.</span><span class="sxs-lookup"><span data-stu-id="a5529-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="a5529-104">Во время процесса подтверждения между клиентом и службой инфраструктура [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] обеспечивает соответствие удостоверения ожидаемой службы значению этого элемента. Таким образом происходит проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="a5529-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="a5529-105">Дополнительные сведения см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a5529-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="a5529-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a5529-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a5529-107">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="a5529-107">\<client></span></span>  
<span data-ttu-id="a5529-108">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="a5529-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5529-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5529-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5529-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a5529-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5529-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a5529-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5529-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a5529-112">Attributes</span></span>  
 <span data-ttu-id="a5529-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a5529-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5529-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a5529-114">Child Elements</span></span>  
  
|<span data-ttu-id="a5529-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5529-115">Element</span></span>|<span data-ttu-id="a5529-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a5529-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5529-117">certificate</span><span class="sxs-lookup"><span data-stu-id="a5529-117">certificate</span></span>|<span data-ttu-id="a5529-118">Задает параметры сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="a5529-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="a5529-119">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="a5529-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="a5529-120">Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="a5529-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="a5529-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="a5529-121">certificateReference</span></span>|<span data-ttu-id="a5529-122">Задает параметры для проверки сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="a5529-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="a5529-123">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="a5529-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="a5529-124">dns</span><span class="sxs-lookup"><span data-stu-id="a5529-124">dns</span></span>|<span data-ttu-id="a5529-125">Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="a5529-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="a5529-126">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="a5529-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="a5529-127">rsa</span><span class="sxs-lookup"><span data-stu-id="a5529-127">rsa</span></span>|<span data-ttu-id="a5529-128">Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="a5529-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="a5529-129">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="a5529-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="a5529-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="a5529-130">servicePrincipalName</span></span>|<span data-ttu-id="a5529-131">Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="a5529-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="a5529-132">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="a5529-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a5529-133">Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="a5529-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="a5529-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a5529-134">userPrincipalName</span></span>|<span data-ttu-id="a5529-135">Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть.</span><span class="sxs-lookup"><span data-stu-id="a5529-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="a5529-136">Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ (@), а затем обычно следует родительский домен службы доменных имен.</span><span class="sxs-lookup"><span data-stu-id="a5529-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="a5529-137">Например, у Джефа в дереве домена Fabrikam.com может быть имя участника-пользователя [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="a5529-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a5529-138">Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="a5529-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5529-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a5529-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a5529-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5529-140">Element</span></span>|<span data-ttu-id="a5529-141">Описание</span><span class="sxs-lookup"><span data-stu-id="a5529-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5529-142">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="a5529-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="a5529-143">Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="a5529-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="a5529-144">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="a5529-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="a5529-145">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a5529-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="a5529-146">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="a5529-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="a5529-147">Задает службу маркеров безопасности для федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="a5529-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="a5529-148">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="a5529-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="a5529-149">Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="a5529-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="a5529-150">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a5529-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="a5529-151">Задает параметры для выданного маркера в настраиваемой привязке.</span><span class="sxs-lookup"><span data-stu-id="a5529-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="a5529-152">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="a5529-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="a5529-153">Задает локальную службу маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="a5529-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5529-154">См. также</span><span class="sxs-lookup"><span data-stu-id="a5529-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="a5529-155">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a5529-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a5529-156">Конечные точки: Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="a5529-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
