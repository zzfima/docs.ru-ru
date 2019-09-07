---
title: <add> из <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400623"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="265fb-102">\<Добавление > \<> кновнцертификатес</span><span class="sxs-lookup"><span data-stu-id="265fb-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="265fb-103">Добавляет сертификат X.509 в коллекцию известных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="265fb-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="265fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="265fb-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="265fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="265fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="265fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="265fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="265fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Иссуедтокенаусентикатион >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="265fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кновнцертификатес >** ](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="265fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="265fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265fb-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="265fb-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="265fb-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="265fb-114">Attributes and Elements</span></span>  
 <span data-ttu-id="265fb-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="265fb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="265fb-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="265fb-116">Attributes</span></span>  
  
|<span data-ttu-id="265fb-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="265fb-117">Attribute</span></span>|<span data-ttu-id="265fb-118">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="265fb-119">findValue</span><span class="sxs-lookup"><span data-stu-id="265fb-119">findValue</span></span>|<span data-ttu-id="265fb-120">Строка.</span><span class="sxs-lookup"><span data-stu-id="265fb-120">String.</span></span> <span data-ttu-id="265fb-121">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="265fb-121">The value to search for.</span></span>|  
|<span data-ttu-id="265fb-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="265fb-122">storeLocation</span></span>|<span data-ttu-id="265fb-123">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="265fb-123">Enumeration.</span></span> <span data-ttu-id="265fb-124">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="265fb-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="265fb-125">storeName</span><span class="sxs-lookup"><span data-stu-id="265fb-125">storeName</span></span>|<span data-ttu-id="265fb-126">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="265fb-126">Enumeration.</span></span> <span data-ttu-id="265fb-127">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="265fb-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="265fb-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="265fb-128">x509FindType</span></span>|<span data-ttu-id="265fb-129">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="265fb-129">Enumeration.</span></span> <span data-ttu-id="265fb-130">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="265fb-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="265fb-131">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="265fb-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="265fb-132">Значение</span><span class="sxs-lookup"><span data-stu-id="265fb-132">Value</span></span>|<span data-ttu-id="265fb-133">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265fb-134">String</span><span class="sxs-lookup"><span data-stu-id="265fb-134">String</span></span>|<span data-ttu-id="265fb-135">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="265fb-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="265fb-136">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="265fb-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="265fb-137">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="265fb-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="265fb-138">Значение</span><span class="sxs-lookup"><span data-stu-id="265fb-138">Value</span></span>|<span data-ttu-id="265fb-139">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265fb-140">Перечисление</span><span class="sxs-lookup"><span data-stu-id="265fb-140">Enumeration</span></span>|<span data-ttu-id="265fb-141">К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="265fb-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="265fb-142">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="265fb-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="265fb-143">Значение</span><span class="sxs-lookup"><span data-stu-id="265fb-143">Value</span></span>|<span data-ttu-id="265fb-144">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265fb-145">Перечисление</span><span class="sxs-lookup"><span data-stu-id="265fb-145">Enumeration</span></span>|<span data-ttu-id="265fb-146">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="265fb-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="265fb-147">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="265fb-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="265fb-148">Значение</span><span class="sxs-lookup"><span data-stu-id="265fb-148">Value</span></span>|<span data-ttu-id="265fb-149">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265fb-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="265fb-150">Enumeration</span></span>|<span data-ttu-id="265fb-151">К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.</span><span class="sxs-lookup"><span data-stu-id="265fb-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="265fb-152">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="265fb-152">Child Elements</span></span>  
 <span data-ttu-id="265fb-153">Нет.</span><span class="sxs-lookup"><span data-stu-id="265fb-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="265fb-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="265fb-154">Parent Elements</span></span>  
  
|<span data-ttu-id="265fb-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="265fb-155">Element</span></span>|<span data-ttu-id="265fb-156">Описание</span><span class="sxs-lookup"><span data-stu-id="265fb-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="265fb-157">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="265fb-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="265fb-158">Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="265fb-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="265fb-159">Примечания</span><span class="sxs-lookup"><span data-stu-id="265fb-159">Remarks</span></span>  
 <span data-ttu-id="265fb-160">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="265fb-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="265fb-161">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="265fb-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="265fb-162">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="265fb-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="265fb-163">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="265fb-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="265fb-164">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="265fb-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="265fb-165">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="265fb-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="265fb-166">Элемент [иссуедтокенаусентикатион > — это репозиторий для любых таких сертификатов службы безопасных маркеров. \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="265fb-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="265fb-167">Чтобы добавить сертификаты, используйте [ \<> кновнцертификатес](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="265fb-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="265fb-168">Вставьте элемент [ \<Add > кновнцертификатес>длякаждогосертификата,какпоказано\<](add-of-knowncertificates.md) в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="265fb-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="265fb-169">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="265fb-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="265fb-170">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="265fb-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="265fb-171">Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации.</span><span class="sxs-lookup"><span data-stu-id="265fb-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="265fb-172">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="265fb-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="265fb-173">Пример</span><span class="sxs-lookup"><span data-stu-id="265fb-173">Example</span></span>  
 <span data-ttu-id="265fb-174">В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.</span><span class="sxs-lookup"><span data-stu-id="265fb-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="265fb-175">См. также</span><span class="sxs-lookup"><span data-stu-id="265fb-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="265fb-176">\<Кновнцертификатес ></span><span class="sxs-lookup"><span data-stu-id="265fb-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="265fb-177">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="265fb-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="265fb-178">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="265fb-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="265fb-179">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="265fb-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="265fb-180">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="265fb-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
