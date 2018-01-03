---
title: "&lt;certificate&gt; элемента &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cbf4ac229d63ad1ab097e5dc2ffe76ccb144515
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="0313f-102">&lt;certificate&gt; элемента &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="0313f-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="0313f-103">Указывает сертификат X.509, используемый для подписания и шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="0313f-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="0313f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0313f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0313f-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="0313f-105">\<behaviors></span></span>  
<span data-ttu-id="0313f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0313f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0313f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0313f-107">\<behavior></span></span>  
<span data-ttu-id="0313f-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0313f-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0313f-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="0313f-109">\<clientCertificate></span></span>  
<span data-ttu-id="0313f-110">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="0313f-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0313f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0313f-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0313f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0313f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0313f-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0313f-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0313f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0313f-114">Attributes</span></span>  
  
|<span data-ttu-id="0313f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0313f-115">Attribute</span></span>|<span data-ttu-id="0313f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0313f-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="0313f-117">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="0313f-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0313f-118">Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType.</span><span class="sxs-lookup"><span data-stu-id="0313f-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="0313f-119">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="0313f-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="0313f-120">Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="0313f-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="0313f-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0313f-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0313f-122">-LocalMachine: хранилище сертификатов, назначенные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0313f-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="0313f-123">-CurrentUser: хранилище сертификатов, назначенные текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="0313f-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="0313f-124">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0313f-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="0313f-125">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="0313f-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="0313f-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0313f-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0313f-127">-AddressBook: Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="0313f-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="0313f-128">-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0313f-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="0313f-129">-CertificationAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0313f-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="0313f-130">-Disallowed: Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0313f-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="0313f-131">-My: Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0313f-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="0313f-132">-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0313f-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="0313f-133">-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0313f-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="0313f-134">-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="0313f-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="0313f-135">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="0313f-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="0313f-136">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="0313f-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="0313f-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0313f-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0313f-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="0313f-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="0313f-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="0313f-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="0313f-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0313f-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="0313f-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="0313f-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="0313f-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0313f-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="0313f-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="0313f-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="0313f-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="0313f-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="0313f-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="0313f-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="0313f-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="0313f-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="0313f-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="0313f-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="0313f-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="0313f-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="0313f-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="0313f-149">-   FindByExtension</span></span><br /><span data-ttu-id="0313f-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="0313f-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="0313f-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="0313f-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="0313f-152">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.</span><span class="sxs-lookup"><span data-stu-id="0313f-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="0313f-153">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="0313f-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0313f-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0313f-154">Child Elements</span></span>  
 <span data-ttu-id="0313f-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0313f-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0313f-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0313f-156">Parent Elements</span></span>  
  
|<span data-ttu-id="0313f-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="0313f-157">Element</span></span>|<span data-ttu-id="0313f-158">Описание:</span><span class="sxs-lookup"><span data-stu-id="0313f-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0313f-159">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="0313f-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="0313f-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="0313f-160">Remarks</span></span>  
 <span data-ttu-id="0313f-161">Элемент `<certificate>` используется в случаях, когда служба должна заранее получить клиентский сертификат для безопасного обмена данными с клиентом.</span><span class="sxs-lookup"><span data-stu-id="0313f-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="0313f-162">Это характерно для дуплексного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="0313f-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="0313f-163">В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.</span><span class="sxs-lookup"><span data-stu-id="0313f-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="0313f-164">Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.</span><span class="sxs-lookup"><span data-stu-id="0313f-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="0313f-165">Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.</span><span class="sxs-lookup"><span data-stu-id="0313f-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="0313f-166">Дополнительные сведения о дуплексных службах см. в разделе [как: создание дуплексного контракта](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0313f-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0313f-167">Пример</span><span class="sxs-lookup"><span data-stu-id="0313f-167">Example</span></span>  
 <span data-ttu-id="0313f-168">В следующем примере кода демонстрируется поиск соответствующего сертификата X.509 и пользовательского типа проверки в элементе `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="0313f-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0313f-169">См. также</span><span class="sxs-lookup"><span data-stu-id="0313f-169">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [<span data-ttu-id="0313f-170">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="0313f-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0313f-171">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="0313f-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="0313f-172">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0313f-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
