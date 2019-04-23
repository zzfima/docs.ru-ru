---
title: Элемент <defaultCertificate>
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: c94531d10b7c0ef5ca0ee1f2d5683d0a259a2537
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100604"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="59512-102">\<defaultCertificate > элемент</span><span class="sxs-lookup"><span data-stu-id="59512-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="59512-103">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="59512-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="59512-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59512-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59512-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="59512-105">\<behaviors></span></span>  
<span data-ttu-id="59512-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="59512-106">endpointBehaviors section</span></span>  
<span data-ttu-id="59512-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="59512-107">\<behavior></span></span>  
<span data-ttu-id="59512-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="59512-108">\<clientCredentials></span></span>  
<span data-ttu-id="59512-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="59512-109">\<serviceCertificate></span></span>  
<span data-ttu-id="59512-110">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="59512-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59512-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59512-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59512-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59512-112">Attributes and Elements</span></span>  
 <span data-ttu-id="59512-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59512-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59512-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59512-114">Attributes</span></span>  
  
|<span data-ttu-id="59512-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59512-115">Attribute</span></span>|<span data-ttu-id="59512-116">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59512-117">findValue</span><span class="sxs-lookup"><span data-stu-id="59512-117">findValue</span></span>|<span data-ttu-id="59512-118">Строка.</span><span class="sxs-lookup"><span data-stu-id="59512-118">String.</span></span> <span data-ttu-id="59512-119">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="59512-119">The value to search for.</span></span>|  
|<span data-ttu-id="59512-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="59512-120">x509FindType</span></span>|<span data-ttu-id="59512-121">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="59512-121">Enumeration.</span></span> <span data-ttu-id="59512-122">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="59512-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="59512-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="59512-123">storeLocation</span></span>|<span data-ttu-id="59512-124">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="59512-124">Enumeration.</span></span> <span data-ttu-id="59512-125">Одно из двух системных расположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="59512-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="59512-126">storeName</span><span class="sxs-lookup"><span data-stu-id="59512-126">storeName</span></span>|<span data-ttu-id="59512-127">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="59512-127">Enumeration.</span></span> <span data-ttu-id="59512-128">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="59512-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="59512-129">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="59512-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="59512-130">Значение</span><span class="sxs-lookup"><span data-stu-id="59512-130">Value</span></span>|<span data-ttu-id="59512-131">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59512-132">String</span><span class="sxs-lookup"><span data-stu-id="59512-132">String</span></span>|<span data-ttu-id="59512-133">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="59512-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="59512-134">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="59512-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="59512-135">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="59512-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="59512-136">Значение</span><span class="sxs-lookup"><span data-stu-id="59512-136">Value</span></span>|<span data-ttu-id="59512-137">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59512-138">Перечисление</span><span class="sxs-lookup"><span data-stu-id="59512-138">Enumeration</span></span>|<span data-ttu-id="59512-139">К этим значениям относятся следующие. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="59512-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="59512-140">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="59512-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="59512-141">Значение</span><span class="sxs-lookup"><span data-stu-id="59512-141">Value</span></span>|<span data-ttu-id="59512-142">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59512-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="59512-143">Enumeration</span></span>|<span data-ttu-id="59512-144">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="59512-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="59512-145">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="59512-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="59512-146">Значение</span><span class="sxs-lookup"><span data-stu-id="59512-146">Value</span></span>|<span data-ttu-id="59512-147">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59512-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="59512-148">Enumeration</span></span>|<span data-ttu-id="59512-149">К этим значениям относятся следующие. AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="59512-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59512-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59512-150">Child Elements</span></span>  
 <span data-ttu-id="59512-151">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="59512-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59512-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59512-152">Parent Elements</span></span>  
  
|<span data-ttu-id="59512-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="59512-153">Element</span></span>|<span data-ttu-id="59512-154">Описание</span><span class="sxs-lookup"><span data-stu-id="59512-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59512-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="59512-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="59512-156">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="59512-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59512-157">Примечания</span><span class="sxs-lookup"><span data-stu-id="59512-157">Remarks</span></span>  
 <span data-ttu-id="59512-158">Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="59512-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="59512-159">Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.</span><span class="sxs-lookup"><span data-stu-id="59512-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59512-160">Пример</span><span class="sxs-lookup"><span data-stu-id="59512-160">Example</span></span>  
 <span data-ttu-id="59512-161">В следующем примере задается сертификат, используемый для конечных точек, чей URI начинается с `http://www.contoso.com` и сертификат, используемый для всех конечных точек, не выполняющих согласование сертификатов.</span><span class="sxs-lookup"><span data-stu-id="59512-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="59512-162">См. также</span><span class="sxs-lookup"><span data-stu-id="59512-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="59512-163">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="59512-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="59512-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="59512-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="59512-165">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="59512-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="59512-166">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="59512-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
