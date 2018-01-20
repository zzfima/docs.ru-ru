---
title: "&lt;transport&gt; для &lt;msmqIntegrationBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dc4f3cb08436f0f1af2e559c924446faa7b870c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="ff0cd-102">&lt;transport&gt; для &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ff0cd-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="ff0cd-103">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="ff0cd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff0cd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff0cd-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-105">\<bindings></span></span>  
<span data-ttu-id="ff0cd-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="ff0cd-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="ff0cd-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-107">\<binding></span></span>  
<span data-ttu-id="ff0cd-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-108">\<security></span></span>  
<span data-ttu-id="ff0cd-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff0cd-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff0cd-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff0cd-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff0cd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ff0cd-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff0cd-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff0cd-113">Attributes</span></span>  
  
|<span data-ttu-id="ff0cd-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ff0cd-114">Attribute</span></span>|<span data-ttu-id="ff0cd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ff0cd-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="ff0cd-116">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="ff0cd-117">Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="ff0cd-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ff0cd-119">— None: Проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-119">-   None: No authentication.</span></span><br /><span data-ttu-id="ff0cd-120">-WindowsDomain: Механизм проверки подлинности использует Active Directory для получения сертификата X.509 для SID, связанного с сообщением.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="ff0cd-121">Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="ff0cd-122">-Certificate: Канал получает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="ff0cd-123">Значение по умолчанию - WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="ff0cd-124">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="ff0cd-125">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="ff0cd-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ff0cd-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="ff0cd-127">-   RC4Stream</span></span><br /><span data-ttu-id="ff0cd-128">-AES</span><span class="sxs-lookup"><span data-stu-id="ff0cd-128">-   AES</span></span><br /><br /> <span data-ttu-id="ff0cd-129">Значение по умолчанию - RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-129">The default value is RC4Stream.</span></span> <span data-ttu-id="ff0cd-130">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="ff0cd-131">Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="ff0cd-132">Шифрование обеспечивает целостность сообщения, а EncryptAndSign - целостность и неотрекаемость сообщения; то есть гарантируется, что сообщение на самом деле поступает от отправителя, и отправитель действительно является тем, кем называет себя.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="ff0cd-133">-Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="ff0cd-134">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-134">-   None: No protection.</span></span><br /><span data-ttu-id="ff0cd-135">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ff0cd-136">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="ff0cd-137">Значение по умолчанию - Sign.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-137">The default value is Sign.</span></span> <span data-ttu-id="ff0cd-138">Это атрибут типа ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="ff0cd-139">— Задает алгоритм, который должен использоваться при вычислении дайджеста как части сигнатур.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="ff0cd-140">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-140">Valid values include the following:</span></span><br /><span data-ttu-id="ff0cd-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="ff0cd-141">-   MD5</span></span><br /><span data-ttu-id="ff0cd-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="ff0cd-142">-   SHA1</span></span><br /><span data-ttu-id="ff0cd-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="ff0cd-143">-   SHA256</span></span><br /><span data-ttu-id="ff0cd-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="ff0cd-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="ff0cd-145">Значение по умолчанию - SHA1.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-145">The default value is SHA1.</span></span> <span data-ttu-id="ff0cd-146">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff0cd-147">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff0cd-147">Child Elements</span></span>  
 <span data-ttu-id="ff0cd-148">Нет</span><span class="sxs-lookup"><span data-stu-id="ff0cd-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff0cd-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff0cd-149">Parent Elements</span></span>  
  
|<span data-ttu-id="ff0cd-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff0cd-150">Element</span></span>|<span data-ttu-id="ff0cd-151">Описание:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff0cd-152">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="ff0cd-153">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff0cd-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff0cd-154">Remarks</span></span>  
 <span data-ttu-id="ff0cd-155">Данный элемент инкапсулирует параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="ff0cd-156">Данные параметры одинаковы для интеграции очереди сообщений и использующих очереди транспортов.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="ff0cd-157">Это позволяет задать режим проверки подлинности, алгоритм шифрования, алгоритм SHA и уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0cd-158">См. также</span><span class="sxs-lookup"><span data-stu-id="ff0cd-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="ff0cd-159">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ff0cd-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ff0cd-160">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ff0cd-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ff0cd-161">Привязки</span><span class="sxs-lookup"><span data-stu-id="ff0cd-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ff0cd-162">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ff0cd-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ff0cd-163">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="ff0cd-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ff0cd-164">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ff0cd-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
