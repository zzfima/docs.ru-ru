---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 262ac9be6d5ce6466cf9aff33c0c2791c0e149dd
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988381"
---
# <a name="identity"></a><span data-ttu-id="6255f-101">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="6255f-101">\<identity></span></span>
<span data-ttu-id="6255f-102">Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="6255f-103">В процессе подтверждения между клиентом и службой инфраструктура Windows Communication Foundation (WCF) обеспечит соответствие идентификатора ожидаемой службы значениям этого элемента и, таким образом, может пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6255f-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="6255f-104">Дополнительные сведения см. в статье [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="6255f-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="6255f-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6255f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6255f-106">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="6255f-106">\<client></span></span>  
<span data-ttu-id="6255f-107">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="6255f-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6255f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6255f-108">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6255f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6255f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6255f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6255f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6255f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6255f-111">Attributes</span></span>  
 <span data-ttu-id="6255f-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="6255f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6255f-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6255f-113">Child Elements</span></span>  
  
|<span data-ttu-id="6255f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="6255f-114">Element</span></span>|<span data-ttu-id="6255f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6255f-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6255f-116">сертификат</span><span class="sxs-lookup"><span data-stu-id="6255f-116">certificate</span></span>|<span data-ttu-id="6255f-117">Задает параметры сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="6255f-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="6255f-118">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="6255f-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="6255f-119">Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="6255f-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="6255f-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="6255f-120">certificateReference</span></span>|<span data-ttu-id="6255f-121">Задает параметры для проверки сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="6255f-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="6255f-122">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="6255f-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="6255f-123">dns</span><span class="sxs-lookup"><span data-stu-id="6255f-123">dns</span></span>|<span data-ttu-id="6255f-124">Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="6255f-125">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="6255f-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="6255f-126">rsa</span><span class="sxs-lookup"><span data-stu-id="6255f-126">rsa</span></span>|<span data-ttu-id="6255f-127">Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="6255f-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="6255f-128">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="6255f-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="6255f-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="6255f-129">servicePrincipalName</span></span>|<span data-ttu-id="6255f-130">Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="6255f-131">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="6255f-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="6255f-132">Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="6255f-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="6255f-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6255f-133">userPrincipalName</span></span>|<span data-ttu-id="6255f-134">Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть.</span><span class="sxs-lookup"><span data-stu-id="6255f-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="6255f-135">Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ (\@) и, как правило, родительский домен системы доменных имен.</span><span class="sxs-lookup"><span data-stu-id="6255f-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="6255f-136">Например, Джефф в дереве доменов Fabrikam.com может иметь имя [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="6255f-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="6255f-137">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="6255f-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="6255f-138">Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="6255f-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6255f-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6255f-139">Parent Elements</span></span>  
  
|<span data-ttu-id="6255f-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="6255f-140">Element</span></span>|<span data-ttu-id="6255f-141">Описание</span><span class="sxs-lookup"><span data-stu-id="6255f-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6255f-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="6255f-142">\<custom></span></span>](custom.md)|<span data-ttu-id="6255f-143">Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="6255f-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="6255f-144">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="6255f-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="6255f-145">Настраивает конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="6255f-146">\<Конечная точка \<> клиента ></span><span class="sxs-lookup"><span data-stu-id="6255f-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="6255f-147">Настраивает конечные точки канала.</span><span class="sxs-lookup"><span data-stu-id="6255f-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="6255f-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="6255f-148">\<issuer></span></span>](issuer.md)|<span data-ttu-id="6255f-149">Задает службу маркеров безопасности для федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="6255f-150">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="6255f-150">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="6255f-151">Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="6255f-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="6255f-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="6255f-152">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="6255f-153">Задает параметры для выданного маркера в настраиваемой привязке.</span><span class="sxs-lookup"><span data-stu-id="6255f-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="6255f-154">\<Локалиссуер ></span><span class="sxs-lookup"><span data-stu-id="6255f-154">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="6255f-155">Задает локальную службу маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6255f-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6255f-156">См. также</span><span class="sxs-lookup"><span data-stu-id="6255f-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="6255f-157">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="6255f-157">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6255f-158">Конеч Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="6255f-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
