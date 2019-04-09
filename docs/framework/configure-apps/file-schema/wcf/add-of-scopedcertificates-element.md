---
title: <add> из <scopedCertificates> элемент
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 06a624d0146745581dfe907d044d1f7d3b857902
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119682"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="9469e-102">\<Добавить > из \<scopedCertificates > элемент</span><span class="sxs-lookup"><span data-stu-id="9469e-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="9469e-103">Добавляет сертификат X.509 в коллекцию сертификатов в области действия.</span><span class="sxs-lookup"><span data-stu-id="9469e-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="9469e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9469e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9469e-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="9469e-105">\<behaviors></span></span>  
<span data-ttu-id="9469e-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="9469e-106">endpointBehaviors section</span></span>  
<span data-ttu-id="9469e-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="9469e-107">\<behavior></span></span>  
<span data-ttu-id="9469e-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9469e-108">\<clientCredentials></span></span>  
<span data-ttu-id="9469e-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="9469e-109">\<serviceCertificate></span></span>  
<span data-ttu-id="9469e-110">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="9469e-110">\<scopedCertificates></span></span>  
<span data-ttu-id="9469e-111">\<Добавить > элемент для \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="9469e-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9469e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9469e-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9469e-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9469e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9469e-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9469e-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9469e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9469e-115">Attributes</span></span>  
  
|<span data-ttu-id="9469e-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9469e-116">Attribute</span></span>|<span data-ttu-id="9469e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9469e-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="9469e-118">targetUri</span></span>|<span data-ttu-id="9469e-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="9469e-119">String.</span></span> <span data-ttu-id="9469e-120">Задает универсальный код ресурса (URI) службы, связанной с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="9469e-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="9469e-121">findValue</span><span class="sxs-lookup"><span data-stu-id="9469e-121">findValue</span></span>|<span data-ttu-id="9469e-122">Строка.</span><span class="sxs-lookup"><span data-stu-id="9469e-122">String.</span></span> <span data-ttu-id="9469e-123">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="9469e-123">The value to search for.</span></span>|  
|<span data-ttu-id="9469e-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="9469e-124">x509FindType</span></span>|<span data-ttu-id="9469e-125">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="9469e-125">Enumeration.</span></span> <span data-ttu-id="9469e-126">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="9469e-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="9469e-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="9469e-127">storeLocation</span></span>|<span data-ttu-id="9469e-128">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="9469e-128">Enumeration.</span></span> <span data-ttu-id="9469e-129">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="9469e-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="9469e-130">storeName</span><span class="sxs-lookup"><span data-stu-id="9469e-130">storeName</span></span>|<span data-ttu-id="9469e-131">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="9469e-131">Enumeration.</span></span> <span data-ttu-id="9469e-132">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="9469e-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="9469e-133">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="9469e-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="9469e-134">Значение</span><span class="sxs-lookup"><span data-stu-id="9469e-134">Value</span></span>|<span data-ttu-id="9469e-135">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9469e-136">String</span><span class="sxs-lookup"><span data-stu-id="9469e-136">String</span></span>|<span data-ttu-id="9469e-137">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="9469e-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="9469e-138">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="9469e-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="9469e-139">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="9469e-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="9469e-140">Значение</span><span class="sxs-lookup"><span data-stu-id="9469e-140">Value</span></span>|<span data-ttu-id="9469e-141">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9469e-142">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9469e-142">Enumeration</span></span>|<span data-ttu-id="9469e-143">К этим значениям относятся следующие. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="9469e-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="9469e-144">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="9469e-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="9469e-145">Значение</span><span class="sxs-lookup"><span data-stu-id="9469e-145">Value</span></span>|<span data-ttu-id="9469e-146">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9469e-147">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9469e-147">Enumeration</span></span>|<span data-ttu-id="9469e-148">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="9469e-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="9469e-149">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="9469e-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="9469e-150">Значение</span><span class="sxs-lookup"><span data-stu-id="9469e-150">Value</span></span>|<span data-ttu-id="9469e-151">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9469e-152">Перечисление</span><span class="sxs-lookup"><span data-stu-id="9469e-152">Enumeration</span></span>|<span data-ttu-id="9469e-153">К этим значениям относятся следующие. AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="9469e-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9469e-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9469e-154">Child Elements</span></span>  
 <span data-ttu-id="9469e-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9469e-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9469e-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9469e-156">Parent Elements</span></span>  
  
|<span data-ttu-id="9469e-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="9469e-157">Element</span></span>|<span data-ttu-id="9469e-158">Описание</span><span class="sxs-lookup"><span data-stu-id="9469e-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9469e-159">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="9469e-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="9469e-160">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9469e-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9469e-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="9469e-161">Remarks</span></span>  
 <span data-ttu-id="9469e-162">Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL-адреса службы, с которой он связывается.</span><span class="sxs-lookup"><span data-stu-id="9469e-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="9469e-163">Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="9469e-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="9469e-164">Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="9469e-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="9469e-165">Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9469e-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="9469e-166">Дополнительные сведения см. в разделе «Сертификаты в области действия» [как: Создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="9469e-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9469e-167">Пример</span><span class="sxs-lookup"><span data-stu-id="9469e-167">Example</span></span>  
 <span data-ttu-id="9469e-168">В следующем примере к коллекции добавляется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="9469e-168">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9469e-169">См. также</span><span class="sxs-lookup"><span data-stu-id="9469e-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="9469e-170">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="9469e-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9469e-171">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="9469e-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9469e-172">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="9469e-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="9469e-173">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9469e-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
