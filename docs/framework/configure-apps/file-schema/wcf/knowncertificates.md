---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400333"
---
# <a name="knowncertificates"></a><span data-ttu-id="69522-101">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="69522-101">\<knownCertificates></span></span>
<span data-ttu-id="69522-102">Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="69522-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="69522-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69522-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69522-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="69522-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="69522-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="69522-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="69522-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="69522-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="69522-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="69522-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="69522-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="69522-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="69522-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Иссуедтокенаусентикатион >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="69522-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="69522-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кновнцертификатес >**</span><span class="sxs-lookup"><span data-stu-id="69522-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69522-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69522-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69522-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69522-112">Attributes and Elements</span></span>  
 <span data-ttu-id="69522-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69522-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69522-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69522-114">Attributes</span></span>  
 <span data-ttu-id="69522-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="69522-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69522-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69522-116">Child Elements</span></span>  
  
|<span data-ttu-id="69522-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="69522-117">Element</span></span>|<span data-ttu-id="69522-118">Описание</span><span class="sxs-lookup"><span data-stu-id="69522-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69522-119">\<add></span><span class="sxs-lookup"><span data-stu-id="69522-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="69522-120">Добавляет сертификат X.509 в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="69522-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69522-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69522-121">Parent Elements</span></span>  
  
|<span data-ttu-id="69522-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="69522-122">Element</span></span>|<span data-ttu-id="69522-123">Описание</span><span class="sxs-lookup"><span data-stu-id="69522-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69522-124">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="69522-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="69522-125">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="69522-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69522-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="69522-126">Remarks</span></span>  
 <span data-ttu-id="69522-127">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="69522-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="69522-128">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="69522-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="69522-129">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="69522-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="69522-130">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="69522-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="69522-131">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="69522-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="69522-132">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="69522-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="69522-133">Элемент [иссуедтокенаусентикатион > — это репозиторий для любых таких сертификатов службы безопасных маркеров. \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="69522-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="69522-134">Чтобы добавить сертификаты, используйте [ \<элемент кновнцертификатес >](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="69522-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="69522-135">Вставьте > добавления для каждого сертификата, как показано в следующем примере. [ \<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="69522-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="69522-136">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="69522-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="69522-137">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="69522-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="69522-138">Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="69522-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="69522-139">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="69522-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="69522-140">Пример, демонстрирующий заполнение коллекции в конфигурации, см. в разделе [ \<Add >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="69522-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69522-141">См. также</span><span class="sxs-lookup"><span data-stu-id="69522-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="69522-142">\<add></span><span class="sxs-lookup"><span data-stu-id="69522-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="69522-143">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="69522-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="69522-144">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="69522-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="69522-145">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="69522-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="69522-146">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="69522-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="69522-147">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="69522-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="69522-148">\<add></span><span class="sxs-lookup"><span data-stu-id="69522-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="69522-149">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="69522-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
