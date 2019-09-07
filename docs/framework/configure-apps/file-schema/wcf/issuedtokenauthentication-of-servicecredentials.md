---
title: <issuedTokenAuthentication> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400361"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="b71be-102">\<иссуедтокенаусентикатион > \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b71be-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="b71be-103">Определяет пользовательский маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="b71be-103">Specifies a custom token issued as a service credential.</span></span>  
  
<span data-ttu-id="b71be-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b71be-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b71be-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b71be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="b71be-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="b71be-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="b71be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Иссуедтокенаусентикатион >**</span><span class="sxs-lookup"><span data-stu-id="b71be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b71be-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b71be-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b71be-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b71be-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b71be-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b71be-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b71be-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b71be-114">Attributes</span></span>  
  
|<span data-ttu-id="b71be-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b71be-115">Attribute</span></span>|<span data-ttu-id="b71be-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b71be-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="b71be-117">Возвращает набор целевых универсальных кодов ресурса (URI), для которых может быть предназначен маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым в экземпляре <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="b71be-117">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="b71be-118">Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="b71be-118">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="b71be-119">Логическое значение, которое указывает, допускаются ли недоверенные издатели сертификатов RSA.</span><span class="sxs-lookup"><span data-stu-id="b71be-119">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="b71be-120">Сертификаты подписываются центрами сертификации (ЦС) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b71be-120">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="b71be-121">Недоверенным издателем является ЦС, который не указан как надежный для подписания сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b71be-121">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="b71be-122">Возвращает значение, которое указывает, должно ли проверяться свойство <xref:System.IdentityModel.Tokens.SamlSecurityToken> маркера безопасности <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="b71be-122">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="b71be-123">Это значение имеет тип <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="b71be-123">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="b71be-124">Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="b71be-124">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="b71be-125">Устанавливает режим проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="b71be-125">Sets the certificate validation mode.</span></span> <span data-ttu-id="b71be-126">Одно из допустимых значений для <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="b71be-126">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="b71be-127">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="b71be-127">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="b71be-128">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="b71be-128">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="b71be-129">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="b71be-129">Optional string.</span></span> <span data-ttu-id="b71be-130">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="b71be-130">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="b71be-131">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="b71be-131">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="b71be-132">Задает режим отзыва, который указывает, проводится ли проверка списка отозванных сертификатов; этот режим также определяет способ проверки: с подключением к сети или автономно.</span><span class="sxs-lookup"><span data-stu-id="b71be-132">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="b71be-133">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="b71be-133">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="b71be-134">Необязательный строковый атрибут, который задает тип SamlSerializer, который используется для учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="b71be-134">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="b71be-135">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="b71be-135">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="b71be-136">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="b71be-136">Optional enumeration.</span></span> <span data-ttu-id="b71be-137">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="b71be-137">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b71be-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b71be-138">Child Elements</span></span>  
  
|<span data-ttu-id="b71be-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="b71be-139">Element</span></span>|<span data-ttu-id="b71be-140">Описание</span><span class="sxs-lookup"><span data-stu-id="b71be-140">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="b71be-141">Задает коллекцию элементов <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>, которая задает доверенных издателей для учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="b71be-141">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b71be-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b71be-142">Parent Elements</span></span>  
  
|<span data-ttu-id="b71be-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="b71be-143">Element</span></span>|<span data-ttu-id="b71be-144">Описание</span><span class="sxs-lookup"><span data-stu-id="b71be-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b71be-145">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b71be-145">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="b71be-146">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="b71be-146">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b71be-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="b71be-147">Remarks</span></span>  
 <span data-ttu-id="b71be-148">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="b71be-148">The issued token scenario has three stages.</span></span> <span data-ttu-id="b71be-149">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="b71be-149">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="b71be-150">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="b71be-150">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="b71be-151">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="b71be-151">The client then returns to the service with the token.</span></span> <span data-ttu-id="b71be-152">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="b71be-152">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="b71be-153">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="b71be-153">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="b71be-154">Этот элемент является хранилищем подобных сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="b71be-154">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="b71be-155">Чтобы добавить сертификаты, используйте [ \<> кновнцертификатес](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="b71be-155">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="b71be-156">Вставьте > добавления для каждого сертификата, как показано в следующем примере. [ \<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="b71be-156">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="b71be-157">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="b71be-157">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="b71be-158">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="b71be-158">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="b71be-159">Дополнительные сведения об использовании этого элемента конфигурации см. в [разделе как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="b71be-159">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71be-160">См. также</span><span class="sxs-lookup"><span data-stu-id="b71be-160">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="b71be-161">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b71be-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b71be-162">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="b71be-162">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
