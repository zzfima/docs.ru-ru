---
title: "&lt;authentication&gt; элемента &lt; serviceCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb2f567b47f66b378cc6e0a5d5e96441ea65c1ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="e52f8-102">&lt;authentication&gt; элемента &lt; serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="e52f8-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="e52f8-103">Задает параметры, которые использует прокси клиента для проверки подлинности сертификатов службы, полученных при помощи согласования SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="e52f8-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="e52f8-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e52f8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e52f8-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e52f8-105">\<behaviors></span></span>  
<span data-ttu-id="e52f8-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="e52f8-106">endpointBehaviors section</span></span>  
<span data-ttu-id="e52f8-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e52f8-107">\<behavior></span></span>  
<span data-ttu-id="e52f8-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e52f8-108">\<clientCredentials></span></span>  
<span data-ttu-id="e52f8-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="e52f8-109">\<serviceCertificate></span></span>  
<span data-ttu-id="e52f8-110">\<Проверка подлинности ></span><span class="sxs-lookup"><span data-stu-id="e52f8-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e52f8-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e52f8-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e52f8-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e52f8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e52f8-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e52f8-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e52f8-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e52f8-114">Attributes</span></span>  
  
|<span data-ttu-id="e52f8-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e52f8-115">Attribute</span></span>|<span data-ttu-id="e52f8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e52f8-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="e52f8-117">customCertificateValidatorType</span></span>|<span data-ttu-id="e52f8-118">Строка.</span><span class="sxs-lookup"><span data-stu-id="e52f8-118">String.</span></span> <span data-ttu-id="e52f8-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="e52f8-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="e52f8-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e52f8-120">certificateValidationMode</span></span>|<span data-ttu-id="e52f8-121">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e52f8-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="e52f8-122">Если задано значение `Custom`, также необходимо предоставить customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="e52f8-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="e52f8-123">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="e52f8-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e52f8-124">revocationMode</span></span>|<span data-ttu-id="e52f8-125">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="e52f8-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="e52f8-126">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="e52f8-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e52f8-127">trustedStoreLocation</span></span>|<span data-ttu-id="e52f8-128">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e52f8-129">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="e52f8-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="e52f8-130">Проверка выполняется для **доверенные лица** хранения в указанном местоположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="e52f8-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="e52f8-131">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="e52f8-132">Атрибут customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="e52f8-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="e52f8-133">Значение</span><span class="sxs-lookup"><span data-stu-id="e52f8-133">Value</span></span>|<span data-ttu-id="e52f8-134">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e52f8-135">Строковое</span><span class="sxs-lookup"><span data-stu-id="e52f8-135">String</span></span>|<span data-ttu-id="e52f8-136">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="e52f8-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="e52f8-137">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e52f8-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="e52f8-138">Значение</span><span class="sxs-lookup"><span data-stu-id="e52f8-138">Value</span></span>|<span data-ttu-id="e52f8-139">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e52f8-140">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e52f8-140">Enumeration</span></span>|<span data-ttu-id="e52f8-141">Одно из следующих значений: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="e52f8-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="e52f8-142">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e52f8-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="e52f8-143">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="e52f8-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="e52f8-144">Значение</span><span class="sxs-lookup"><span data-stu-id="e52f8-144">Value</span></span>|<span data-ttu-id="e52f8-145">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e52f8-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e52f8-146">Enumeration</span></span>|<span data-ttu-id="e52f8-147">Одно из следующих значений: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="e52f8-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="e52f8-148">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e52f8-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="e52f8-149">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e52f8-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="e52f8-150">Значение</span><span class="sxs-lookup"><span data-stu-id="e52f8-150">Value</span></span>|<span data-ttu-id="e52f8-151">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e52f8-152">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e52f8-152">Enumeration</span></span>|<span data-ttu-id="e52f8-153">Одно из следующих значений: LocalMachine или CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="e52f8-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="e52f8-154">Значение по умолчанию - CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="e52f8-154">The default is CurrentUser.</span></span> <span data-ttu-id="e52f8-155">Если клиентское приложение выполняется в контексте системной учетной записи, сертификат обычно находится в LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="e52f8-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="e52f8-156">Если клиентское приложение выполняется в контексте учетной записи пользователя, то сертификат обычно находится в CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="e52f8-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e52f8-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e52f8-157">Child Elements</span></span>  
 <span data-ttu-id="e52f8-158">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e52f8-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e52f8-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e52f8-159">Parent Elements</span></span>  
  
|<span data-ttu-id="e52f8-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="e52f8-160">Element</span></span>|<span data-ttu-id="e52f8-161">Описание</span><span class="sxs-lookup"><span data-stu-id="e52f8-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e52f8-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="e52f8-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="e52f8-163">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="e52f8-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e52f8-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="e52f8-164">Remarks</span></span>  
 <span data-ttu-id="e52f8-165">Атрибут `certificateValidationMode` данного элемента конфигурации указывает уровень доверия, который используется при проверке подлинности сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e52f8-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="e52f8-166">По умолчанию для уровня устанавливается значение `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="e52f8-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="e52f8-167">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="e52f8-167">This is the most secure mode.</span></span> <span data-ttu-id="e52f8-168">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="e52f8-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="e52f8-169">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="e52f8-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="e52f8-170">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="e52f8-171">Также можно задать значение `Custom` или `None`.</span><span class="sxs-lookup"><span data-stu-id="e52f8-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="e52f8-172">Чтобы использовать значение `Custom`, необходимо также установить атрибут `customCertificateValidator` для сборки и типа, которые используются при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="e52f8-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="e52f8-173">Для создания собственного пользовательского проверяющего элемента управления необходимо унаследовать его от абстрактного класса X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="e52f8-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="e52f8-174">Дополнительные сведения см. в разделе [как: создание службы, использующей пользовательское средство проверки сертификатов](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="e52f8-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="e52f8-175">Атрибут `revocationMode` указывает способ проверки отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e52f8-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="e52f8-176">По умолчанию используется значение `online`, которое указывает, что проверка, является ли сертификат отозванным, будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="e52f8-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="e52f8-177">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e52f8-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e52f8-178">Пример</span><span class="sxs-lookup"><span data-stu-id="e52f8-178">Example</span></span>  
 <span data-ttu-id="e52f8-179">В следующем примере выполняется две задачи.</span><span class="sxs-lookup"><span data-stu-id="e52f8-179">The following example does two tasks.</span></span> <span data-ttu-id="e52f8-180">Во-первых, указывается сертификат службы для клиента, который должен использоваться при связи по протоколу HTTP с конечными точками, именем домена которых является www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e52f8-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is www.contoso.com over the HTTP protocol.</span></span> <span data-ttu-id="e52f8-181">Во-вторых, в этом примере указывается режим отзыва и место хранения, которые используются при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="e52f8-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e52f8-182">См. также</span><span class="sxs-lookup"><span data-stu-id="e52f8-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="e52f8-183">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="e52f8-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="e52f8-184">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="e52f8-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e52f8-185">Как: создание службы, использующей пользовательский сертификат проверяющий элемент управления</span><span class="sxs-lookup"><span data-stu-id="e52f8-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="e52f8-186">\<Проверка подлинности ></span><span class="sxs-lookup"><span data-stu-id="e52f8-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="e52f8-187">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="e52f8-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="e52f8-188">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e52f8-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
