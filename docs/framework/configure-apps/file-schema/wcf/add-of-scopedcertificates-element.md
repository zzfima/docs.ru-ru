---
title: <add> элемента <scopedCertificates>
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398345"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="f2b3d-102">\<Добавление > \<элемента > скопедцертификатес</span><span class="sxs-lookup"><span data-stu-id="f2b3d-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="f2b3d-103">Добавляет сертификат X.509 в коллекцию сертификатов в области действия.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="f2b3d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2b3d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f2b3d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f2b3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f2b3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f2b3d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="f2b3d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="f2b3d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Скопедцертификатес >** ](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2b3d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="f2b3d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="f2b3d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b3d-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2b3d-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2b3d-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f2b3d-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f2b3d-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2b3d-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2b3d-116">Attributes</span></span>  
  
|<span data-ttu-id="f2b3d-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f2b3d-117">Attribute</span></span>|<span data-ttu-id="f2b3d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2b3d-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="f2b3d-119">targetUri</span></span>|<span data-ttu-id="f2b3d-120">Строка.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-120">String.</span></span> <span data-ttu-id="f2b3d-121">Задает универсальный код ресурса (URI) службы, связанной с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="f2b3d-122">findValue</span><span class="sxs-lookup"><span data-stu-id="f2b3d-122">findValue</span></span>|<span data-ttu-id="f2b3d-123">Строка.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-123">String.</span></span> <span data-ttu-id="f2b3d-124">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-124">The value to search for.</span></span>|  
|<span data-ttu-id="f2b3d-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f2b3d-125">x509FindType</span></span>|<span data-ttu-id="f2b3d-126">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-126">Enumeration.</span></span> <span data-ttu-id="f2b3d-127">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="f2b3d-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f2b3d-128">storeLocation</span></span>|<span data-ttu-id="f2b3d-129">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-129">Enumeration.</span></span> <span data-ttu-id="f2b3d-130">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="f2b3d-131">storeName</span><span class="sxs-lookup"><span data-stu-id="f2b3d-131">storeName</span></span>|<span data-ttu-id="f2b3d-132">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-132">Enumeration.</span></span> <span data-ttu-id="f2b3d-133">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="f2b3d-134">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="f2b3d-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="f2b3d-135">Значение</span><span class="sxs-lookup"><span data-stu-id="f2b3d-135">Value</span></span>|<span data-ttu-id="f2b3d-136">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2b3d-137">String</span><span class="sxs-lookup"><span data-stu-id="f2b3d-137">String</span></span>|<span data-ttu-id="f2b3d-138">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="f2b3d-139">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="f2b3d-140">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="f2b3d-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="f2b3d-141">Значение</span><span class="sxs-lookup"><span data-stu-id="f2b3d-141">Value</span></span>|<span data-ttu-id="f2b3d-142">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2b3d-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="f2b3d-143">Enumeration</span></span>|<span data-ttu-id="f2b3d-144">К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="f2b3d-145">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="f2b3d-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="f2b3d-146">Значение</span><span class="sxs-lookup"><span data-stu-id="f2b3d-146">Value</span></span>|<span data-ttu-id="f2b3d-147">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2b3d-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="f2b3d-148">Enumeration</span></span>|<span data-ttu-id="f2b3d-149">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="f2b3d-150">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="f2b3d-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="f2b3d-151">Значение</span><span class="sxs-lookup"><span data-stu-id="f2b3d-151">Value</span></span>|<span data-ttu-id="f2b3d-152">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2b3d-153">Перечисление</span><span class="sxs-lookup"><span data-stu-id="f2b3d-153">Enumeration</span></span>|<span data-ttu-id="f2b3d-154">К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2b3d-155">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2b3d-155">Child Elements</span></span>  
 <span data-ttu-id="f2b3d-156">Нет.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2b3d-157">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f2b3d-157">Parent Elements</span></span>  
  
|<span data-ttu-id="f2b3d-158">Элемент</span><span class="sxs-lookup"><span data-stu-id="f2b3d-158">Element</span></span>|<span data-ttu-id="f2b3d-159">Описание</span><span class="sxs-lookup"><span data-stu-id="f2b3d-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2b3d-160">\<Скопедцертификатес ></span><span class="sxs-lookup"><span data-stu-id="f2b3d-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="f2b3d-161">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2b3d-162">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2b3d-162">Remarks</span></span>  
 <span data-ttu-id="f2b3d-163">Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL-адреса службы, с которой он связывается.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="f2b3d-164">Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="f2b3d-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="f2b3d-165">Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="f2b3d-166">Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="f2b3d-167">Дополнительные сведения см. в разделе "сертификаты с заданной областью [" статьи как Создайте федеративный клиент](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="f2b3d-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b3d-168">Пример</span><span class="sxs-lookup"><span data-stu-id="f2b3d-168">Example</span></span>  
 <span data-ttu-id="f2b3d-169">В следующем примере к коллекции добавляется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="f2b3d-169">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2b3d-170">См. также</span><span class="sxs-lookup"><span data-stu-id="f2b3d-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="f2b3d-171">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="f2b3d-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f2b3d-172">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="f2b3d-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f2b3d-173">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="f2b3d-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f2b3d-174">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f2b3d-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
