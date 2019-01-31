---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 4c1dc15621138aa692f0a30d285f729c2bd670d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274122"
---
# <a name="knowncertificates"></a><span data-ttu-id="9abe4-101">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="9abe4-101">\<knownCertificates></span></span>
<span data-ttu-id="9abe4-102">Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="9abe4-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="9abe4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9abe4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9abe4-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="9abe4-104">\<behaviors></span></span>  
<span data-ttu-id="9abe4-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9abe4-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9abe4-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="9abe4-106">\<behavior></span></span>  
<span data-ttu-id="9abe4-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9abe4-107">\<serviceCredentials></span></span>  
<span data-ttu-id="9abe4-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9abe4-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="9abe4-109">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="9abe4-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9abe4-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9abe4-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9abe4-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9abe4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9abe4-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9abe4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9abe4-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9abe4-113">Attributes</span></span>  
 <span data-ttu-id="9abe4-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9abe4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9abe4-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9abe4-115">Child Elements</span></span>  
  
|<span data-ttu-id="9abe4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="9abe4-116">Element</span></span>|<span data-ttu-id="9abe4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9abe4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9abe4-118">\<add></span><span class="sxs-lookup"><span data-stu-id="9abe4-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="9abe4-119">Добавляет сертификат X.509 в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="9abe4-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9abe4-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9abe4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9abe4-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="9abe4-121">Element</span></span>|<span data-ttu-id="9abe4-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="9abe4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9abe4-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9abe4-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="9abe4-124">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="9abe4-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9abe4-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="9abe4-125">Remarks</span></span>  
 <span data-ttu-id="9abe4-126">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="9abe4-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="9abe4-127">На первом этапе клиент, пытающийся получить доступ к службе называется *служба маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="9abe4-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="9abe4-128">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="9abe4-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="9abe4-129">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="9abe4-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="9abe4-130">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="9abe4-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="9abe4-131">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="9abe4-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="9abe4-132">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент является хранилищем подобных сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="9abe4-132">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="9abe4-133">Чтобы добавить сертификаты, используйте [ \<knownCertificates > элемент](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="9abe4-133">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="9abe4-134">Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9abe4-134">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="9abe4-135">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="9abe4-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="9abe4-136">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="9abe4-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="9abe4-137">Необходимые условия для клиента не может проверить подлинность федеративной службы, а также дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="9abe4-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="9abe4-138">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="9abe4-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="9abe4-139">Пример, показывающий, как для заполнения коллекции в конфигурации, см. в разделе [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="9abe4-139">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abe4-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9abe4-140">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="9abe4-141">\<add></span><span class="sxs-lookup"><span data-stu-id="9abe4-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="9abe4-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9abe4-142">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="9abe4-143">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="9abe4-143">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9abe4-144">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="9abe4-144">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="9abe4-145">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="9abe4-145">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9abe4-146">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9abe4-146">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9abe4-147">\<add></span><span class="sxs-lookup"><span data-stu-id="9abe4-147">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="9abe4-148">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9abe4-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
