---
title: Элемент <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 09094c00b8faa28c37e202112251fee7cb4580be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934023"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="4bf64-102">\<Элемент > Пираусентикатион</span><span class="sxs-lookup"><span data-stu-id="4bf64-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="4bf64-103">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="4bf64-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="4bf64-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="4bf64-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="4bf64-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4bf64-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4bf64-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4bf64-106">\<behaviors></span></span>  
<span data-ttu-id="4bf64-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4bf64-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="4bf64-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4bf64-108">\<behavior></span></span>  
<span data-ttu-id="4bf64-109">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="4bf64-109">\<clientCredentials></span></span>  
<span data-ttu-id="4bf64-110">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="4bf64-110">\<peer></span></span>  
<span data-ttu-id="4bf64-111">\<Пираусентикатион ></span><span class="sxs-lookup"><span data-stu-id="4bf64-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf64-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bf64-112">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bf64-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4bf64-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4bf64-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4bf64-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bf64-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4bf64-115">Attributes</span></span>  
  
|<span data-ttu-id="4bf64-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4bf64-116">Attribute</span></span>|<span data-ttu-id="4bf64-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="4bf64-118">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="4bf64-118">Optional string.</span></span> <span data-ttu-id="4bf64-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="4bf64-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="4bf64-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="4bf64-121">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="4bf64-121">Optional enumeration.</span></span> <span data-ttu-id="4bf64-122">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4bf64-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="4bf64-123">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="4bf64-124">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="4bf64-125">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="4bf64-125">Optional enumeration.</span></span> <span data-ttu-id="4bf64-126">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="4bf64-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="4bf64-127">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="4bf64-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="4bf64-128">Optional enumeration.</span></span> <span data-ttu-id="4bf64-129">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4bf64-130">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="4bf64-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="4bf64-131">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="4bf64-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="4bf64-132">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="4bf64-133">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="4bf64-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="4bf64-134">Значение</span><span class="sxs-lookup"><span data-stu-id="4bf64-134">Value</span></span>|<span data-ttu-id="4bf64-135">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4bf64-136">String</span><span class="sxs-lookup"><span data-stu-id="4bf64-136">String</span></span>|<span data-ttu-id="4bf64-137">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="4bf64-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="4bf64-138">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="4bf64-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="4bf64-139">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="4bf64-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="4bf64-140">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="4bf64-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="4bf64-141">Значение</span><span class="sxs-lookup"><span data-stu-id="4bf64-141">Value</span></span>|<span data-ttu-id="4bf64-142">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4bf64-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4bf64-143">Enumeration</span></span>|<span data-ttu-id="4bf64-144">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="4bf64-145">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="4bf64-146">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4bf64-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="4bf64-147">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="4bf64-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="4bf64-148">Значение</span><span class="sxs-lookup"><span data-stu-id="4bf64-148">Value</span></span>|<span data-ttu-id="4bf64-149">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4bf64-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4bf64-150">Enumeration</span></span>|<span data-ttu-id="4bf64-151">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="4bf64-152">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="4bf64-153">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4bf64-153">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="4bf64-154">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="4bf64-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="4bf64-155">Значение</span><span class="sxs-lookup"><span data-stu-id="4bf64-155">Value</span></span>|<span data-ttu-id="4bf64-156">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4bf64-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="4bf64-157">Enumeration</span></span>|<span data-ttu-id="4bf64-158">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4bf64-159">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="4bf64-160">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="4bf64-161">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4bf64-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4bf64-162">Child Elements</span></span>  
 <span data-ttu-id="4bf64-163">Нет.</span><span class="sxs-lookup"><span data-stu-id="4bf64-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4bf64-164">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4bf64-164">Parent Elements</span></span>  
  
|<span data-ttu-id="4bf64-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="4bf64-165">Element</span></span>|<span data-ttu-id="4bf64-166">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf64-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bf64-167">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="4bf64-167">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="4bf64-168">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="4bf64-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bf64-169">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bf64-169">Remarks</span></span>  
 <span data-ttu-id="4bf64-170">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="4bf64-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="4bf64-171">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="4bf64-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="4bf64-172">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="4bf64-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="4bf64-173">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="4bf64-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="4bf64-174">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="4bf64-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bf64-175">Пример</span><span class="sxs-lookup"><span data-stu-id="4bf64-175">Example</span></span>  
 <span data-ttu-id="4bf64-176">В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4bf64-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="4bf64-177">См. также</span><span class="sxs-lookup"><span data-stu-id="4bf64-177">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="4bf64-178">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="4bf64-178">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4bf64-179">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="4bf64-179">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="4bf64-180">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4bf64-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="4bf64-181">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4bf64-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="4bf64-182">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="4bf64-182">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
