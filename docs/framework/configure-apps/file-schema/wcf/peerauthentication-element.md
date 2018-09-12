---
title: Элемент &lt;peerAuthentication&gt;
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4fb8cc4989313afa3ef16c90b54e0feae1ccb71d
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44699076"
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="e1788-102">Элемент &lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="e1788-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="e1788-103">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="e1788-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="e1788-104">Дополнительные сведения о программировании peer-to-peer см. в разделе [сети Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="e1788-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="e1788-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e1788-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e1788-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e1788-106">\<behaviors></span></span>  
<span data-ttu-id="e1788-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e1788-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="e1788-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e1788-108">\<behavior></span></span>  
<span data-ttu-id="e1788-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e1788-109">\<clientCredentials></span></span>  
<span data-ttu-id="e1788-110">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="e1788-110">\<peer></span></span>  
<span data-ttu-id="e1788-111">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e1788-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1788-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1788-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1788-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1788-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e1788-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1788-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1788-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1788-115">Attributes</span></span>  
  
|<span data-ttu-id="e1788-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1788-116">Attribute</span></span>|<span data-ttu-id="e1788-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="e1788-118">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="e1788-118">Optional string.</span></span> <span data-ttu-id="e1788-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="e1788-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e1788-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e1788-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="e1788-121">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e1788-121">Optional enumeration.</span></span> <span data-ttu-id="e1788-122">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e1788-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="e1788-123">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="e1788-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="e1788-124">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e1788-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="e1788-125">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e1788-125">Optional enumeration.</span></span> <span data-ttu-id="e1788-126">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="e1788-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="e1788-127">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="e1788-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="e1788-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e1788-128">Optional enumeration.</span></span> <span data-ttu-id="e1788-129">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e1788-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e1788-130">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="e1788-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="e1788-131">Выполнение проверки **доверенные лица** хранения в указанном местоположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="e1788-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="e1788-132">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e1788-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="e1788-133">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="e1788-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="e1788-134">Значение</span><span class="sxs-lookup"><span data-stu-id="e1788-134">Value</span></span>|<span data-ttu-id="e1788-135">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1788-136">Строковое</span><span class="sxs-lookup"><span data-stu-id="e1788-136">String</span></span>|<span data-ttu-id="e1788-137">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="e1788-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="e1788-138">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="e1788-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="e1788-139">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e1788-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="e1788-140">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e1788-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="e1788-141">Значение</span><span class="sxs-lookup"><span data-stu-id="e1788-141">Value</span></span>|<span data-ttu-id="e1788-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1788-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e1788-143">Enumeration</span></span>|<span data-ttu-id="e1788-144">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e1788-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="e1788-145">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e1788-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="e1788-146">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e1788-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="e1788-147">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="e1788-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="e1788-148">Значение</span><span class="sxs-lookup"><span data-stu-id="e1788-148">Value</span></span>|<span data-ttu-id="e1788-149">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1788-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e1788-150">Enumeration</span></span>|<span data-ttu-id="e1788-151">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="e1788-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="e1788-152">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="e1788-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="e1788-153">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e1788-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="e1788-154">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e1788-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="e1788-155">Значение</span><span class="sxs-lookup"><span data-stu-id="e1788-155">Value</span></span>|<span data-ttu-id="e1788-156">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1788-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e1788-157">Enumeration</span></span>|<span data-ttu-id="e1788-158">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e1788-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e1788-159">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e1788-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="e1788-160">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="e1788-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="e1788-161">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e1788-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1788-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1788-162">Child Elements</span></span>  
 <span data-ttu-id="e1788-163">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1788-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1788-164">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1788-164">Parent Elements</span></span>  
  
|<span data-ttu-id="e1788-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1788-165">Element</span></span>|<span data-ttu-id="e1788-166">Описание</span><span class="sxs-lookup"><span data-stu-id="e1788-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1788-167">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="e1788-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="e1788-168">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="e1788-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1788-169">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1788-169">Remarks</span></span>  
 <span data-ttu-id="e1788-170">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e1788-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="e1788-171">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="e1788-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="e1788-172">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="e1788-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="e1788-173">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="e1788-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="e1788-174">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="e1788-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1788-175">Пример</span><span class="sxs-lookup"><span data-stu-id="e1788-175">Example</span></span>  
 <span data-ttu-id="e1788-176">В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e1788-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1788-177">См. также</span><span class="sxs-lookup"><span data-stu-id="e1788-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="e1788-178">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="e1788-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e1788-179">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="e1788-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="e1788-180">Проверка подлинности сообщений однорангового канала</span><span class="sxs-lookup"><span data-stu-id="e1788-180">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="e1788-181">Нестандартной проверки подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e1788-181">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="e1788-182">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="e1788-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
