---
title: <transport> из <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 41f11be9b4ae8f7a7535c9766965de8575cff784
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399318"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="809b5-102">\<transport>  — \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="809b5-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="809b5-103">Определяет тип требований безопасности на уровне сообщений для конечной точки, [ \<](nettcpbinding.md)настроенной с помощью > NetTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="809b5-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="809b5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="809b5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="809b5-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="809b5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="809b5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="809b5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="809b5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="809b5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="809b5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="809b5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="809b5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="809b5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="809b5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="809b5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809b5-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="809b5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="809b5-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="809b5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="809b5-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="809b5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="809b5-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="809b5-114">Attributes</span></span>  
  
|<span data-ttu-id="809b5-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="809b5-115">Attribute</span></span>|<span data-ttu-id="809b5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="809b5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="809b5-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="809b5-117">clientCredentialType</span></span>|<span data-ttu-id="809b5-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="809b5-118">Optional.</span></span> <span data-ttu-id="809b5-119">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="809b5-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="809b5-120">— Значение по умолчанию `Windows`—.</span><span class="sxs-lookup"><span data-stu-id="809b5-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="809b5-121">— Этот атрибут имеет тип <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="809b5-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="809b5-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="809b5-122">protectionLevel</span></span>|<span data-ttu-id="809b5-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="809b5-123">Optional.</span></span> <span data-ttu-id="809b5-124">Определяет безопасность на уровне транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="809b5-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="809b5-125">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="809b5-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="809b5-126">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="809b5-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="809b5-127">Значение по умолчанию — `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="809b5-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="809b5-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="809b5-128">sslProtocols</span></span>|<span data-ttu-id="809b5-129">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="809b5-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="809b5-130">Значение по умолчанию&#124;—&#124;TLS Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="809b5-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="809b5-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="809b5-131">policyEnforcement</span></span>|<span data-ttu-id="809b5-132">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="809b5-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="809b5-133">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="809b5-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="809b5-134">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="809b5-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="809b5-135">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="809b5-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="809b5-136">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="809b5-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="809b5-137">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="809b5-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="809b5-138">Значение</span><span class="sxs-lookup"><span data-stu-id="809b5-138">Value</span></span>|<span data-ttu-id="809b5-139">Описание</span><span class="sxs-lookup"><span data-stu-id="809b5-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="809b5-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="809b5-140">None</span></span>|<span data-ttu-id="809b5-141">Анонимный клиент.</span><span class="sxs-lookup"><span data-stu-id="809b5-141">The client is anonymous.</span></span> <span data-ttu-id="809b5-142">Это требует сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="809b5-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="809b5-143">Windows</span><span class="sxs-lookup"><span data-stu-id="809b5-143">Windows</span></span>|<span data-ttu-id="809b5-144">Задает проверку подлинности Windows для клиента с использованием согласования SP (согласование Kerberos).</span><span class="sxs-lookup"><span data-stu-id="809b5-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="809b5-145">Сертификат</span><span class="sxs-lookup"><span data-stu-id="809b5-145">Certificate</span></span>|<span data-ttu-id="809b5-146">Проверка подлинности клиента выполняется с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="809b5-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="809b5-147">Это требует согласования SSL и сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="809b5-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="809b5-148">Атрибут protectionLevel</span><span class="sxs-lookup"><span data-stu-id="809b5-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="809b5-149">Значение</span><span class="sxs-lookup"><span data-stu-id="809b5-149">Value</span></span>|<span data-ttu-id="809b5-150">Описание</span><span class="sxs-lookup"><span data-stu-id="809b5-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="809b5-151">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="809b5-151">None</span></span>|<span data-ttu-id="809b5-152">Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="809b5-152">No protection.</span></span>|  
|<span data-ttu-id="809b5-153">Sign</span><span class="sxs-lookup"><span data-stu-id="809b5-153">Sign</span></span>|<span data-ttu-id="809b5-154">Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="809b5-154">Messages are signed.</span></span>|  
|<span data-ttu-id="809b5-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="809b5-155">EncryptAndSign</span></span>|<span data-ttu-id="809b5-156">— Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="809b5-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="809b5-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="809b5-157">Child Elements</span></span>  
 <span data-ttu-id="809b5-158">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="809b5-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="809b5-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="809b5-159">Parent Elements</span></span>  
  
|<span data-ttu-id="809b5-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="809b5-160">Element</span></span>|<span data-ttu-id="809b5-161">Описание</span><span class="sxs-lookup"><span data-stu-id="809b5-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="809b5-162">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="809b5-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="809b5-163">Указывает возможности [ \<безопасности > NetTcpBinding](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="809b5-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="809b5-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="809b5-164">Remarks</span></span>  
 <span data-ttu-id="809b5-165">Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="809b5-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="809b5-166">Если этот режим безопасности выбран для какой-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows (Negotiate) или SSL по TCP.</span><span class="sxs-lookup"><span data-stu-id="809b5-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809b5-167">См. также</span><span class="sxs-lookup"><span data-stu-id="809b5-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="809b5-168">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="809b5-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="809b5-169">Привязки</span><span class="sxs-lookup"><span data-stu-id="809b5-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="809b5-170">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="809b5-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="809b5-171">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="809b5-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="809b5-172">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="809b5-172">\<binding></span></span>](../../../misc/binding.md)
