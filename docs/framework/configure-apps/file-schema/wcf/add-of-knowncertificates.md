---
title: "&lt;add&gt; для &lt;knownCertificates&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30b3216842b602745ad40d1743175350aba78296
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltknowncertificatesgt"></a><span data-ttu-id="d0e26-102">&lt;add&gt; для &lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="d0e26-102">&lt;add&gt; of &lt;knownCertificates&gt;</span></span>
<span data-ttu-id="d0e26-103">Добавляет сертификат X.509 в коллекцию известных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d0e26-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="d0e26-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d0e26-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0e26-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="d0e26-105">\<behaviors></span></span>  
<span data-ttu-id="d0e26-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d0e26-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d0e26-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d0e26-107">\<behavior></span></span>  
<span data-ttu-id="d0e26-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d0e26-108">\<serviceCredentials></span></span>  
<span data-ttu-id="d0e26-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d0e26-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="d0e26-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="d0e26-110">\<knownCertificates></span></span>  
<span data-ttu-id="d0e26-111">\<add></span><span class="sxs-lookup"><span data-stu-id="d0e26-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e26-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0e26-112">Syntax</span></span>  
  
```xml  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0e26-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0e26-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d0e26-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0e26-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0e26-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0e26-115">Attributes</span></span>  
  
|<span data-ttu-id="d0e26-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0e26-116">Attribute</span></span>|<span data-ttu-id="d0e26-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0e26-118">findValue</span><span class="sxs-lookup"><span data-stu-id="d0e26-118">findValue</span></span>|<span data-ttu-id="d0e26-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="d0e26-119">String.</span></span> <span data-ttu-id="d0e26-120">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="d0e26-120">The value to search for.</span></span>|  
|<span data-ttu-id="d0e26-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d0e26-121">storeLocation</span></span>|<span data-ttu-id="d0e26-122">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0e26-122">Enumeration.</span></span> <span data-ttu-id="d0e26-123">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0e26-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="d0e26-124">storeName</span><span class="sxs-lookup"><span data-stu-id="d0e26-124">storeName</span></span>|<span data-ttu-id="d0e26-125">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0e26-125">Enumeration.</span></span> <span data-ttu-id="d0e26-126">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0e26-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="d0e26-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d0e26-127">x509FindType</span></span>|<span data-ttu-id="d0e26-128">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0e26-128">Enumeration.</span></span> <span data-ttu-id="d0e26-129">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0e26-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d0e26-130">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="d0e26-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="d0e26-131">Значение</span><span class="sxs-lookup"><span data-stu-id="d0e26-131">Value</span></span>|<span data-ttu-id="d0e26-132">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e26-133">Строковое</span><span class="sxs-lookup"><span data-stu-id="d0e26-133">String</span></span>|<span data-ttu-id="d0e26-134">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="d0e26-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d0e26-135">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="d0e26-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d0e26-136">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="d0e26-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d0e26-137">Значение</span><span class="sxs-lookup"><span data-stu-id="d0e26-137">Value</span></span>|<span data-ttu-id="d0e26-138">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e26-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0e26-139">Enumeration</span></span>|<span data-ttu-id="d0e26-140">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="d0e26-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d0e26-141">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="d0e26-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d0e26-142">Значение</span><span class="sxs-lookup"><span data-stu-id="d0e26-142">Value</span></span>|<span data-ttu-id="d0e26-143">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e26-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0e26-144">Enumeration</span></span>|<span data-ttu-id="d0e26-145">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d0e26-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d0e26-146">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="d0e26-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="d0e26-147">Значение</span><span class="sxs-lookup"><span data-stu-id="d0e26-147">Value</span></span>|<span data-ttu-id="d0e26-148">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e26-149">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0e26-149">Enumeration</span></span>|<span data-ttu-id="d0e26-150">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="d0e26-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0e26-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0e26-151">Child Elements</span></span>  
 <span data-ttu-id="d0e26-152">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0e26-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0e26-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0e26-153">Parent Elements</span></span>  
  
|<span data-ttu-id="d0e26-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0e26-154">Element</span></span>|<span data-ttu-id="d0e26-155">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e26-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0e26-156">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="d0e26-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="d0e26-157">Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d0e26-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e26-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0e26-158">Remarks</span></span>  
 <span data-ttu-id="d0e26-159">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="d0e26-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="d0e26-160">На первом этапе клиент, который пытается получить доступ к службе называется *службы маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="d0e26-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="d0e26-161">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="d0e26-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="d0e26-162">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="d0e26-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="d0e26-163">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="d0e26-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="d0e26-164">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="d0e26-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="d0e26-165">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент является хранилищем для всех таких сертификатов службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d0e26-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="d0e26-166">Чтобы добавить сертификаты, используйте [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0e26-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="d0e26-167">Вставить [ \<Добавить > элемент \<knownCertificates > элемент](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d0e26-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="d0e26-168">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d0e26-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="d0e26-169">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="d0e26-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="d0e26-170">Просмотреть условия, необходимые клиенту проходить проверку подлинности в федеративной службе, а также дополнительные сведения об использовании данного элемента конфигурации в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="d0e26-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="d0e26-171">Дополнительные сведения о федеративных сценариев см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="d0e26-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e26-172">Пример</span><span class="sxs-lookup"><span data-stu-id="d0e26-172">Example</span></span>  
 <span data-ttu-id="d0e26-173">В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.</span><span class="sxs-lookup"><span data-stu-id="d0e26-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0e26-174">См. также</span><span class="sxs-lookup"><span data-stu-id="d0e26-174">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="d0e26-175">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="d0e26-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)  
 [<span data-ttu-id="d0e26-176">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="d0e26-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d0e26-177">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="d0e26-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="d0e26-178">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="d0e26-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="d0e26-179">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d0e26-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
