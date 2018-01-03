---
title: "&lt;authentication&gt; элемента &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e909bd7f6257445fe4c42dd92ae366676f72d60c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltauthenticationgt-of-ltclientcertificategt-element"></a><span data-ttu-id="560e9-102">&lt;authentication&gt; элемента &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="560e9-102">&lt;authentication&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="560e9-103">Указывает расширения функциональности аутентификации для сертификатов клиентов, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="560e9-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="560e9-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="560e9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="560e9-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="560e9-105">\<behaviors></span></span>  
<span data-ttu-id="560e9-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="560e9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="560e9-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="560e9-107">\<behavior></span></span>  
<span data-ttu-id="560e9-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="560e9-108">\<serviceCredentials></span></span>  
<span data-ttu-id="560e9-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="560e9-109">\<clientCertificate></span></span>  
<span data-ttu-id="560e9-110">\<Проверка подлинности ></span><span class="sxs-lookup"><span data-stu-id="560e9-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560e9-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="560e9-111">Syntax</span></span>  
  
```xml  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="560e9-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="560e9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="560e9-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="560e9-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="560e9-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="560e9-114">Attributes</span></span>  
  
|<span data-ttu-id="560e9-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="560e9-115">Attribute</span></span>|<span data-ttu-id="560e9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="560e9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="560e9-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="560e9-117">customCertificateValidatorType</span></span>|<span data-ttu-id="560e9-118">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="560e9-118">Optional string.</span></span> <span data-ttu-id="560e9-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="560e9-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="560e9-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="560e9-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="560e9-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="560e9-121">certificateValidationMode</span></span>|<span data-ttu-id="560e9-122">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="560e9-122">Optional enumeration.</span></span> <span data-ttu-id="560e9-123">Задает один из режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="560e9-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="560e9-124">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="560e9-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="560e9-125">Если свойству присвоено значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="560e9-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="560e9-126">Значение по умолчанию — <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="560e9-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="560e9-127">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="560e9-127">includeWindowsGroups</span></span>|<span data-ttu-id="560e9-128">Необязательный логический атрибут.</span><span class="sxs-lookup"><span data-stu-id="560e9-128">Optional Boolean.</span></span> <span data-ttu-id="560e9-129">Указывает, включены ли группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="560e9-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="560e9-130">Установка для этого атрибута значения `true` снижает производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="560e9-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="560e9-131">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="560e9-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="560e9-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="560e9-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="560e9-133">Логическое.</span><span class="sxs-lookup"><span data-stu-id="560e9-133">Boolean.</span></span> <span data-ttu-id="560e9-134">Указывает, может ли клиент сопоставляться с удостоверением Windows с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="560e9-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="560e9-135">Для этого необходимо включить службу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="560e9-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="560e9-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="560e9-136">revocationMode</span></span>|<span data-ttu-id="560e9-137">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="560e9-137">Optional enumeration.</span></span> <span data-ttu-id="560e9-138">Один из режимов, используемых для проверки списков отозванных сертификатов (RCL).</span><span class="sxs-lookup"><span data-stu-id="560e9-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="560e9-139">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="560e9-139">The default is `Online`.</span></span> <span data-ttu-id="560e9-140">Это значение не учитывается при использовании безопасности транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="560e9-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="560e9-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="560e9-141">trustedStoreLocation</span></span>|<span data-ttu-id="560e9-142">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="560e9-142">Optional enumeration.</span></span> <span data-ttu-id="560e9-143">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="560e9-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="560e9-144">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="560e9-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="560e9-145">Проверка выполняется для **доверенные лица** хранения в указанном местоположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="560e9-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="560e9-146">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="560e9-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="560e9-147">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="560e9-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="560e9-148">Значение</span><span class="sxs-lookup"><span data-stu-id="560e9-148">Value</span></span>|<span data-ttu-id="560e9-149">Описание</span><span class="sxs-lookup"><span data-stu-id="560e9-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="560e9-150">Строковое</span><span class="sxs-lookup"><span data-stu-id="560e9-150">String</span></span>|<span data-ttu-id="560e9-151">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="560e9-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="560e9-152">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="560e9-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="560e9-153">Значение</span><span class="sxs-lookup"><span data-stu-id="560e9-153">Value</span></span>|<span data-ttu-id="560e9-154">Описание</span><span class="sxs-lookup"><span data-stu-id="560e9-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="560e9-155">Перечисление</span><span class="sxs-lookup"><span data-stu-id="560e9-155">Enumeration</span></span>|<span data-ttu-id="560e9-156">Одно из следующих значений: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="560e9-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="560e9-157">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="560e9-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="560e9-158">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="560e9-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="560e9-159">Значение</span><span class="sxs-lookup"><span data-stu-id="560e9-159">Value</span></span>|<span data-ttu-id="560e9-160">Описание</span><span class="sxs-lookup"><span data-stu-id="560e9-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="560e9-161">Перечисление</span><span class="sxs-lookup"><span data-stu-id="560e9-161">Enumeration</span></span>|<span data-ttu-id="560e9-162">Одно из следующих значений: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="560e9-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="560e9-163">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="560e9-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="560e9-164">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="560e9-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="560e9-165">Значение</span><span class="sxs-lookup"><span data-stu-id="560e9-165">Value</span></span>|<span data-ttu-id="560e9-166">Описание</span><span class="sxs-lookup"><span data-stu-id="560e9-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="560e9-167">Перечисление</span><span class="sxs-lookup"><span data-stu-id="560e9-167">Enumeration</span></span>|<span data-ttu-id="560e9-168">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="560e9-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="560e9-169">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="560e9-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="560e9-170">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="560e9-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="560e9-171">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="560e9-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="560e9-172">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="560e9-172">Child Elements</span></span>  
 <span data-ttu-id="560e9-173">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="560e9-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="560e9-174">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="560e9-174">Parent Elements</span></span>  
  
|<span data-ttu-id="560e9-175">Элемент</span><span class="sxs-lookup"><span data-stu-id="560e9-175">Element</span></span>|<span data-ttu-id="560e9-176">Описание:</span><span class="sxs-lookup"><span data-stu-id="560e9-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="560e9-177">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="560e9-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="560e9-178">Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.</span><span class="sxs-lookup"><span data-stu-id="560e9-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="560e9-179">Примечания</span><span class="sxs-lookup"><span data-stu-id="560e9-179">Remarks</span></span>  
 <span data-ttu-id="560e9-180">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="560e9-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="560e9-181">Это дает возможность настраивать способ проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="560e9-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="560e9-182">Для атрибута `certificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`.</span><span class="sxs-lookup"><span data-stu-id="560e9-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="560e9-183">По умолчанию имеет значение уровень `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, заканчивающейся *корневой центр* в верхней части цепочки.</span><span class="sxs-lookup"><span data-stu-id="560e9-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="560e9-184">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="560e9-184">This is the most secure mode.</span></span> <span data-ttu-id="560e9-185">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="560e9-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="560e9-186">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="560e9-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="560e9-187">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="560e9-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="560e9-188">Также можно установить значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="560e9-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="560e9-189">При установке значения `Custom` необходимо также задать атрибут `customCertificateValidatorType` для сборки и тип, который используется при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="560e9-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="560e9-190">Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="560e9-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="560e9-191">Дополнительные сведения см. в разделе [как: создание службы, использующей пользовательское средство проверки сертификатов](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="560e9-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="560e9-192">Пример</span><span class="sxs-lookup"><span data-stu-id="560e9-192">Example</span></span>  
 <span data-ttu-id="560e9-193">В следующем примере кода задается сертификат X.509 и пользовательский тип проверки в элементе `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="560e9-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="560e9-194">См. также</span><span class="sxs-lookup"><span data-stu-id="560e9-194">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>  
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>  
 [<span data-ttu-id="560e9-195">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="560e9-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="560e9-196">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="560e9-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="560e9-197">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="560e9-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
