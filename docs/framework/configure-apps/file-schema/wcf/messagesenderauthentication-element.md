---
title: Элемент <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931379"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="1bea2-102">\<Элемент > Мессажесендераусентикатион</span><span class="sxs-lookup"><span data-stu-id="1bea2-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="1bea2-103">Задает параметры проверки подлинности для одноранговых отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="1bea2-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="1bea2-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="1bea2-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="1bea2-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1bea2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1bea2-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1bea2-106">\<behaviors></span></span>  
<span data-ttu-id="1bea2-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1bea2-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="1bea2-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1bea2-108">\<behavior></span></span>  
<span data-ttu-id="1bea2-109">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="1bea2-109">\<clientCredentials></span></span>  
<span data-ttu-id="1bea2-110">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="1bea2-110">\<peer></span></span>  
<span data-ttu-id="1bea2-111">\<Мессажесендераусентикатион ></span><span class="sxs-lookup"><span data-stu-id="1bea2-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bea2-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bea2-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bea2-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1bea2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1bea2-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1bea2-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bea2-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1bea2-115">Attributes</span></span>  
  
|<span data-ttu-id="1bea2-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1bea2-116">Attribute</span></span>|<span data-ttu-id="1bea2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="1bea2-118">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="1bea2-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1bea2-119">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="1bea2-120">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1bea2-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="1bea2-121">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="1bea2-122">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="1bea2-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1bea2-123">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1bea2-124">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="1bea2-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="1bea2-125">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="1bea2-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="1bea2-126">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="1bea2-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="1bea2-127">Значение</span><span class="sxs-lookup"><span data-stu-id="1bea2-127">Value</span></span>|<span data-ttu-id="1bea2-128">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1bea2-129">String</span><span class="sxs-lookup"><span data-stu-id="1bea2-129">String</span></span>|<span data-ttu-id="1bea2-130">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1bea2-130">Optional.</span></span> <span data-ttu-id="1bea2-131">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="1bea2-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="1bea2-132">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="1bea2-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="1bea2-133">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="1bea2-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="1bea2-134">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1bea2-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="1bea2-135">Значение</span><span class="sxs-lookup"><span data-stu-id="1bea2-135">Value</span></span>|<span data-ttu-id="1bea2-136">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1bea2-137">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1bea2-137">Enumeration</span></span>|<span data-ttu-id="1bea2-138">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1bea2-138">Optional.</span></span> <span data-ttu-id="1bea2-139">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="1bea2-140">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="1bea2-141">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="1bea2-142">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1bea2-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="1bea2-143">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="1bea2-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="1bea2-144">Значение</span><span class="sxs-lookup"><span data-stu-id="1bea2-144">Value</span></span>|<span data-ttu-id="1bea2-145">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1bea2-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1bea2-146">Enumeration</span></span>|<span data-ttu-id="1bea2-147">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="1bea2-148">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="1bea2-149">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="1bea2-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="1bea2-150">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1bea2-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="1bea2-151">Значение</span><span class="sxs-lookup"><span data-stu-id="1bea2-151">Value</span></span>|<span data-ttu-id="1bea2-152">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1bea2-153">Перечисление</span><span class="sxs-lookup"><span data-stu-id="1bea2-153">Enumeration</span></span>|<span data-ttu-id="1bea2-154">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1bea2-155">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="1bea2-156">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="1bea2-157">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="1bea2-158">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bea2-159">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1bea2-159">Child Elements</span></span>  
 <span data-ttu-id="1bea2-160">Нет.</span><span class="sxs-lookup"><span data-stu-id="1bea2-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bea2-161">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1bea2-161">Parent Elements</span></span>  
  
|<span data-ttu-id="1bea2-162">Элемент</span><span class="sxs-lookup"><span data-stu-id="1bea2-162">Element</span></span>|<span data-ttu-id="1bea2-163">Описание</span><span class="sxs-lookup"><span data-stu-id="1bea2-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bea2-164">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="1bea2-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1bea2-165">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="1bea2-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bea2-166">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bea2-166">Remarks</span></span>  
 <span data-ttu-id="1bea2-167">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="1bea2-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="1bea2-168">Для выходных каналов каждое сообщение подписывается с помощью сертификата, [ \<](certificate-element.md)предоставленного сертификатом >.</span><span class="sxs-lookup"><span data-stu-id="1bea2-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="1bea2-169">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1bea2-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="1bea2-170">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1bea2-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bea2-171">Пример</span><span class="sxs-lookup"><span data-stu-id="1bea2-171">Example</span></span>  
 <span data-ttu-id="1bea2-172">В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1bea2-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1bea2-173">См. также</span><span class="sxs-lookup"><span data-stu-id="1bea2-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="1bea2-174">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="1bea2-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1bea2-175">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="1bea2-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1bea2-176">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1bea2-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1bea2-177">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1bea2-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1bea2-178">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="1bea2-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
