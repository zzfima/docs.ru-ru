---
title: "Элемент &lt;peerAuthentication&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3cc625f5fdb20505f2e36c5a2d37fca0676bbb37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="aea8e-102">Элемент &lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="aea8e-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="aea8e-103">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="aea8e-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="aea8e-104">Одноранговая сеть программирования, см. в разделе [-одноранговые сети](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="aea8e-104"> peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="aea8e-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aea8e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="aea8e-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="aea8e-106">\<behaviors></span></span>  
<span data-ttu-id="aea8e-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="aea8e-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="aea8e-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="aea8e-108">\<behavior></span></span>  
<span data-ttu-id="aea8e-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="aea8e-109">\<clientCredentials></span></span>  
<span data-ttu-id="aea8e-110">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="aea8e-110">\<peer></span></span>  
<span data-ttu-id="aea8e-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="aea8e-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea8e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aea8e-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aea8e-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aea8e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aea8e-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aea8e-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aea8e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aea8e-115">Attributes</span></span>  
  
|<span data-ttu-id="aea8e-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aea8e-116">Attribute</span></span>|<span data-ttu-id="aea8e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="aea8e-118">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="aea8e-118">Optional string.</span></span> <span data-ttu-id="aea8e-119">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="aea8e-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="aea8e-120">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="aea8e-121">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="aea8e-121">Optional enumeration.</span></span> <span data-ttu-id="aea8e-122">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="aea8e-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="aea8e-123">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="aea8e-124">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="aea8e-125">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="aea8e-125">Optional enumeration.</span></span> <span data-ttu-id="aea8e-126">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="aea8e-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="aea8e-127">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="aea8e-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="aea8e-128">Optional enumeration.</span></span> <span data-ttu-id="aea8e-129">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="aea8e-130">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="aea8e-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="aea8e-131">Проверка выполняется для **доверенные лица** хранения в указанном местоположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="aea8e-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="aea8e-132">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="aea8e-133">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="aea8e-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="aea8e-134">Значение</span><span class="sxs-lookup"><span data-stu-id="aea8e-134">Value</span></span>|<span data-ttu-id="aea8e-135">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aea8e-136">Строковое</span><span class="sxs-lookup"><span data-stu-id="aea8e-136">String</span></span>|<span data-ttu-id="aea8e-137">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="aea8e-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="aea8e-138">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="aea8e-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="aea8e-139">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="aea8e-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="aea8e-140">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="aea8e-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="aea8e-141">Значение</span><span class="sxs-lookup"><span data-stu-id="aea8e-141">Value</span></span>|<span data-ttu-id="aea8e-142">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aea8e-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="aea8e-143">Enumeration</span></span>|<span data-ttu-id="aea8e-144">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="aea8e-145">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="aea8e-146">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="aea8e-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="aea8e-147">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="aea8e-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="aea8e-148">Значение</span><span class="sxs-lookup"><span data-stu-id="aea8e-148">Value</span></span>|<span data-ttu-id="aea8e-149">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aea8e-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="aea8e-150">Enumeration</span></span>|<span data-ttu-id="aea8e-151">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="aea8e-152">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="aea8e-153">Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="aea8e-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="aea8e-154">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="aea8e-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="aea8e-155">Значение</span><span class="sxs-lookup"><span data-stu-id="aea8e-155">Value</span></span>|<span data-ttu-id="aea8e-156">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aea8e-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="aea8e-157">Enumeration</span></span>|<span data-ttu-id="aea8e-158">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="aea8e-159">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="aea8e-160">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="aea8e-161">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aea8e-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aea8e-162">Child Elements</span></span>  
 <span data-ttu-id="aea8e-163">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aea8e-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aea8e-164">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aea8e-164">Parent Elements</span></span>  
  
|<span data-ttu-id="aea8e-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="aea8e-165">Element</span></span>|<span data-ttu-id="aea8e-166">Описание</span><span class="sxs-lookup"><span data-stu-id="aea8e-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aea8e-167">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="aea8e-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="aea8e-168">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="aea8e-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aea8e-169">Примечания</span><span class="sxs-lookup"><span data-stu-id="aea8e-169">Remarks</span></span>  
 <span data-ttu-id="aea8e-170">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="aea8e-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="aea8e-171">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="aea8e-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="aea8e-172">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="aea8e-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="aea8e-173">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="aea8e-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="aea8e-174">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="aea8e-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aea8e-175">Пример</span><span class="sxs-lookup"><span data-stu-id="aea8e-175">Example</span></span>  
 <span data-ttu-id="aea8e-176">В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="aea8e-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aea8e-177">См. также</span><span class="sxs-lookup"><span data-stu-id="aea8e-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="aea8e-178">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="aea8e-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="aea8e-179">Одноранговые сети</span><span class="sxs-lookup"><span data-stu-id="aea8e-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="aea8e-180">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="aea8e-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="aea8e-181">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="aea8e-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="aea8e-182">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="aea8e-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
