---
title: Элемент <defaultCertificate>
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400419"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="30e15-102">\<Элемент > Дефаултцертификате</span><span class="sxs-lookup"><span data-stu-id="30e15-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="30e15-103">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="30e15-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="30e15-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30e15-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="30e15-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="30e15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="30e15-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="30e15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="30e15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="30e15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="30e15-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Дефаултцертификате >**</span><span class="sxs-lookup"><span data-stu-id="30e15-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e15-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30e15-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30e15-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="30e15-113">Attributes and Elements</span></span>  
 <span data-ttu-id="30e15-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="30e15-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30e15-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30e15-115">Attributes</span></span>  
  
|<span data-ttu-id="30e15-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="30e15-116">Attribute</span></span>|<span data-ttu-id="30e15-117">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30e15-118">findValue</span><span class="sxs-lookup"><span data-stu-id="30e15-118">findValue</span></span>|<span data-ttu-id="30e15-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="30e15-119">String.</span></span> <span data-ttu-id="30e15-120">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="30e15-120">The value to search for.</span></span>|  
|<span data-ttu-id="30e15-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="30e15-121">x509FindType</span></span>|<span data-ttu-id="30e15-122">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="30e15-122">Enumeration.</span></span> <span data-ttu-id="30e15-123">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="30e15-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="30e15-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="30e15-124">storeLocation</span></span>|<span data-ttu-id="30e15-125">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="30e15-125">Enumeration.</span></span> <span data-ttu-id="30e15-126">Одно из двух системных расположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="30e15-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="30e15-127">storeName</span><span class="sxs-lookup"><span data-stu-id="30e15-127">storeName</span></span>|<span data-ttu-id="30e15-128">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="30e15-128">Enumeration.</span></span> <span data-ttu-id="30e15-129">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="30e15-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="30e15-130">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="30e15-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="30e15-131">Значение</span><span class="sxs-lookup"><span data-stu-id="30e15-131">Value</span></span>|<span data-ttu-id="30e15-132">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30e15-133">String</span><span class="sxs-lookup"><span data-stu-id="30e15-133">String</span></span>|<span data-ttu-id="30e15-134">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="30e15-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="30e15-135">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="30e15-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="30e15-136">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="30e15-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="30e15-137">Значение</span><span class="sxs-lookup"><span data-stu-id="30e15-137">Value</span></span>|<span data-ttu-id="30e15-138">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30e15-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="30e15-139">Enumeration</span></span>|<span data-ttu-id="30e15-140">К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="30e15-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="30e15-141">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="30e15-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="30e15-142">Значение</span><span class="sxs-lookup"><span data-stu-id="30e15-142">Value</span></span>|<span data-ttu-id="30e15-143">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30e15-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="30e15-144">Enumeration</span></span>|<span data-ttu-id="30e15-145">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="30e15-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="30e15-146">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="30e15-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="30e15-147">Значение</span><span class="sxs-lookup"><span data-stu-id="30e15-147">Value</span></span>|<span data-ttu-id="30e15-148">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30e15-149">Перечисление</span><span class="sxs-lookup"><span data-stu-id="30e15-149">Enumeration</span></span>|<span data-ttu-id="30e15-150">К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.</span><span class="sxs-lookup"><span data-stu-id="30e15-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30e15-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30e15-151">Child Elements</span></span>  
 <span data-ttu-id="30e15-152">Нет.</span><span class="sxs-lookup"><span data-stu-id="30e15-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30e15-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="30e15-153">Parent Elements</span></span>  
  
|<span data-ttu-id="30e15-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="30e15-154">Element</span></span>|<span data-ttu-id="30e15-155">Описание</span><span class="sxs-lookup"><span data-stu-id="30e15-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30e15-156">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="30e15-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="30e15-157">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="30e15-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e15-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="30e15-158">Remarks</span></span>  
 <span data-ttu-id="30e15-159">Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="30e15-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="30e15-160">Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.</span><span class="sxs-lookup"><span data-stu-id="30e15-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30e15-161">Пример</span><span class="sxs-lookup"><span data-stu-id="30e15-161">Example</span></span>  
 <span data-ttu-id="30e15-162">В следующем примере указывается сертификат, который будет использоваться для конечных точек, `http://www.contoso.com` URI которых начинается с, и сертификат, который будет использоваться для всех остальных конечных точек, не выполняющих согласование сертификатов.</span><span class="sxs-lookup"><span data-stu-id="30e15-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30e15-163">См. также</span><span class="sxs-lookup"><span data-stu-id="30e15-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="30e15-164">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="30e15-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="30e15-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="30e15-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="30e15-166">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="30e15-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="30e15-167">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="30e15-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
