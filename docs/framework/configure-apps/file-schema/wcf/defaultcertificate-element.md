---
title: Элемент &lt;defaultCertificate&gt;
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: a4af1c6ec452b24634fa50162fa71f069e2451f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751016"
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="34a60-102">Элемент &lt;defaultCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="34a60-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="34a60-103">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="34a60-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="34a60-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="34a60-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="34a60-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="34a60-105">\<behaviors></span></span>  
<span data-ttu-id="34a60-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="34a60-106">endpointBehaviors section</span></span>  
<span data-ttu-id="34a60-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="34a60-107">\<behavior></span></span>  
<span data-ttu-id="34a60-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="34a60-108">\<clientCredentials></span></span>  
<span data-ttu-id="34a60-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="34a60-109">\<serviceCertificate></span></span>  
<span data-ttu-id="34a60-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="34a60-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a60-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34a60-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34a60-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="34a60-112">Attributes and Elements</span></span>  
 <span data-ttu-id="34a60-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="34a60-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34a60-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="34a60-114">Attributes</span></span>  
  
|<span data-ttu-id="34a60-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="34a60-115">Attribute</span></span>|<span data-ttu-id="34a60-116">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34a60-117">findValue</span><span class="sxs-lookup"><span data-stu-id="34a60-117">findValue</span></span>|<span data-ttu-id="34a60-118">Строка.</span><span class="sxs-lookup"><span data-stu-id="34a60-118">String.</span></span> <span data-ttu-id="34a60-119">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="34a60-119">The value to search for.</span></span>|  
|<span data-ttu-id="34a60-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="34a60-120">x509FindType</span></span>|<span data-ttu-id="34a60-121">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="34a60-121">Enumeration.</span></span> <span data-ttu-id="34a60-122">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="34a60-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="34a60-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="34a60-123">storeLocation</span></span>|<span data-ttu-id="34a60-124">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="34a60-124">Enumeration.</span></span> <span data-ttu-id="34a60-125">Одно из двух системных расположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="34a60-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="34a60-126">storeName</span><span class="sxs-lookup"><span data-stu-id="34a60-126">storeName</span></span>|<span data-ttu-id="34a60-127">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="34a60-127">Enumeration.</span></span> <span data-ttu-id="34a60-128">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="34a60-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="34a60-129">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="34a60-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="34a60-130">Значение</span><span class="sxs-lookup"><span data-stu-id="34a60-130">Value</span></span>|<span data-ttu-id="34a60-131">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34a60-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="34a60-132">String</span></span>|<span data-ttu-id="34a60-133">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="34a60-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="34a60-134">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="34a60-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="34a60-135">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="34a60-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="34a60-136">Значение</span><span class="sxs-lookup"><span data-stu-id="34a60-136">Value</span></span>|<span data-ttu-id="34a60-137">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34a60-138">Перечисление</span><span class="sxs-lookup"><span data-stu-id="34a60-138">Enumeration</span></span>|<span data-ttu-id="34a60-139">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="34a60-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="34a60-140">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="34a60-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="34a60-141">Значение</span><span class="sxs-lookup"><span data-stu-id="34a60-141">Value</span></span>|<span data-ttu-id="34a60-142">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34a60-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="34a60-143">Enumeration</span></span>|<span data-ttu-id="34a60-144">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="34a60-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="34a60-145">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="34a60-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="34a60-146">Значение</span><span class="sxs-lookup"><span data-stu-id="34a60-146">Value</span></span>|<span data-ttu-id="34a60-147">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34a60-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="34a60-148">Enumeration</span></span>|<span data-ttu-id="34a60-149">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="34a60-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34a60-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="34a60-150">Child Elements</span></span>  
 <span data-ttu-id="34a60-151">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="34a60-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34a60-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="34a60-152">Parent Elements</span></span>  
  
|<span data-ttu-id="34a60-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="34a60-153">Element</span></span>|<span data-ttu-id="34a60-154">Описание</span><span class="sxs-lookup"><span data-stu-id="34a60-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34a60-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="34a60-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="34a60-156">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="34a60-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34a60-157">Примечания</span><span class="sxs-lookup"><span data-stu-id="34a60-157">Remarks</span></span>  
 <span data-ttu-id="34a60-158">Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="34a60-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="34a60-159">Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.</span><span class="sxs-lookup"><span data-stu-id="34a60-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a60-160">Пример</span><span class="sxs-lookup"><span data-stu-id="34a60-160">Example</span></span>  
 <span data-ttu-id="34a60-161">В следующем примере задается сертификат для конечных точек, чей URI начинается с http://www.contoso.com и сертификат для использования для всех конечных точек, не выполняющих согласование сертификатов.</span><span class="sxs-lookup"><span data-stu-id="34a60-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34a60-162">См. также</span><span class="sxs-lookup"><span data-stu-id="34a60-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="34a60-163">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="34a60-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="34a60-164">\<Проверка подлинности ></span><span class="sxs-lookup"><span data-stu-id="34a60-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="34a60-165">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="34a60-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="34a60-166">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="34a60-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
