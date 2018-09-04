---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 8a3beb42d1064e6c6629014369628248b4cd5c8d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553801"
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="33a45-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="33a45-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="33a45-103">Задает параметры проверки подлинности для однорангового сертификата, используемого отправителем сообщения.</span><span class="sxs-lookup"><span data-stu-id="33a45-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="33a45-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="33a45-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="33a45-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="33a45-105">\<behaviors></span></span>  
<span data-ttu-id="33a45-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="33a45-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="33a45-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="33a45-107">\<behavior></span></span>  
<span data-ttu-id="33a45-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="33a45-108">\<serviceCredentials></span></span>  
<span data-ttu-id="33a45-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="33a45-109">\<peer></span></span>  
<span data-ttu-id="33a45-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="33a45-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a45-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33a45-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33a45-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33a45-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33a45-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33a45-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33a45-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33a45-114">Attributes</span></span>  
  
|<span data-ttu-id="33a45-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="33a45-115">Attribute</span></span>|<span data-ttu-id="33a45-116">Описание</span><span class="sxs-lookup"><span data-stu-id="33a45-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="33a45-117">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="33a45-117">Optional enumeration.</span></span> <span data-ttu-id="33a45-118">Задает один из пяти режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="33a45-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="33a45-119">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="33a45-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="33a45-120">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="33a45-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="33a45-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="33a45-121">Optional string.</span></span> <span data-ttu-id="33a45-122">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="33a45-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="33a45-123">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="33a45-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="33a45-124">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="33a45-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="33a45-125">Windows Communication Foundation (WCF) предоставляет используемый по умолчанию проверяющий элемент управления для сертификата, который проверяет, что одноранговый сертификат в хранилище доверенных лиц.</span><span class="sxs-lookup"><span data-stu-id="33a45-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="33a45-126">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="33a45-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="33a45-127">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="33a45-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="33a45-128">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="33a45-128">Optional enumeration.</span></span> <span data-ttu-id="33a45-129">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="33a45-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="33a45-130">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="33a45-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="33a45-131">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="33a45-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="33a45-132">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="33a45-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="33a45-133">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="33a45-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="33a45-134">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="33a45-134">Optional enumeration.</span></span> <span data-ttu-id="33a45-135">Задает расположение доверенного хранилища, где одноранговый сертификат проверяется системой безопасности WCF.</span><span class="sxs-lookup"><span data-stu-id="33a45-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="33a45-136">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="33a45-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33a45-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33a45-137">Child Elements</span></span>  
 <span data-ttu-id="33a45-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="33a45-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33a45-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33a45-139">Parent Elements</span></span>  
  
|<span data-ttu-id="33a45-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="33a45-140">Element</span></span>|<span data-ttu-id="33a45-141">Описание</span><span class="sxs-lookup"><span data-stu-id="33a45-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33a45-142">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="33a45-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="33a45-143">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="33a45-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33a45-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="33a45-144">Remarks</span></span>  
 <span data-ttu-id="33a45-145">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="33a45-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="33a45-146">Для каналов вывода каждое сообщение подписывается с помощью сертификата, предоставленного [ \<сертификата >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="33a45-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="33a45-147">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="33a45-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="33a45-148">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="33a45-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a45-149">См. также</span><span class="sxs-lookup"><span data-stu-id="33a45-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="33a45-150">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="33a45-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="33a45-151">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="33a45-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="33a45-152">Проверка подлинности сообщений однорангового канала</span><span class="sxs-lookup"><span data-stu-id="33a45-152">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="33a45-153">Нестандартной проверки подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="33a45-153">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="33a45-154">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="33a45-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
