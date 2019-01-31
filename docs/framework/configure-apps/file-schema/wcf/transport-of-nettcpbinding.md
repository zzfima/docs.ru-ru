---
title: <transport> из <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: de1f87d8074bbf3d85f6092a4ac316f5fd20052c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266368"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="73747-102">\<Транспорт > из \<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="73747-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="73747-103">Определяет тип требований безопасности уровня сообщений для конечной точки, настроенной с [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="73747-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="73747-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="73747-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73747-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="73747-105">\<bindings></span></span>  
<span data-ttu-id="73747-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="73747-106">\<netTcpBinding></span></span>  
<span data-ttu-id="73747-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="73747-107">\<binding></span></span>  
<span data-ttu-id="73747-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="73747-108">\<security></span></span>  
<span data-ttu-id="73747-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="73747-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73747-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73747-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73747-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73747-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73747-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73747-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73747-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73747-113">Attributes</span></span>  
  
|<span data-ttu-id="73747-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73747-114">Attribute</span></span>|<span data-ttu-id="73747-115">Описание</span><span class="sxs-lookup"><span data-stu-id="73747-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73747-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="73747-116">clientCredentialType</span></span>|<span data-ttu-id="73747-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="73747-117">Optional.</span></span> <span data-ttu-id="73747-118">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="73747-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="73747-119">-Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="73747-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="73747-120">— Этот атрибут имеет тип <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="73747-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="73747-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="73747-121">protectionLevel</span></span>|<span data-ttu-id="73747-122">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="73747-122">Optional.</span></span> <span data-ttu-id="73747-123">Определяет безопасность на уровне транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="73747-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="73747-124">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="73747-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="73747-125">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="73747-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="73747-126">Значение по умолчанию — `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="73747-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="73747-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="73747-127">sslProtocols</span></span>|<span data-ttu-id="73747-128">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="73747-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="73747-129">По умолчанию используется Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="73747-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="73747-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="73747-130">policyEnforcement</span></span>|<span data-ttu-id="73747-131">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="73747-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="73747-132">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="73747-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="73747-133">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="73747-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="73747-134">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="73747-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="73747-135">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="73747-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="73747-136">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="73747-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="73747-137">Значение</span><span class="sxs-lookup"><span data-stu-id="73747-137">Value</span></span>|<span data-ttu-id="73747-138">Описание</span><span class="sxs-lookup"><span data-stu-id="73747-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73747-139">Нет</span><span class="sxs-lookup"><span data-stu-id="73747-139">None</span></span>|<span data-ttu-id="73747-140">Анонимный клиент.</span><span class="sxs-lookup"><span data-stu-id="73747-140">The client is anonymous.</span></span> <span data-ttu-id="73747-141">Это требует сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="73747-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="73747-142">Windows</span><span class="sxs-lookup"><span data-stu-id="73747-142">Windows</span></span>|<span data-ttu-id="73747-143">Задает проверку подлинности Windows для клиента с использованием согласования SP (согласование Kerberos).</span><span class="sxs-lookup"><span data-stu-id="73747-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="73747-144">Сертификат</span><span class="sxs-lookup"><span data-stu-id="73747-144">Certificate</span></span>|<span data-ttu-id="73747-145">Проверка подлинности клиента выполняется с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="73747-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="73747-146">Это требует согласования SSL и сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="73747-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="73747-147">Атрибут protectionLevel</span><span class="sxs-lookup"><span data-stu-id="73747-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="73747-148">Значение</span><span class="sxs-lookup"><span data-stu-id="73747-148">Value</span></span>|<span data-ttu-id="73747-149">Описание</span><span class="sxs-lookup"><span data-stu-id="73747-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73747-150">Нет</span><span class="sxs-lookup"><span data-stu-id="73747-150">None</span></span>|<span data-ttu-id="73747-151">Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="73747-151">No protection.</span></span>|  
|<span data-ttu-id="73747-152">Sign</span><span class="sxs-lookup"><span data-stu-id="73747-152">Sign</span></span>|<span data-ttu-id="73747-153">Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="73747-153">Messages are signed.</span></span>|  
|<span data-ttu-id="73747-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="73747-154">EncryptAndSign</span></span>|<span data-ttu-id="73747-155">-Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="73747-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73747-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73747-156">Child Elements</span></span>  
 <span data-ttu-id="73747-157">Нет</span><span class="sxs-lookup"><span data-stu-id="73747-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73747-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73747-158">Parent Elements</span></span>  
  
|<span data-ttu-id="73747-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="73747-159">Element</span></span>|<span data-ttu-id="73747-160">Описание:</span><span class="sxs-lookup"><span data-stu-id="73747-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73747-161">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="73747-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="73747-162">Задает возможности безопасности [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="73747-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73747-163">Примечания</span><span class="sxs-lookup"><span data-stu-id="73747-163">Remarks</span></span>  
 <span data-ttu-id="73747-164">Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73747-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="73747-165">Если этот режим безопасности выбран для какой-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows (Negotiate) или SSL по TCP.</span><span class="sxs-lookup"><span data-stu-id="73747-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73747-166">См. также</span><span class="sxs-lookup"><span data-stu-id="73747-166">See also</span></span>
- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="73747-167">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="73747-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="73747-168">Привязки</span><span class="sxs-lookup"><span data-stu-id="73747-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="73747-169">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="73747-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="73747-170">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="73747-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="73747-171">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="73747-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
