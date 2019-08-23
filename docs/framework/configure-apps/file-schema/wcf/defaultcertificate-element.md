---
title: Элемент <defaultCertificate>
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919250"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="d0d25-102">\<Элемент > Дефаултцертификате</span><span class="sxs-lookup"><span data-stu-id="d0d25-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="d0d25-103">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="d0d25-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="d0d25-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d0d25-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0d25-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d0d25-105">\<behaviors></span></span>  
<span data-ttu-id="d0d25-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="d0d25-106">endpointBehaviors section</span></span>  
<span data-ttu-id="d0d25-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d0d25-107">\<behavior></span></span>  
<span data-ttu-id="d0d25-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="d0d25-108">\<clientCredentials></span></span>  
<span data-ttu-id="d0d25-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d0d25-109">\<serviceCertificate></span></span>  
<span data-ttu-id="d0d25-110">\<Дефаултцертификате ></span><span class="sxs-lookup"><span data-stu-id="d0d25-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d25-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0d25-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0d25-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0d25-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d0d25-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0d25-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0d25-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0d25-114">Attributes</span></span>  
  
|<span data-ttu-id="d0d25-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0d25-115">Attribute</span></span>|<span data-ttu-id="d0d25-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0d25-117">findValue</span><span class="sxs-lookup"><span data-stu-id="d0d25-117">findValue</span></span>|<span data-ttu-id="d0d25-118">Строка.</span><span class="sxs-lookup"><span data-stu-id="d0d25-118">String.</span></span> <span data-ttu-id="d0d25-119">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="d0d25-119">The value to search for.</span></span>|  
|<span data-ttu-id="d0d25-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d0d25-120">x509FindType</span></span>|<span data-ttu-id="d0d25-121">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0d25-121">Enumeration.</span></span> <span data-ttu-id="d0d25-122">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0d25-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="d0d25-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d0d25-123">storeLocation</span></span>|<span data-ttu-id="d0d25-124">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0d25-124">Enumeration.</span></span> <span data-ttu-id="d0d25-125">Одно из двух системных расположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0d25-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="d0d25-126">storeName</span><span class="sxs-lookup"><span data-stu-id="d0d25-126">storeName</span></span>|<span data-ttu-id="d0d25-127">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d0d25-127">Enumeration.</span></span> <span data-ttu-id="d0d25-128">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d0d25-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d0d25-129">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="d0d25-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="d0d25-130">Значение</span><span class="sxs-lookup"><span data-stu-id="d0d25-130">Value</span></span>|<span data-ttu-id="d0d25-131">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0d25-132">String</span><span class="sxs-lookup"><span data-stu-id="d0d25-132">String</span></span>|<span data-ttu-id="d0d25-133">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="d0d25-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d0d25-134">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="d0d25-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d0d25-135">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="d0d25-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d0d25-136">Значение</span><span class="sxs-lookup"><span data-stu-id="d0d25-136">Value</span></span>|<span data-ttu-id="d0d25-137">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0d25-138">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0d25-138">Enumeration</span></span>|<span data-ttu-id="d0d25-139">К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="d0d25-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d0d25-140">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="d0d25-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d0d25-141">Значение</span><span class="sxs-lookup"><span data-stu-id="d0d25-141">Value</span></span>|<span data-ttu-id="d0d25-142">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0d25-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0d25-143">Enumeration</span></span>|<span data-ttu-id="d0d25-144">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d0d25-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d0d25-145">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="d0d25-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="d0d25-146">Значение</span><span class="sxs-lookup"><span data-stu-id="d0d25-146">Value</span></span>|<span data-ttu-id="d0d25-147">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0d25-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d0d25-148">Enumeration</span></span>|<span data-ttu-id="d0d25-149">К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.</span><span class="sxs-lookup"><span data-stu-id="d0d25-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0d25-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0d25-150">Child Elements</span></span>  
 <span data-ttu-id="d0d25-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="d0d25-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0d25-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0d25-152">Parent Elements</span></span>  
  
|<span data-ttu-id="d0d25-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0d25-153">Element</span></span>|<span data-ttu-id="d0d25-154">Описание</span><span class="sxs-lookup"><span data-stu-id="d0d25-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0d25-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d0d25-155">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="d0d25-156">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="d0d25-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0d25-157">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0d25-157">Remarks</span></span>  
 <span data-ttu-id="d0d25-158">Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="d0d25-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="d0d25-159">Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.</span><span class="sxs-lookup"><span data-stu-id="d0d25-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0d25-160">Пример</span><span class="sxs-lookup"><span data-stu-id="d0d25-160">Example</span></span>  
 <span data-ttu-id="d0d25-161">В следующем примере указывается сертификат, который будет использоваться для конечных точек, `http://www.contoso.com` URI которых начинается с, и сертификат, который будет использоваться для всех остальных конечных точек, не выполняющих согласование сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d0d25-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0d25-162">См. также</span><span class="sxs-lookup"><span data-stu-id="d0d25-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="d0d25-163">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="d0d25-163">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d0d25-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d0d25-164">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="d0d25-165">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="d0d25-165">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d0d25-166">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d0d25-166">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
