---
title: <messageSenderAuthentication> - элемент
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 63b6e62b55759c47a7b453b3db7d91e0bc430b2d
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758759"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="0db1a-102">\<messageSenderAuthentication > элемент</span><span class="sxs-lookup"><span data-stu-id="0db1a-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="0db1a-103">Задает параметры проверки подлинности для одноранговых отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="0db1a-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="0db1a-104">Дополнительные сведения о программировании peer-to-peer см. в разделе [сети Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="0db1a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="0db1a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0db1a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0db1a-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="0db1a-106">\<behaviors></span></span>  
<span data-ttu-id="0db1a-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0db1a-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="0db1a-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="0db1a-108">\<behavior></span></span>  
<span data-ttu-id="0db1a-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0db1a-109">\<clientCredentials></span></span>  
<span data-ttu-id="0db1a-110">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="0db1a-110">\<peer></span></span>  
<span data-ttu-id="0db1a-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="0db1a-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db1a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0db1a-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0db1a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0db1a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0db1a-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0db1a-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0db1a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0db1a-115">Attributes</span></span>  
  
|<span data-ttu-id="0db1a-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0db1a-116">Attribute</span></span>|<span data-ttu-id="0db1a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0db1a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0db1a-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="0db1a-118">customCertificateValidatorType</span></span>|<span data-ttu-id="0db1a-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="0db1a-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="0db1a-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="0db1a-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0db1a-121">certifcateValidationMode</span></span>|<span data-ttu-id="0db1a-122">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0db1a-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="0db1a-123">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="0db1a-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="0db1a-124">revocationMode</span></span>|<span data-ttu-id="0db1a-125">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="0db1a-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="0db1a-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0db1a-126">trustedStoreLocation</span></span>|<span data-ttu-id="0db1a-127">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="0db1a-128">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="0db1a-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="0db1a-129">Выполнение проверки **доверенные лица** хранения в указанном местоположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="0db1a-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="0db1a-130">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="0db1a-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="0db1a-131">Значение</span><span class="sxs-lookup"><span data-stu-id="0db1a-131">Value</span></span>|<span data-ttu-id="0db1a-132">Описание</span><span class="sxs-lookup"><span data-stu-id="0db1a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0db1a-133">Строковое</span><span class="sxs-lookup"><span data-stu-id="0db1a-133">String</span></span>|<span data-ttu-id="0db1a-134">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0db1a-134">Optional.</span></span> <span data-ttu-id="0db1a-135">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="0db1a-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="0db1a-136">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="0db1a-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="0db1a-137">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="0db1a-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="0db1a-138">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0db1a-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="0db1a-139">Значение</span><span class="sxs-lookup"><span data-stu-id="0db1a-139">Value</span></span>|<span data-ttu-id="0db1a-140">Описание</span><span class="sxs-lookup"><span data-stu-id="0db1a-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0db1a-141">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0db1a-141">Enumeration</span></span>|<span data-ttu-id="0db1a-142">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0db1a-142">Optional.</span></span> <span data-ttu-id="0db1a-143">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="0db1a-144">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="0db1a-145">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="0db1a-146">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0db1a-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="0db1a-147">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="0db1a-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="0db1a-148">Значение</span><span class="sxs-lookup"><span data-stu-id="0db1a-148">Value</span></span>|<span data-ttu-id="0db1a-149">Описание</span><span class="sxs-lookup"><span data-stu-id="0db1a-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0db1a-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0db1a-150">Enumeration</span></span>|<span data-ttu-id="0db1a-151">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="0db1a-152">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="0db1a-153">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0db1a-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="0db1a-154">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0db1a-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="0db1a-155">Значение</span><span class="sxs-lookup"><span data-stu-id="0db1a-155">Value</span></span>|<span data-ttu-id="0db1a-156">Описание</span><span class="sxs-lookup"><span data-stu-id="0db1a-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0db1a-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0db1a-157">Enumeration</span></span>|<span data-ttu-id="0db1a-158">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="0db1a-159">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="0db1a-160">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="0db1a-161">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="0db1a-162">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0db1a-163">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0db1a-163">Child Elements</span></span>  
 <span data-ttu-id="0db1a-164">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0db1a-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0db1a-165">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0db1a-165">Parent Elements</span></span>  
  
|<span data-ttu-id="0db1a-166">Элемент</span><span class="sxs-lookup"><span data-stu-id="0db1a-166">Element</span></span>|<span data-ttu-id="0db1a-167">Описание:</span><span class="sxs-lookup"><span data-stu-id="0db1a-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0db1a-168">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="0db1a-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="0db1a-169">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="0db1a-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0db1a-170">Примечания</span><span class="sxs-lookup"><span data-stu-id="0db1a-170">Remarks</span></span>  
 <span data-ttu-id="0db1a-171">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="0db1a-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="0db1a-172">Для каналов вывода каждое сообщение подписывается с помощью сертификата, предоставленного [ \<сертификата >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="0db1a-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="0db1a-173">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="0db1a-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="0db1a-174">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0db1a-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0db1a-175">Пример</span><span class="sxs-lookup"><span data-stu-id="0db1a-175">Example</span></span>  
 <span data-ttu-id="0db1a-176">В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="0db1a-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="0db1a-177">См. также</span><span class="sxs-lookup"><span data-stu-id="0db1a-177">See also</span></span>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="0db1a-178">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0db1a-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0db1a-179">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="0db1a-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="0db1a-180">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0db1a-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0db1a-181">[Нестандартной проверки подлинности одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0db1a-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0db1a-182">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="0db1a-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
