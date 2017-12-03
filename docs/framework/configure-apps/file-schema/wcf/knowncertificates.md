---
title: '&lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f62a43f1f8d3d025f62efca341c35e4af590abd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="1c358-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="1c358-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="1c358-103">Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="1c358-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="1c358-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1c358-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c358-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="1c358-105">\<behaviors></span></span>  
<span data-ttu-id="1c358-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1c358-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1c358-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1c358-107">\<behavior></span></span>  
<span data-ttu-id="1c358-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1c358-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1c358-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1c358-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="1c358-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="1c358-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c358-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c358-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c358-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c358-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c358-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1c358-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c358-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c358-114">Attributes</span></span>  
 <span data-ttu-id="1c358-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c358-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c358-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c358-116">Child Elements</span></span>  
  
|<span data-ttu-id="1c358-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c358-117">Element</span></span>|<span data-ttu-id="1c358-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1c358-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c358-119">\<add></span><span class="sxs-lookup"><span data-stu-id="1c358-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="1c358-120">Добавляет сертификат X.509 в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="1c358-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c358-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c358-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1c358-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c358-122">Element</span></span>|<span data-ttu-id="1c358-123">Описание</span><span class="sxs-lookup"><span data-stu-id="1c358-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c358-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1c358-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="1c358-125">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="1c358-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c358-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c358-126">Remarks</span></span>  
 <span data-ttu-id="1c358-127">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="1c358-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="1c358-128">На первом этапе клиент, который пытается получить доступ к службе называется *службы маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="1c358-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="1c358-129">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="1c358-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="1c358-130">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="1c358-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="1c358-131">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="1c358-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="1c358-132">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="1c358-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="1c358-133">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент является хранилищем для всех таких сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c358-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="1c358-134">Чтобы добавить сертификаты, используйте [ \<knownCertificates > элемент](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1c358-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="1c358-135">Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1c358-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="1c358-136">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c358-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="1c358-137">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="1c358-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="1c358-138">Просмотреть условия, необходимые клиенту проходить проверку подлинности в федеративной службе, а также дополнительные сведения об использовании данного элемента конфигурации в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1c358-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="1c358-139">Дополнительные сведения о федеративных сценариев см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="1c358-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="1c358-140">Пример, демонстрирующий способы заполнения коллекции в конфигурации см. в разделе [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="1c358-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c358-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1c358-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="1c358-142">\<add></span><span class="sxs-lookup"><span data-stu-id="1c358-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1c358-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1c358-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="1c358-144">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="1c358-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="1c358-145">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="1c358-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="1c358-146">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="1c358-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1c358-147">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="1c358-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1c358-148">\<add></span><span class="sxs-lookup"><span data-stu-id="1c358-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="1c358-149">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1c358-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
