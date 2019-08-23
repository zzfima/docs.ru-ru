---
title: <add> из <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 939718e8dacca2698b6f71a3bdc1262a5dc3ee20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926682"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="99418-102">\<Добавление > \<> кновнцертификатес</span><span class="sxs-lookup"><span data-stu-id="99418-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="99418-103">Добавляет сертификат X.509 в коллекцию известных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="99418-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="99418-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="99418-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99418-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="99418-105">\<behaviors></span></span>  
<span data-ttu-id="99418-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="99418-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="99418-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="99418-107">\<behavior></span></span>  
<span data-ttu-id="99418-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="99418-108">\<serviceCredentials></span></span>  
<span data-ttu-id="99418-109">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="99418-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="99418-110">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="99418-110">\<knownCertificates></span></span>  
<span data-ttu-id="99418-111">\<add></span><span class="sxs-lookup"><span data-stu-id="99418-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99418-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99418-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99418-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="99418-113">Attributes and Elements</span></span>  
 <span data-ttu-id="99418-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="99418-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99418-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="99418-115">Attributes</span></span>  
  
|<span data-ttu-id="99418-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="99418-116">Attribute</span></span>|<span data-ttu-id="99418-117">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99418-118">findValue</span><span class="sxs-lookup"><span data-stu-id="99418-118">findValue</span></span>|<span data-ttu-id="99418-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="99418-119">String.</span></span> <span data-ttu-id="99418-120">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="99418-120">The value to search for.</span></span>|  
|<span data-ttu-id="99418-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="99418-121">storeLocation</span></span>|<span data-ttu-id="99418-122">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="99418-122">Enumeration.</span></span> <span data-ttu-id="99418-123">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="99418-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="99418-124">storeName</span><span class="sxs-lookup"><span data-stu-id="99418-124">storeName</span></span>|<span data-ttu-id="99418-125">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="99418-125">Enumeration.</span></span> <span data-ttu-id="99418-126">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="99418-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="99418-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="99418-127">x509FindType</span></span>|<span data-ttu-id="99418-128">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="99418-128">Enumeration.</span></span> <span data-ttu-id="99418-129">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="99418-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="99418-130">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="99418-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="99418-131">Значение</span><span class="sxs-lookup"><span data-stu-id="99418-131">Value</span></span>|<span data-ttu-id="99418-132">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99418-133">String</span><span class="sxs-lookup"><span data-stu-id="99418-133">String</span></span>|<span data-ttu-id="99418-134">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="99418-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="99418-135">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="99418-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="99418-136">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="99418-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="99418-137">Значение</span><span class="sxs-lookup"><span data-stu-id="99418-137">Value</span></span>|<span data-ttu-id="99418-138">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99418-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="99418-139">Enumeration</span></span>|<span data-ttu-id="99418-140">К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="99418-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="99418-141">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="99418-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="99418-142">Значение</span><span class="sxs-lookup"><span data-stu-id="99418-142">Value</span></span>|<span data-ttu-id="99418-143">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99418-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="99418-144">Enumeration</span></span>|<span data-ttu-id="99418-145">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="99418-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="99418-146">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="99418-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="99418-147">Значение</span><span class="sxs-lookup"><span data-stu-id="99418-147">Value</span></span>|<span data-ttu-id="99418-148">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99418-149">Перечисление</span><span class="sxs-lookup"><span data-stu-id="99418-149">Enumeration</span></span>|<span data-ttu-id="99418-150">К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.</span><span class="sxs-lookup"><span data-stu-id="99418-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99418-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="99418-151">Child Elements</span></span>  
 <span data-ttu-id="99418-152">Нет.</span><span class="sxs-lookup"><span data-stu-id="99418-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99418-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="99418-153">Parent Elements</span></span>  
  
|<span data-ttu-id="99418-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="99418-154">Element</span></span>|<span data-ttu-id="99418-155">Описание</span><span class="sxs-lookup"><span data-stu-id="99418-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99418-156">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="99418-156">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="99418-157">Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="99418-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99418-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="99418-158">Remarks</span></span>  
 <span data-ttu-id="99418-159">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="99418-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="99418-160">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="99418-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="99418-161">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="99418-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="99418-162">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="99418-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="99418-163">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="99418-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="99418-164">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="99418-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="99418-165">Элемент [иссуедтокенаусентикатион > — это репозиторий для любых таких сертификатов службы безопасных маркеров. \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="99418-165">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="99418-166">Чтобы добавить сертификаты, используйте [ \<> кновнцертификатес](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="99418-166">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="99418-167">Вставьте элемент [ \<Add > кновнцертификатес>длякаждогосертификата,какпоказано\<](add-of-knowncertificates.md) в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="99418-167">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="99418-168">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="99418-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="99418-169">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="99418-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="99418-170">Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="99418-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="99418-171">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="99418-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99418-172">Пример</span><span class="sxs-lookup"><span data-stu-id="99418-172">Example</span></span>  
 <span data-ttu-id="99418-173">В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.</span><span class="sxs-lookup"><span data-stu-id="99418-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="99418-174">См. также</span><span class="sxs-lookup"><span data-stu-id="99418-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="99418-175">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="99418-175">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="99418-176">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="99418-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="99418-177">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="99418-177">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="99418-178">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="99418-178">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="99418-179">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="99418-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
