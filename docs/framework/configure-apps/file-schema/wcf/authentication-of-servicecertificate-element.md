---
title: <authentication> элемента <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398229"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="6d753-102">\<> проверки подлинности элемента > \<serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="6d753-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="6d753-103">Задает параметры, которые использует прокси клиента для проверки подлинности сертификатов службы, полученных при помощи согласования SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="6d753-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="6d753-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6d753-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6d753-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6d753-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6d753-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6d753-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="6d753-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d753-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="6d753-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="6d753-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d753-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d753-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d753-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d753-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6d753-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6d753-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d753-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d753-115">Attributes</span></span>  
  
|<span data-ttu-id="6d753-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6d753-116">Attribute</span></span>|<span data-ttu-id="6d753-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d753-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="6d753-118">customCertificateValidatorType</span></span>|<span data-ttu-id="6d753-119">Строка.</span><span class="sxs-lookup"><span data-stu-id="6d753-119">String.</span></span> <span data-ttu-id="6d753-120">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="6d753-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="6d753-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6d753-121">certificateValidationMode</span></span>|<span data-ttu-id="6d753-122">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="6d753-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="6d753-123">Если задано значение `Custom`, также необходимо предоставить customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="6d753-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="6d753-124">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6d753-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="6d753-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6d753-125">revocationMode</span></span>|<span data-ttu-id="6d753-126">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="6d753-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="6d753-127">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="6d753-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="6d753-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6d753-128">trustedStoreLocation</span></span>|<span data-ttu-id="6d753-129">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6d753-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6d753-130">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="6d753-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="6d753-131">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="6d753-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="6d753-132">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="6d753-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="6d753-133">Атрибут customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="6d753-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="6d753-134">Значение</span><span class="sxs-lookup"><span data-stu-id="6d753-134">Value</span></span>|<span data-ttu-id="6d753-135">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d753-136">String</span><span class="sxs-lookup"><span data-stu-id="6d753-136">String</span></span>|<span data-ttu-id="6d753-137">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="6d753-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="6d753-138">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6d753-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="6d753-139">Значение</span><span class="sxs-lookup"><span data-stu-id="6d753-139">Value</span></span>|<span data-ttu-id="6d753-140">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d753-141">Перечисление</span><span class="sxs-lookup"><span data-stu-id="6d753-141">Enumeration</span></span>|<span data-ttu-id="6d753-142">Одно из следующих значений: None, доверие одноранговой группы, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="6d753-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="6d753-143">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6d753-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="6d753-144">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="6d753-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="6d753-145">Значение</span><span class="sxs-lookup"><span data-stu-id="6d753-145">Value</span></span>|<span data-ttu-id="6d753-146">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d753-147">Перечисление</span><span class="sxs-lookup"><span data-stu-id="6d753-147">Enumeration</span></span>|<span data-ttu-id="6d753-148">Одно из следующих значений: Не проверять, в сети, вне сети.</span><span class="sxs-lookup"><span data-stu-id="6d753-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="6d753-149">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6d753-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="6d753-150">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6d753-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="6d753-151">Значение</span><span class="sxs-lookup"><span data-stu-id="6d753-151">Value</span></span>|<span data-ttu-id="6d753-152">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d753-153">Перечисление</span><span class="sxs-lookup"><span data-stu-id="6d753-153">Enumeration</span></span>|<span data-ttu-id="6d753-154">Одно из следующих значений: LocalMachine или CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6d753-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="6d753-155">Значение по умолчанию - CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6d753-155">The default is CurrentUser.</span></span> <span data-ttu-id="6d753-156">Если клиентское приложение выполняется в контексте системной учетной записи, сертификат обычно находится в LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="6d753-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="6d753-157">Если клиентское приложение выполняется в контексте учетной записи пользователя, то сертификат обычно находится в CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="6d753-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d753-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d753-158">Child Elements</span></span>  
 <span data-ttu-id="6d753-159">Нет.</span><span class="sxs-lookup"><span data-stu-id="6d753-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d753-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d753-160">Parent Elements</span></span>  
  
|<span data-ttu-id="6d753-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d753-161">Element</span></span>|<span data-ttu-id="6d753-162">Описание</span><span class="sxs-lookup"><span data-stu-id="6d753-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d753-163">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="6d753-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="6d753-164">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="6d753-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d753-165">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d753-165">Remarks</span></span>  
 <span data-ttu-id="6d753-166">Атрибут `certificateValidationMode` данного элемента конфигурации указывает уровень доверия, который используется при проверке подлинности сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6d753-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="6d753-167">По умолчанию для уровня устанавливается значение `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="6d753-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="6d753-168">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="6d753-168">This is the most secure mode.</span></span> <span data-ttu-id="6d753-169">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="6d753-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="6d753-170">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="6d753-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="6d753-171">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="6d753-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="6d753-172">Также можно задать значение `Custom` или `None`.</span><span class="sxs-lookup"><span data-stu-id="6d753-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="6d753-173">Чтобы использовать значение `Custom`, необходимо также установить атрибут `customCertificateValidator` для сборки и типа, которые используются при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="6d753-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="6d753-174">Для создания собственного пользовательского проверяющего элемента управления необходимо унаследовать его от абстрактного класса X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="6d753-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="6d753-175">Дополнительные сведения см. в разделе [Практическое руководство. Создайте службу, которая использует пользовательский проверяющий элемент управления](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6d753-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="6d753-176">Атрибут `revocationMode` указывает способ проверки отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6d753-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="6d753-177">По умолчанию используется значение `online`, которое указывает, что проверка, является ли сертификат отозванным, будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="6d753-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="6d753-178">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6d753-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d753-179">Пример</span><span class="sxs-lookup"><span data-stu-id="6d753-179">Example</span></span>  
 <span data-ttu-id="6d753-180">В следующем примере выполняется две задачи.</span><span class="sxs-lookup"><span data-stu-id="6d753-180">The following example does two tasks.</span></span> <span data-ttu-id="6d753-181">Сначала он указывает сертификат службы, который будет использоваться клиентом при взаимодействии с конечными точками, доменное имя которых находится `www.contoso.com` по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="6d753-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="6d753-182">Во-вторых, в этом примере указывается режим отзыва и место хранения, которые используются при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="6d753-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d753-183">См. также</span><span class="sxs-lookup"><span data-stu-id="6d753-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="6d753-184">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="6d753-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6d753-185">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="6d753-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6d753-186">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="6d753-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="6d753-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="6d753-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="6d753-188">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="6d753-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="6d753-189">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6d753-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
