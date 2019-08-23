---
title: <authentication> элемента <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: d770ba1f9a0a18c927b3a4bf6d4141286e3a380c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919980"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="0146e-102">\<> проверки подлинности элемента > \<serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="0146e-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="0146e-103">Задает параметры, которые использует прокси клиента для проверки подлинности сертификатов службы, полученных при помощи согласования SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="0146e-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="0146e-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0146e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0146e-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0146e-105">\<behaviors></span></span>  
<span data-ttu-id="0146e-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="0146e-106">endpointBehaviors section</span></span>  
<span data-ttu-id="0146e-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0146e-107">\<behavior></span></span>  
<span data-ttu-id="0146e-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="0146e-108">\<clientCredentials></span></span>  
<span data-ttu-id="0146e-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0146e-109">\<serviceCertificate></span></span>  
<span data-ttu-id="0146e-110">\<> проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0146e-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0146e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0146e-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0146e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0146e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0146e-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0146e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0146e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0146e-114">Attributes</span></span>  
  
|<span data-ttu-id="0146e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0146e-115">Attribute</span></span>|<span data-ttu-id="0146e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0146e-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="0146e-117">customCertificateValidatorType</span></span>|<span data-ttu-id="0146e-118">Строка.</span><span class="sxs-lookup"><span data-stu-id="0146e-118">String.</span></span> <span data-ttu-id="0146e-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="0146e-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="0146e-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0146e-120">certificateValidationMode</span></span>|<span data-ttu-id="0146e-121">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0146e-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="0146e-122">Если задано значение `Custom`, также необходимо предоставить customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="0146e-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="0146e-123">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="0146e-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="0146e-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="0146e-124">revocationMode</span></span>|<span data-ttu-id="0146e-125">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="0146e-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="0146e-126">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="0146e-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="0146e-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0146e-127">trustedStoreLocation</span></span>|<span data-ttu-id="0146e-128">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0146e-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="0146e-129">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="0146e-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="0146e-130">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="0146e-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="0146e-131">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0146e-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="0146e-132">Атрибут customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="0146e-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="0146e-133">Значение</span><span class="sxs-lookup"><span data-stu-id="0146e-133">Value</span></span>|<span data-ttu-id="0146e-134">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0146e-135">String</span><span class="sxs-lookup"><span data-stu-id="0146e-135">String</span></span>|<span data-ttu-id="0146e-136">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="0146e-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="0146e-137">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0146e-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="0146e-138">Значение</span><span class="sxs-lookup"><span data-stu-id="0146e-138">Value</span></span>|<span data-ttu-id="0146e-139">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0146e-140">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0146e-140">Enumeration</span></span>|<span data-ttu-id="0146e-141">Одно из следующих значений: None, доверие одноранговой группы, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="0146e-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="0146e-142">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0146e-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="0146e-143">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="0146e-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="0146e-144">Значение</span><span class="sxs-lookup"><span data-stu-id="0146e-144">Value</span></span>|<span data-ttu-id="0146e-145">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0146e-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0146e-146">Enumeration</span></span>|<span data-ttu-id="0146e-147">Одно из следующих значений: Не проверять, в сети, вне сети.</span><span class="sxs-lookup"><span data-stu-id="0146e-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="0146e-148">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0146e-148">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="0146e-149">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0146e-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="0146e-150">Значение</span><span class="sxs-lookup"><span data-stu-id="0146e-150">Value</span></span>|<span data-ttu-id="0146e-151">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0146e-152">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0146e-152">Enumeration</span></span>|<span data-ttu-id="0146e-153">Одно из следующих значений: LocalMachine или CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="0146e-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="0146e-154">Значение по умолчанию - CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="0146e-154">The default is CurrentUser.</span></span> <span data-ttu-id="0146e-155">Если клиентское приложение выполняется в контексте системной учетной записи, сертификат обычно находится в LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0146e-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="0146e-156">Если клиентское приложение выполняется в контексте учетной записи пользователя, то сертификат обычно находится в CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="0146e-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0146e-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0146e-157">Child Elements</span></span>  
 <span data-ttu-id="0146e-158">Нет.</span><span class="sxs-lookup"><span data-stu-id="0146e-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0146e-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0146e-159">Parent Elements</span></span>  
  
|<span data-ttu-id="0146e-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="0146e-160">Element</span></span>|<span data-ttu-id="0146e-161">Описание</span><span class="sxs-lookup"><span data-stu-id="0146e-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0146e-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0146e-162">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="0146e-163">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="0146e-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0146e-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="0146e-164">Remarks</span></span>  
 <span data-ttu-id="0146e-165">Атрибут `certificateValidationMode` данного элемента конфигурации указывает уровень доверия, который используется при проверке подлинности сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0146e-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="0146e-166">По умолчанию для уровня устанавливается значение `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="0146e-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="0146e-167">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="0146e-167">This is the most secure mode.</span></span> <span data-ttu-id="0146e-168">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="0146e-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="0146e-169">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="0146e-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="0146e-170">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="0146e-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="0146e-171">Также можно задать значение `Custom` или `None`.</span><span class="sxs-lookup"><span data-stu-id="0146e-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="0146e-172">Чтобы использовать значение `Custom`, необходимо также установить атрибут `customCertificateValidator` для сборки и типа, которые используются при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="0146e-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="0146e-173">Для создания собственного пользовательского проверяющего элемента управления необходимо унаследовать его от абстрактного класса X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="0146e-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="0146e-174">Дополнительные сведения см. в разделе [Практическое руководство. Создайте службу, которая использует пользовательский проверяющий элемент управления](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0146e-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="0146e-175">Атрибут `revocationMode` указывает способ проверки отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0146e-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="0146e-176">По умолчанию используется значение `online`, которое указывает, что проверка, является ли сертификат отозванным, будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="0146e-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="0146e-177">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0146e-177">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0146e-178">Пример</span><span class="sxs-lookup"><span data-stu-id="0146e-178">Example</span></span>  
 <span data-ttu-id="0146e-179">В следующем примере выполняется две задачи.</span><span class="sxs-lookup"><span data-stu-id="0146e-179">The following example does two tasks.</span></span> <span data-ttu-id="0146e-180">Сначала он указывает сертификат службы, который будет использоваться клиентом при взаимодействии с конечными точками, доменное имя которых находится `www.contoso.com` по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="0146e-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="0146e-181">Во-вторых, в этом примере указывается режим отзыва и место хранения, которые используются при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="0146e-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0146e-182">См. также</span><span class="sxs-lookup"><span data-stu-id="0146e-182">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="0146e-183">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="0146e-183">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0146e-184">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0146e-184">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0146e-185">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="0146e-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="0146e-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="0146e-186">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="0146e-187">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="0146e-187">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0146e-188">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0146e-188">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
