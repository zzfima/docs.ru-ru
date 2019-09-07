---
title: Элемент <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400083"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="78a7a-102">\<Элемент > Пираусентикатион</span><span class="sxs-lookup"><span data-stu-id="78a7a-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="78a7a-103">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="78a7a-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="78a7a-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="78a7a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="78a7a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78a7a-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="78a7a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="78a7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="78a7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="78a7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="78a7a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Одноранговые >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="78a7a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="78a7a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Пираусентикатион >**</span><span class="sxs-lookup"><span data-stu-id="78a7a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a7a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78a7a-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78a7a-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78a7a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="78a7a-115">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78a7a-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78a7a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78a7a-116">Attributes</span></span>  
  
|<span data-ttu-id="78a7a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78a7a-117">Attribute</span></span>|<span data-ttu-id="78a7a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="78a7a-119">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="78a7a-119">Optional string.</span></span> <span data-ttu-id="78a7a-120">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="78a7a-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="78a7a-121">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="78a7a-122">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="78a7a-122">Optional enumeration.</span></span> <span data-ttu-id="78a7a-123">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="78a7a-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="78a7a-124">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="78a7a-125">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="78a7a-126">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="78a7a-126">Optional enumeration.</span></span> <span data-ttu-id="78a7a-127">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="78a7a-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="78a7a-128">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="78a7a-129">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="78a7a-129">Optional enumeration.</span></span> <span data-ttu-id="78a7a-130">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="78a7a-131">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="78a7a-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="78a7a-132">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="78a7a-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="78a7a-133">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="78a7a-134">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="78a7a-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="78a7a-135">Значение</span><span class="sxs-lookup"><span data-stu-id="78a7a-135">Value</span></span>|<span data-ttu-id="78a7a-136">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78a7a-137">String</span><span class="sxs-lookup"><span data-stu-id="78a7a-137">String</span></span>|<span data-ttu-id="78a7a-138">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="78a7a-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="78a7a-139">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="78a7a-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="78a7a-140">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="78a7a-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="78a7a-141">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="78a7a-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="78a7a-142">Значение</span><span class="sxs-lookup"><span data-stu-id="78a7a-142">Value</span></span>|<span data-ttu-id="78a7a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78a7a-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="78a7a-144">Enumeration</span></span>|<span data-ttu-id="78a7a-145">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="78a7a-146">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="78a7a-147">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="78a7a-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="78a7a-148">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="78a7a-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="78a7a-149">Значение</span><span class="sxs-lookup"><span data-stu-id="78a7a-149">Value</span></span>|<span data-ttu-id="78a7a-150">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78a7a-151">Перечисление</span><span class="sxs-lookup"><span data-stu-id="78a7a-151">Enumeration</span></span>|<span data-ttu-id="78a7a-152">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="78a7a-153">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="78a7a-154">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="78a7a-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="78a7a-155">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="78a7a-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="78a7a-156">Значение</span><span class="sxs-lookup"><span data-stu-id="78a7a-156">Value</span></span>|<span data-ttu-id="78a7a-157">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78a7a-158">Перечисление</span><span class="sxs-lookup"><span data-stu-id="78a7a-158">Enumeration</span></span>|<span data-ttu-id="78a7a-159">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="78a7a-160">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="78a7a-161">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="78a7a-162">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78a7a-163">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78a7a-163">Child Elements</span></span>  
 <span data-ttu-id="78a7a-164">Нет.</span><span class="sxs-lookup"><span data-stu-id="78a7a-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78a7a-165">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78a7a-165">Parent Elements</span></span>  
  
|<span data-ttu-id="78a7a-166">Элемент</span><span class="sxs-lookup"><span data-stu-id="78a7a-166">Element</span></span>|<span data-ttu-id="78a7a-167">Описание</span><span class="sxs-lookup"><span data-stu-id="78a7a-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78a7a-168">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="78a7a-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="78a7a-169">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="78a7a-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a7a-170">Примечания</span><span class="sxs-lookup"><span data-stu-id="78a7a-170">Remarks</span></span>  
 <span data-ttu-id="78a7a-171">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="78a7a-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="78a7a-172">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="78a7a-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="78a7a-173">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="78a7a-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="78a7a-174">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="78a7a-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="78a7a-175">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="78a7a-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a7a-176">Пример</span><span class="sxs-lookup"><span data-stu-id="78a7a-176">Example</span></span>  
 <span data-ttu-id="78a7a-177">В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78a7a-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="78a7a-178">См. также</span><span class="sxs-lookup"><span data-stu-id="78a7a-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="78a7a-179">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="78a7a-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="78a7a-180">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="78a7a-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="78a7a-181">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="78a7a-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="78a7a-182">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="78a7a-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="78a7a-183">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="78a7a-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
