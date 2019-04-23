---
title: <issuedTokenAuthentication> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: d093b45269b230b4ff074d07a66290ab09592f60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178572"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="bc5a3-102">\<issuedTokenAuthentication > из \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="bc5a3-103">Определяет пользовательский маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="bc5a3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bc5a3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bc5a3-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-105">\<behaviors></span></span>  
<span data-ttu-id="bc5a3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bc5a3-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-107">\<behavior></span></span>  
<span data-ttu-id="bc5a3-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="bc5a3-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="bc5a3-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5a3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc5a3-110">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc5a3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bc5a3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bc5a3-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc5a3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc5a3-113">Attributes</span></span>  
  
|<span data-ttu-id="bc5a3-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc5a3-114">Attribute</span></span>|<span data-ttu-id="bc5a3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bc5a3-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="bc5a3-116">Возвращает набор целевых универсальных кодов ресурса (URI), для которых может быть предназначен маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым в экземпляре <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="bc5a3-117">Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="bc5a3-118">Логическое значение, которое указывает, допускаются ли недоверенные издатели сертификатов RSA.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="bc5a3-119">Сертификаты подписываются центрами сертификации (ЦС) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="bc5a3-120">Недоверенным издателем является ЦС, который не указан как надежный для подписания сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="bc5a3-121">Возвращает значение, которое указывает, должно ли проверяться свойство <xref:System.IdentityModel.Tokens.SamlSecurityToken> маркера безопасности <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="bc5a3-122">Это значение имеет тип <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="bc5a3-123">Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="bc5a3-124">Устанавливает режим проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="bc5a3-125">Одно из допустимых значений для <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="bc5a3-126">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="bc5a3-127">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="bc5a3-128">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-128">Optional string.</span></span> <span data-ttu-id="bc5a3-129">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="bc5a3-130">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="bc5a3-131">Задает режим отзыва, который указывает, проводится ли проверка списка отозванных сертификатов; этот режим также определяет способ проверки: с подключением к сети или автономно.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="bc5a3-132">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="bc5a3-133">Необязательный строковый атрибут, который задает тип SamlSerializer, который используется для учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="bc5a3-134">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="bc5a3-135">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-135">Optional enumeration.</span></span> <span data-ttu-id="bc5a3-136">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc5a3-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc5a3-137">Child Elements</span></span>  
  
|<span data-ttu-id="bc5a3-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc5a3-138">Element</span></span>|<span data-ttu-id="bc5a3-139">Описание</span><span class="sxs-lookup"><span data-stu-id="bc5a3-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="bc5a3-140">Задает коллекцию элементов <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>, которая задает доверенных издателей для учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc5a3-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc5a3-141">Parent Elements</span></span>  
  
|<span data-ttu-id="bc5a3-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc5a3-142">Element</span></span>|<span data-ttu-id="bc5a3-143">Описание</span><span class="sxs-lookup"><span data-stu-id="bc5a3-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc5a3-144">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bc5a3-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="bc5a3-145">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc5a3-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc5a3-146">Remarks</span></span>  
 <span data-ttu-id="bc5a3-147">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="bc5a3-148">На первом этапе клиент, пытающийся получить доступ к службе называется *служба маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="bc5a3-149">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="bc5a3-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="bc5a3-150">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="bc5a3-151">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="bc5a3-152">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="bc5a3-153">Этот элемент является хранилищем подобных сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="bc5a3-154">Чтобы добавить сертификаты, используйте [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="bc5a3-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="bc5a3-155">Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="bc5a3-156">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="bc5a3-157">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="bc5a3-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="bc5a3-158">Дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="bc5a3-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5a3-159">См. также</span><span class="sxs-lookup"><span data-stu-id="bc5a3-159">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="bc5a3-160">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="bc5a3-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="bc5a3-161">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="bc5a3-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
