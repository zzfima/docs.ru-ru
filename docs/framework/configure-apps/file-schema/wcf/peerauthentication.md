---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1de8b8ceaf56931dfd3f09e5cc21ac939c49b4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="f9b47-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="f9b47-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="f9b47-103">Задает параметры проверки подлинности для сертификата однорангового узла, используемого одноранговым узлом.</span><span class="sxs-lookup"><span data-stu-id="f9b47-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="f9b47-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f9b47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9b47-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="f9b47-105">\<behaviors></span></span>  
<span data-ttu-id="f9b47-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f9b47-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f9b47-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="f9b47-107">\<behavior></span></span>  
<span data-ttu-id="f9b47-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="f9b47-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f9b47-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="f9b47-109">\<peer></span></span>  
<span data-ttu-id="f9b47-110">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="f9b47-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b47-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9b47-111">Syntax</span></span>  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9b47-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9b47-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f9b47-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9b47-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9b47-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9b47-114">Attributes</span></span>  
  
|<span data-ttu-id="f9b47-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f9b47-115">Attribute</span></span>|<span data-ttu-id="f9b47-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f9b47-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="f9b47-117">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="f9b47-117">Optional enumeration.</span></span> <span data-ttu-id="f9b47-118">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f9b47-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="f9b47-119">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="f9b47-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="f9b47-120">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="f9b47-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="f9b47-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="f9b47-121">Optional string.</span></span> <span data-ttu-id="f9b47-122">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="f9b47-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="f9b47-123">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f9b47-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="f9b47-124">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="f9b47-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="f9b47-125"> предоставляет используемый по умолчанию проверяющий элемент управления для сертификата точки, осуществляющий проверку того, находится ли этот сертификат в хранилище "Доверенные лица".</span><span class="sxs-lookup"><span data-stu-id="f9b47-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="f9b47-126">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="f9b47-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="f9b47-127">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="f9b47-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="f9b47-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="f9b47-128">Optional enumeration.</span></span> <span data-ttu-id="f9b47-129">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f9b47-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="f9b47-130">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="f9b47-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="f9b47-131">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f9b47-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="f9b47-132">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="f9b47-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="f9b47-133">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="f9b47-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="f9b47-134">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="f9b47-134">Optional enumeration.</span></span> <span data-ttu-id="f9b47-135">Задает расположение доверенного хранилища, где одноранговый сертификат проверяется системой безопасности [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9b47-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="f9b47-136">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="f9b47-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9b47-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9b47-137">Child Elements</span></span>  
 <span data-ttu-id="f9b47-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f9b47-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9b47-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9b47-139">Parent Elements</span></span>  
  
|<span data-ttu-id="f9b47-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9b47-140">Element</span></span>|<span data-ttu-id="f9b47-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="f9b47-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b47-142">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="f9b47-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="f9b47-143">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="f9b47-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9b47-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9b47-144">Remarks</span></span>  
 <span data-ttu-id="f9b47-145">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="f9b47-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="f9b47-146">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="f9b47-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="f9b47-147">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="f9b47-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="f9b47-148">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="f9b47-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="f9b47-149">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="f9b47-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b47-150">См. также</span><span class="sxs-lookup"><span data-stu-id="f9b47-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="f9b47-151">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="f9b47-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="f9b47-152">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="f9b47-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="f9b47-153">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="f9b47-153">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="f9b47-154">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="f9b47-154">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="f9b47-155">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="f9b47-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
