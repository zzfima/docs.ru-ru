---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: d5d06953c67b90e8367f2c0d01a670a46f487526
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925416"
---
# <a name="identity"></a><span data-ttu-id="2c25e-101">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="2c25e-101">\<identity></span></span>
<span data-ttu-id="2c25e-102">Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="2c25e-103">В процессе подтверждения между клиентом и службой инфраструктура Windows Communication Foundation (WCF) обеспечит соответствие идентификатора ожидаемой службы значениям этого элемента и, таким образом, может пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c25e-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="2c25e-104">Дополнительные сведения см. в статье [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c25e-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="2c25e-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2c25e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c25e-106">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="2c25e-106">\<client></span></span>  
<span data-ttu-id="2c25e-107">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="2c25e-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c25e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c25e-108">Syntax</span></span>  
  
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
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c25e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c25e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2c25e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c25e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c25e-111">Attributes</span></span>  
 <span data-ttu-id="2c25e-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c25e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c25e-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c25e-113">Child Elements</span></span>  
  
|<span data-ttu-id="2c25e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c25e-114">Element</span></span>|<span data-ttu-id="2c25e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2c25e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c25e-116">сертификат</span><span class="sxs-lookup"><span data-stu-id="2c25e-116">certificate</span></span>|<span data-ttu-id="2c25e-117">Задает параметры сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="2c25e-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="2c25e-118">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="2c25e-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="2c25e-119">Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="2c25e-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="2c25e-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="2c25e-120">certificateReference</span></span>|<span data-ttu-id="2c25e-121">Задает параметры для проверки сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="2c25e-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="2c25e-122">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="2c25e-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="2c25e-123">dns</span><span class="sxs-lookup"><span data-stu-id="2c25e-123">dns</span></span>|<span data-ttu-id="2c25e-124">Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="2c25e-125">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="2c25e-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="2c25e-126">rsa</span><span class="sxs-lookup"><span data-stu-id="2c25e-126">rsa</span></span>|<span data-ttu-id="2c25e-127">Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="2c25e-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="2c25e-128">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="2c25e-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="2c25e-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2c25e-129">servicePrincipalName</span></span>|<span data-ttu-id="2c25e-130">Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="2c25e-131">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="2c25e-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2c25e-132">Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2c25e-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="2c25e-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2c25e-133">userPrincipalName</span></span>|<span data-ttu-id="2c25e-134">Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть.</span><span class="sxs-lookup"><span data-stu-id="2c25e-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="2c25e-135">Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ (\@) и, как правило, родительский домен системы доменных имен.</span><span class="sxs-lookup"><span data-stu-id="2c25e-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="2c25e-136">Например, Джефф в дереве доменов Fabrikam.com может иметь имя [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c25e-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="2c25e-137">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="2c25e-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2c25e-138">Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="2c25e-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c25e-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c25e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="2c25e-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c25e-140">Element</span></span>|<span data-ttu-id="2c25e-141">Описание</span><span class="sxs-lookup"><span data-stu-id="2c25e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c25e-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="2c25e-142">\<custom></span></span>](custom.md)|<span data-ttu-id="2c25e-143">Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="2c25e-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="2c25e-144">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="2c25e-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="2c25e-145">Настраивает конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="2c25e-146">\<Конечная точка \<> клиента ></span><span class="sxs-lookup"><span data-stu-id="2c25e-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="2c25e-147">Настраивает конечные точки канала.</span><span class="sxs-lookup"><span data-stu-id="2c25e-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="2c25e-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2c25e-148">\<issuer></span></span>](issuer.md)|<span data-ttu-id="2c25e-149">Задает службу маркеров безопасности для федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="2c25e-150">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="2c25e-150">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="2c25e-151">Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="2c25e-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="2c25e-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2c25e-152">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="2c25e-153">Задает параметры для выданного маркера в настраиваемой привязке.</span><span class="sxs-lookup"><span data-stu-id="2c25e-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="2c25e-154">\<Локалиссуер ></span><span class="sxs-lookup"><span data-stu-id="2c25e-154">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="2c25e-155">Задает локальную службу маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="2c25e-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c25e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="2c25e-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="2c25e-157">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="2c25e-157">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2c25e-158">Конеч Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="2c25e-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
