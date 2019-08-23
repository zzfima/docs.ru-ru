---
title: <transport> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ede4103f9c8f2f73ac34036fe7a58242e32350e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934693"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="dbe6c-102">\<транспортное \<> из NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="dbe6c-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="dbe6c-103">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="dbe6c-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dbe6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dbe6c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dbe6c-105">\<bindings></span></span>  
<span data-ttu-id="dbe6c-106">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="dbe6c-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="dbe6c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dbe6c-107">\<binding></span></span>  
<span data-ttu-id="dbe6c-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="dbe6c-108">\<security></span></span>  
<span data-ttu-id="dbe6c-109">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="dbe6c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe6c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbe6c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbe6c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dbe6c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dbe6c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbe6c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dbe6c-113">Attributes</span></span>  
  
|<span data-ttu-id="dbe6c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dbe6c-114">Attribute</span></span>|<span data-ttu-id="dbe6c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dbe6c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbe6c-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="dbe6c-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="dbe6c-117">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="dbe6c-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dbe6c-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dbe6c-119">None Без проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-119">-   None: No authentication.</span></span><br /><span data-ttu-id="dbe6c-120">WindowsDomain Механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="dbe6c-121">Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="dbe6c-122">Certificate Канал извлекает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="dbe6c-123">Значение по умолчанию — `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="dbe6c-124">Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="dbe6c-125">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="dbe6c-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="dbe6c-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="dbe6c-127">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="dbe6c-128">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dbe6c-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dbe6c-129">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="dbe6c-129">-   RC4Stream</span></span><br /><span data-ttu-id="dbe6c-130">— AES</span><span class="sxs-lookup"><span data-stu-id="dbe6c-130">-   AES</span></span><br /><span data-ttu-id="dbe6c-131">— Значение по умолчанию `RC4Stream`—.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="dbe6c-132">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="dbe6c-133">msmqprotectionLevel</span><span class="sxs-lookup"><span data-stu-id="dbe6c-133">msmqProtectionLevel</span></span>|<span data-ttu-id="dbe6c-134">Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="dbe6c-135">Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="dbe6c-136">Это гарантирует, что сообщение действительно поступило от отправителя, и отправитель действительно является тем, за кого он себя выдает.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="dbe6c-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dbe6c-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dbe6c-138">None Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-138">-   None: No protection.</span></span><br /><span data-ttu-id="dbe6c-139">Писать Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="dbe6c-140">EncryptAndSign Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="dbe6c-141">— Значение по умолчанию — `Sign`.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="dbe6c-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="dbe6c-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="dbe6c-143">Указывает алгоритм хэширования, который будет использоваться при вычислении хэш-кода сообщения.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="dbe6c-144">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dbe6c-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dbe6c-145">-MD5</span><span class="sxs-lookup"><span data-stu-id="dbe6c-145">-   MD5</span></span><br /><span data-ttu-id="dbe6c-146">-SHA1</span><span class="sxs-lookup"><span data-stu-id="dbe6c-146">-   SHA1</span></span><br /><span data-ttu-id="dbe6c-147">-SHA256</span><span class="sxs-lookup"><span data-stu-id="dbe6c-147">-   SHA256</span></span><br /><span data-ttu-id="dbe6c-148">-SHA512</span><span class="sxs-lookup"><span data-stu-id="dbe6c-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="dbe6c-149">Значение по умолчанию — `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-149">The default is `SHA1`.</span></span> <span data-ttu-id="dbe6c-150">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="dbe6c-151">Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-151">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbe6c-152">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dbe6c-152">Child Elements</span></span>  
 <span data-ttu-id="dbe6c-153">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="dbe6c-153">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbe6c-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dbe6c-154">Parent Elements</span></span>  
  
|<span data-ttu-id="dbe6c-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="dbe6c-155">Element</span></span>|<span data-ttu-id="dbe6c-156">Описание</span><span class="sxs-lookup"><span data-stu-id="dbe6c-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbe6c-157">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="dbe6c-157">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="dbe6c-158">Определяет параметры безопасности для поставленного в очередь транспорта.</span><span class="sxs-lookup"><span data-stu-id="dbe6c-158">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbe6c-159">См. также</span><span class="sxs-lookup"><span data-stu-id="dbe6c-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="dbe6c-160">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="dbe6c-160">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="dbe6c-161">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dbe6c-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dbe6c-162">Привязки</span><span class="sxs-lookup"><span data-stu-id="dbe6c-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dbe6c-163">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="dbe6c-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dbe6c-164">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dbe6c-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dbe6c-165">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dbe6c-165">\<binding></span></span>](../../../misc/binding.md)
