---
title: '&lt;add&gt; элемента &lt;scopedCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 0eb2f116fc0a2c7d59b90cea71150c7b46ee39fa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltscopedcertificatesgt-element"></a><span data-ttu-id="7bab3-102">&lt;add&gt; элемента &lt;scopedCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="7bab3-102">&lt;add&gt; of &lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="7bab3-103">Добавляет сертификат X.509 в коллекцию сертификатов в области действия.</span><span class="sxs-lookup"><span data-stu-id="7bab3-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="7bab3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7bab3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7bab3-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="7bab3-105">\<behaviors></span></span>  
<span data-ttu-id="7bab3-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="7bab3-106">endpointBehaviors section</span></span>  
<span data-ttu-id="7bab3-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7bab3-107">\<behavior></span></span>  
<span data-ttu-id="7bab3-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="7bab3-108">\<clientCredentials></span></span>  
<span data-ttu-id="7bab3-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7bab3-109">\<serviceCertificate></span></span>  
<span data-ttu-id="7bab3-110">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="7bab3-110">\<scopedCertificates></span></span>  
<span data-ttu-id="7bab3-111">\<Добавить > элемент для \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="7bab3-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bab3-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bab3-112">Syntax</span></span>  
  
```xml  
<add findValue="String"  
          storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
          targetUri="string"  
         x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"   
/>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bab3-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7bab3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7bab3-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7bab3-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bab3-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7bab3-115">Attributes</span></span>  
  
|<span data-ttu-id="7bab3-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7bab3-116">Attribute</span></span>|<span data-ttu-id="7bab3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7bab3-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="7bab3-118">targetUri</span></span>|<span data-ttu-id="7bab3-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="7bab3-119">String.</span></span> <span data-ttu-id="7bab3-120">Задает универсальный код ресурса (URI) службы, связанной с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="7bab3-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="7bab3-121">findValue</span><span class="sxs-lookup"><span data-stu-id="7bab3-121">findValue</span></span>|<span data-ttu-id="7bab3-122">Строка.</span><span class="sxs-lookup"><span data-stu-id="7bab3-122">String.</span></span> <span data-ttu-id="7bab3-123">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="7bab3-123">The value to search for.</span></span>|  
|<span data-ttu-id="7bab3-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="7bab3-124">x509FindType</span></span>|<span data-ttu-id="7bab3-125">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="7bab3-125">Enumeration.</span></span> <span data-ttu-id="7bab3-126">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="7bab3-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="7bab3-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="7bab3-127">storeLocation</span></span>|<span data-ttu-id="7bab3-128">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="7bab3-128">Enumeration.</span></span> <span data-ttu-id="7bab3-129">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="7bab3-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="7bab3-130">storeName</span><span class="sxs-lookup"><span data-stu-id="7bab3-130">storeName</span></span>|<span data-ttu-id="7bab3-131">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="7bab3-131">Enumeration.</span></span> <span data-ttu-id="7bab3-132">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="7bab3-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="7bab3-133">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="7bab3-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="7bab3-134">Значение</span><span class="sxs-lookup"><span data-stu-id="7bab3-134">Value</span></span>|<span data-ttu-id="7bab3-135">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bab3-136">Строковое</span><span class="sxs-lookup"><span data-stu-id="7bab3-136">String</span></span>|<span data-ttu-id="7bab3-137">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="7bab3-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="7bab3-138">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="7bab3-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="7bab3-139">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="7bab3-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="7bab3-140">Значение</span><span class="sxs-lookup"><span data-stu-id="7bab3-140">Value</span></span>|<span data-ttu-id="7bab3-141">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bab3-142">Перечисление</span><span class="sxs-lookup"><span data-stu-id="7bab3-142">Enumeration</span></span>|<span data-ttu-id="7bab3-143">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="7bab3-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="7bab3-144">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="7bab3-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="7bab3-145">Значение</span><span class="sxs-lookup"><span data-stu-id="7bab3-145">Value</span></span>|<span data-ttu-id="7bab3-146">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bab3-147">Перечисление</span><span class="sxs-lookup"><span data-stu-id="7bab3-147">Enumeration</span></span>|<span data-ttu-id="7bab3-148">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="7bab3-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="7bab3-149">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="7bab3-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="7bab3-150">Значение</span><span class="sxs-lookup"><span data-stu-id="7bab3-150">Value</span></span>|<span data-ttu-id="7bab3-151">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bab3-152">Перечисление</span><span class="sxs-lookup"><span data-stu-id="7bab3-152">Enumeration</span></span>|<span data-ttu-id="7bab3-153">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="7bab3-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bab3-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7bab3-154">Child Elements</span></span>  
 <span data-ttu-id="7bab3-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7bab3-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bab3-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7bab3-156">Parent Elements</span></span>  
  
|<span data-ttu-id="7bab3-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bab3-157">Element</span></span>|<span data-ttu-id="7bab3-158">Описание</span><span class="sxs-lookup"><span data-stu-id="7bab3-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bab3-159">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="7bab3-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="7bab3-160">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7bab3-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bab3-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bab3-161">Remarks</span></span>  
 <span data-ttu-id="7bab3-162">Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL-адреса службы, с которой он связывается.</span><span class="sxs-lookup"><span data-stu-id="7bab3-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="7bab3-163">Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="7bab3-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="7bab3-164">Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="7bab3-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="7bab3-165">Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7bab3-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="7bab3-166">Дополнительные сведения см. раздел «Областью действия сертификатов» [как: создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="7bab3-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bab3-167">Пример</span><span class="sxs-lookup"><span data-stu-id="7bab3-167">Example</span></span>  
 <span data-ttu-id="7bab3-168">В следующем примере к коллекции добавляется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="7bab3-168">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <serviceCertificate>  
     <scopedCertificates>  
      <add targetUri="http://www.contoso.com"   
       findValue="www.Contoso.com"   
       storeLocation="LocalMachine"  
       storeName="Root"   
       x509FindType="FindByIssuerName" />  
     </scopedCertificates>  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bab3-169">См. также</span><span class="sxs-lookup"><span data-stu-id="7bab3-169">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="7bab3-170">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="7bab3-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="7bab3-171">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="7bab3-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="7bab3-172">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="7bab3-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="7bab3-173">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7bab3-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
