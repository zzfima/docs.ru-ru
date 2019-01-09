---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: ed2bd5ec5b3a2a3e7b929b954df1c00be0849d71
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149763"
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="5841a-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="5841a-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="5841a-103">Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="5841a-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="5841a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5841a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5841a-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5841a-105">\<behaviors></span></span>  
<span data-ttu-id="5841a-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5841a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5841a-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5841a-107">\<behavior></span></span>  
<span data-ttu-id="5841a-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5841a-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5841a-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5841a-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="5841a-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="5841a-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5841a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5841a-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5841a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5841a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5841a-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5841a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5841a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5841a-114">Attributes</span></span>  
 <span data-ttu-id="5841a-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5841a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5841a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5841a-116">Child Elements</span></span>  
  
|<span data-ttu-id="5841a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5841a-117">Element</span></span>|<span data-ttu-id="5841a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5841a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5841a-119">\<add></span><span class="sxs-lookup"><span data-stu-id="5841a-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="5841a-120">Добавляет сертификат X.509 в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5841a-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5841a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5841a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5841a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="5841a-122">Element</span></span>|<span data-ttu-id="5841a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5841a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5841a-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5841a-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="5841a-125">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="5841a-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5841a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5841a-126">Remarks</span></span>  
 <span data-ttu-id="5841a-127">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="5841a-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="5841a-128">На первом этапе клиент, пытающийся получить доступ к службе называется *служба маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="5841a-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5841a-129">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="5841a-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5841a-130">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="5841a-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="5841a-131">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="5841a-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5841a-132">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="5841a-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5841a-133">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент является хранилищем подобных сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5841a-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5841a-134">Чтобы добавить сертификаты, используйте [ \<knownCertificates > элемент](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5841a-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="5841a-135">Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5841a-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5841a-136">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5841a-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5841a-137">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="5841a-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5841a-138">Необходимые условия для клиента не может проверить подлинность федеративной службы, а также дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="5841a-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5841a-139">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="5841a-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="5841a-140">Пример, показывающий, как для заполнения коллекции в конфигурации, см. в разделе [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5841a-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5841a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5841a-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="5841a-142">\<add></span><span class="sxs-lookup"><span data-stu-id="5841a-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="5841a-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5841a-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="5841a-144">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="5841a-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="5841a-145">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="5841a-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="5841a-146">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="5841a-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="5841a-147">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="5841a-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="5841a-148">\<add></span><span class="sxs-lookup"><span data-stu-id="5841a-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="5841a-149">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5841a-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
