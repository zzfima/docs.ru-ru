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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd18acaf76b2d5ccceb12b62398357b0b1655cb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="240ac-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="240ac-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="240ac-103">Задает параметры проверки подлинности для сертификата однорангового узла, используемого одноранговым узлом.</span><span class="sxs-lookup"><span data-stu-id="240ac-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="240ac-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="240ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="240ac-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="240ac-105">\<behaviors></span></span>  
<span data-ttu-id="240ac-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="240ac-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="240ac-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="240ac-107">\<behavior></span></span>  
<span data-ttu-id="240ac-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="240ac-108">\<serviceCredentials></span></span>  
<span data-ttu-id="240ac-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="240ac-109">\<peer></span></span>  
<span data-ttu-id="240ac-110">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="240ac-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240ac-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="240ac-111">Syntax</span></span>  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="240ac-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="240ac-112">Attributes and Elements</span></span>  
 <span data-ttu-id="240ac-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="240ac-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="240ac-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="240ac-114">Attributes</span></span>  
  
|<span data-ttu-id="240ac-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="240ac-115">Attribute</span></span>|<span data-ttu-id="240ac-116">Описание</span><span class="sxs-lookup"><span data-stu-id="240ac-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="240ac-117">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="240ac-117">Optional enumeration.</span></span> <span data-ttu-id="240ac-118">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="240ac-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="240ac-119">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="240ac-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="240ac-120">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="240ac-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="240ac-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="240ac-121">Optional string.</span></span> <span data-ttu-id="240ac-122">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="240ac-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="240ac-123">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="240ac-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="240ac-124">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="240ac-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="240ac-125"> предоставляет используемый по умолчанию проверяющий элемент управления для сертификата точки, осуществляющий проверку того, находится ли этот сертификат в хранилище "Доверенные лица".</span><span class="sxs-lookup"><span data-stu-id="240ac-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="240ac-126">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="240ac-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="240ac-127">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="240ac-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="240ac-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="240ac-128">Optional enumeration.</span></span> <span data-ttu-id="240ac-129">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="240ac-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="240ac-130">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="240ac-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="240ac-131">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="240ac-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="240ac-132">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="240ac-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="240ac-133">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="240ac-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="240ac-134">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="240ac-134">Optional enumeration.</span></span> <span data-ttu-id="240ac-135">Задает расположение доверенного хранилища, где одноранговый сертификат проверяется системой безопасности [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240ac-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="240ac-136">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="240ac-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="240ac-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="240ac-137">Child Elements</span></span>  
 <span data-ttu-id="240ac-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="240ac-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="240ac-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="240ac-139">Parent Elements</span></span>  
  
|<span data-ttu-id="240ac-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="240ac-140">Element</span></span>|<span data-ttu-id="240ac-141">Описание</span><span class="sxs-lookup"><span data-stu-id="240ac-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="240ac-142">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="240ac-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="240ac-143">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="240ac-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="240ac-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="240ac-144">Remarks</span></span>  
 <span data-ttu-id="240ac-145">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="240ac-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="240ac-146">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="240ac-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="240ac-147">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="240ac-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="240ac-148">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="240ac-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="240ac-149">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="240ac-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240ac-150">См. также</span><span class="sxs-lookup"><span data-stu-id="240ac-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="240ac-151">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="240ac-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="240ac-152">Одноранговые сети</span><span class="sxs-lookup"><span data-stu-id="240ac-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="240ac-153">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="240ac-153">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="240ac-154">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="240ac-154">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="240ac-155">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="240ac-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
