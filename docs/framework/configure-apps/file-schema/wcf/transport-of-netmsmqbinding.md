---
title: "&lt;transport&gt; для &lt;netMsmqBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 611d6730695c2e353782d11cb74d391107c02c35
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="052ba-102">&lt;transport&gt; для &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="052ba-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="052ba-103">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="052ba-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="052ba-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="052ba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="052ba-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="052ba-105">\<bindings></span></span>  
<span data-ttu-id="052ba-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="052ba-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="052ba-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="052ba-107">\<binding></span></span>  
<span data-ttu-id="052ba-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="052ba-108">\<security></span></span>  
<span data-ttu-id="052ba-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="052ba-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="052ba-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="052ba-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="052ba-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="052ba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="052ba-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="052ba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="052ba-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="052ba-113">Attributes</span></span>  
  
|<span data-ttu-id="052ba-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="052ba-114">Attribute</span></span>|<span data-ttu-id="052ba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="052ba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="052ba-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="052ba-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="052ba-117">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="052ba-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="052ba-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="052ba-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="052ba-119">— None: Проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="052ba-119">-   None: No authentication.</span></span><br /><span data-ttu-id="052ba-120">-WindowsDomain: Механизм проверки подлинности использует Active Directory для получения сертификата X.509 для идентификатора безопасности, связанные с данным сообщением.</span><span class="sxs-lookup"><span data-stu-id="052ba-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="052ba-121">Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.</span><span class="sxs-lookup"><span data-stu-id="052ba-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="052ba-122">-Certificate: Канал извлекает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="052ba-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="052ba-123">Значение по умолчанию — `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="052ba-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="052ba-124">Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`.</span><span class="sxs-lookup"><span data-stu-id="052ba-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="052ba-125">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="052ba-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="052ba-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="052ba-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="052ba-127">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="052ba-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="052ba-128">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="052ba-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="052ba-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="052ba-129">-   RC4Stream</span></span><br /><span data-ttu-id="052ba-130">-AES</span><span class="sxs-lookup"><span data-stu-id="052ba-130">-   AES</span></span><br /><span data-ttu-id="052ba-131">Значение по умолчанию — `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="052ba-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="052ba-132">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="052ba-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="052ba-133">msmqprotectionLevel</span><span class="sxs-lookup"><span data-stu-id="052ba-133">msmqProtectionLevel</span></span>|<span data-ttu-id="052ba-134">Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="052ba-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="052ba-135">Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность.</span><span class="sxs-lookup"><span data-stu-id="052ba-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="052ba-136">Это гарантирует, что сообщение действительно поступило от отправителя, и отправитель действительно является тем, за кого он себя выдает.</span><span class="sxs-lookup"><span data-stu-id="052ba-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="052ba-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="052ba-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="052ba-138">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="052ba-138">-   None: No protection.</span></span><br /><span data-ttu-id="052ba-139">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="052ba-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="052ba-140">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="052ba-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="052ba-141">-Значение по умолчанию — `Sign`.</span><span class="sxs-lookup"><span data-stu-id="052ba-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="052ba-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="052ba-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="052ba-143">Указывает алгоритм хэширования, который будет использоваться при вычислении дайджеста сообщения.</span><span class="sxs-lookup"><span data-stu-id="052ba-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="052ba-144">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="052ba-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="052ba-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="052ba-145">-   MD5</span></span><br /><span data-ttu-id="052ba-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="052ba-146">-   SHA1</span></span><br /><span data-ttu-id="052ba-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="052ba-147">-   SHA256</span></span><br /><span data-ttu-id="052ba-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="052ba-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="052ba-149">Значение по умолчанию — `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="052ba-149">The default is `SHA1`.</span></span> <span data-ttu-id="052ba-150">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="052ba-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="052ba-151">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="052ba-151">Child Elements</span></span>  
 <span data-ttu-id="052ba-152">Нет</span><span class="sxs-lookup"><span data-stu-id="052ba-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="052ba-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="052ba-153">Parent Elements</span></span>  
  
|<span data-ttu-id="052ba-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="052ba-154">Element</span></span>|<span data-ttu-id="052ba-155">Описание:</span><span class="sxs-lookup"><span data-stu-id="052ba-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="052ba-156">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="052ba-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="052ba-157">Определяет параметры безопасности для поставленного в очередь транспорта.</span><span class="sxs-lookup"><span data-stu-id="052ba-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="052ba-158">См. также</span><span class="sxs-lookup"><span data-stu-id="052ba-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="052ba-159">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="052ba-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="052ba-160">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="052ba-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="052ba-161">Привязки</span><span class="sxs-lookup"><span data-stu-id="052ba-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="052ba-162">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="052ba-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="052ba-163">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="052ba-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="052ba-164">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="052ba-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
