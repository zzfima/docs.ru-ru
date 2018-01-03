---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496542ca476d9af309a34b4b05a1c3c023c06124
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="badde-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="badde-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="badde-103">Задает параметры проверки подлинности для однорангового сертификата, используемого отправителем сообщения.</span><span class="sxs-lookup"><span data-stu-id="badde-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="badde-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="badde-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="badde-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="badde-105">\<behaviors></span></span>  
<span data-ttu-id="badde-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="badde-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="badde-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="badde-107">\<behavior></span></span>  
<span data-ttu-id="badde-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="badde-108">\<serviceCredentials></span></span>  
<span data-ttu-id="badde-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="badde-109">\<peer></span></span>  
<span data-ttu-id="badde-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="badde-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="badde-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="badde-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="badde-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="badde-112">Attributes and Elements</span></span>  
 <span data-ttu-id="badde-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="badde-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="badde-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="badde-114">Attributes</span></span>  
  
|<span data-ttu-id="badde-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="badde-115">Attribute</span></span>|<span data-ttu-id="badde-116">Описание</span><span class="sxs-lookup"><span data-stu-id="badde-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="badde-117">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="badde-117">Optional enumeration.</span></span> <span data-ttu-id="badde-118">Задает один из пяти режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="badde-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="badde-119">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="badde-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="badde-120">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="badde-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="badde-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="badde-121">Optional string.</span></span> <span data-ttu-id="badde-122">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="badde-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="badde-123">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="badde-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="badde-124">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="badde-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="badde-125"> предоставляет используемый по умолчанию проверяющий элемент управления для сертификата точки, осуществляющий проверку того, находится ли этот сертификат в хранилище "Доверенные лица".</span><span class="sxs-lookup"><span data-stu-id="badde-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="badde-126">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="badde-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="badde-127">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="badde-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="badde-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="badde-128">Optional enumeration.</span></span> <span data-ttu-id="badde-129">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="badde-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="badde-130">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="badde-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="badde-131">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="badde-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="badde-132">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="badde-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="badde-133">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="badde-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="badde-134">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="badde-134">Optional enumeration.</span></span> <span data-ttu-id="badde-135">Задает расположение доверенного хранилища, где одноранговый сертификат проверяется системой безопасности [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="badde-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="badde-136">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="badde-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="badde-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="badde-137">Child Elements</span></span>  
 <span data-ttu-id="badde-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="badde-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="badde-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="badde-139">Parent Elements</span></span>  
  
|<span data-ttu-id="badde-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="badde-140">Element</span></span>|<span data-ttu-id="badde-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="badde-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="badde-142">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="badde-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="badde-143">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="badde-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="badde-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="badde-144">Remarks</span></span>  
 <span data-ttu-id="badde-145">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="badde-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="badde-146">Для вывода каналов, каждое сообщение подписывается с помощью сертификата, предоставляемого [ \<сертификата >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="badde-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="badde-147">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="badde-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="badde-148">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="badde-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badde-149">См. также</span><span class="sxs-lookup"><span data-stu-id="badde-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="badde-150">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="badde-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="badde-151">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="badde-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="badde-152">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="badde-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="badde-153">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="badde-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="badde-154">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="badde-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
