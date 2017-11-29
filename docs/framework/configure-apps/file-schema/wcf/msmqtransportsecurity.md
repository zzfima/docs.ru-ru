---
title: '&lt;msmqTransportSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: eee2cb916d79bf3b79e882cd757b10344121f6b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltmsmqtransportsecuritygt"></a><span data-ttu-id="1c6be-102">&lt;msmqTransportSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="1c6be-102">&lt;msmqTransportSecurity&gt;</span></span>
<span data-ttu-id="1c6be-103">Задает параметры безопасности транспорта MSMQ для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="1c6be-103">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="1c6be-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1c6be-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1c6be-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1c6be-105">\<bindings></span></span>  
<span data-ttu-id="1c6be-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1c6be-106">\<customBinding></span></span>  
<span data-ttu-id="1c6be-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1c6be-107">\<binding></span></span>  
<span data-ttu-id="1c6be-108">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="1c6be-108">\<msmqIntegration></span></span>  
<span data-ttu-id="1c6be-109">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="1c6be-109">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6be-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c6be-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c6be-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c6be-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1c6be-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1c6be-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c6be-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c6be-113">Attributes</span></span>  
  
|<span data-ttu-id="1c6be-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1c6be-114">Attribute</span></span>|<span data-ttu-id="1c6be-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1c6be-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="1c6be-116">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1c6be-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="1c6be-117">Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.</span><span class="sxs-lookup"><span data-stu-id="1c6be-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="1c6be-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1c6be-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6be-119">— None: Проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1c6be-119">-   None: No authentication.</span></span><br /><span data-ttu-id="1c6be-120">-Windows: Механизм проверки подлинности использует Active Directory для получения сертификата X.509 для SID, связанного с сообщением.</span><span class="sxs-lookup"><span data-stu-id="1c6be-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="1c6be-121">Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.</span><span class="sxs-lookup"><span data-stu-id="1c6be-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="1c6be-122">-Certificate: Канал получает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1c6be-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="1c6be-123">Значение по умолчанию - Windows.</span><span class="sxs-lookup"><span data-stu-id="1c6be-123">The default value is Windows.</span></span> <span data-ttu-id="1c6be-124">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="1c6be-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="1c6be-125">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="1c6be-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="1c6be-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1c6be-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6be-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="1c6be-127">-   RC4Stream</span></span><br /><span data-ttu-id="1c6be-128">-AES</span><span class="sxs-lookup"><span data-stu-id="1c6be-128">-   AES</span></span><br /><br /> <span data-ttu-id="1c6be-129">Значение по умолчанию - RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="1c6be-129">The default value is RC4Stream.</span></span> <span data-ttu-id="1c6be-130">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="1c6be-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="1c6be-131">Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1c6be-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="1c6be-132">Шифрование обеспечивает целостность сообщения, а EncryptAndSign - целостность и неотрекаемость сообщения; то есть гарантируется, что сообщение на самом деле поступает от отправителя, и отправитель действительно является тем, кем называет себя.</span><span class="sxs-lookup"><span data-stu-id="1c6be-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="1c6be-133">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1c6be-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6be-134">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="1c6be-134">-   None: No protection.</span></span><br /><span data-ttu-id="1c6be-135">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="1c6be-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1c6be-136">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="1c6be-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1c6be-137">Значение по умолчанию - Sign.</span><span class="sxs-lookup"><span data-stu-id="1c6be-137">The default value is Sign.</span></span> <span data-ttu-id="1c6be-138">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="1c6be-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="1c6be-139">Задает алгоритм, который должен использоваться при вычислении дайджеста как части сигнатур.</span><span class="sxs-lookup"><span data-stu-id="1c6be-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="1c6be-140">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1c6be-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6be-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="1c6be-141">-   MD5</span></span><br /><span data-ttu-id="1c6be-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="1c6be-142">-   SHA1</span></span><br /><span data-ttu-id="1c6be-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="1c6be-143">-   SHA256</span></span><br /><span data-ttu-id="1c6be-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="1c6be-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="1c6be-145">Значение по умолчанию - SHA1.</span><span class="sxs-lookup"><span data-stu-id="1c6be-145">The default value is SHA1.</span></span> <span data-ttu-id="1c6be-146">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="1c6be-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c6be-147">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c6be-147">Child Elements</span></span>  
 <span data-ttu-id="1c6be-148">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c6be-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c6be-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c6be-149">Parent Elements</span></span>  
  
|<span data-ttu-id="1c6be-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c6be-150">Element</span></span>|<span data-ttu-id="1c6be-151">Описание</span><span class="sxs-lookup"><span data-stu-id="1c6be-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c6be-152">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="1c6be-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="1c6be-153">Задает параметры, необходимые для взаимодействия с отправителем или получателем очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="1c6be-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="1c6be-154">\<msmqTransport ></span><span class="sxs-lookup"><span data-stu-id="1c6be-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="1c6be-155">Задает свойства обмена данными в очереди для службы Windows Communication Foundation (WCF), использующей собственный протокол MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1c6be-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c6be-156">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c6be-156">Remarks</span></span>  
 <span data-ttu-id="1c6be-157">Дополнительные сведения об обеспечении безопасности транспорта см. в разделе [безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="1c6be-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6be-158">См. также</span><span class="sxs-lookup"><span data-stu-id="1c6be-158">See Also</span></span>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1c6be-159">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="1c6be-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="1c6be-160">Транспорты</span><span class="sxs-lookup"><span data-stu-id="1c6be-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="1c6be-161">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="1c6be-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="1c6be-162">Привязки</span><span class="sxs-lookup"><span data-stu-id="1c6be-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1c6be-163">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="1c6be-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1c6be-164">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="1c6be-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1c6be-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1c6be-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="1c6be-166">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="1c6be-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
