---
title: <transport> из <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735929"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="52ad9-102">\<transport>  — \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="52ad9-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="52ad9-103">Определяет тип требований безопасности на уровне сообщений для конечной точки, настроенной с помощью [\<netTcpBinding >](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="52ad9-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="52ad9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52ad9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52ad9-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="52ad9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="52ad9-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="52ad9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="52ad9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="52ad9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="52ad9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="52ad9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="52ad9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="52ad9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="52ad9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="52ad9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ad9-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52ad9-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52ad9-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52ad9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="52ad9-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52ad9-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52ad9-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52ad9-114">Attributes</span></span>  
  
|<span data-ttu-id="52ad9-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="52ad9-115">Attribute</span></span>|<span data-ttu-id="52ad9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="52ad9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52ad9-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="52ad9-117">clientCredentialType</span></span>|<span data-ttu-id="52ad9-118">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="52ad9-118">Optional.</span></span> <span data-ttu-id="52ad9-119">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="52ad9-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="52ad9-120">— Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="52ad9-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="52ad9-121">— Этот атрибут имеет тип <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="52ad9-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="52ad9-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="52ad9-122">protectionLevel</span></span>|<span data-ttu-id="52ad9-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="52ad9-123">Optional.</span></span> <span data-ttu-id="52ad9-124">Определяет безопасность на уровне транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="52ad9-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="52ad9-125">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="52ad9-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="52ad9-126">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="52ad9-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="52ad9-127">Значение по умолчанию — `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="52ad9-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="52ad9-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="52ad9-128">sslProtocols</span></span>|<span data-ttu-id="52ad9-129">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="52ad9-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="52ad9-130">Значение по умолчанию&#124;—&#124;TLS Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="52ad9-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="52ad9-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="52ad9-131">policyEnforcement</span></span>|<span data-ttu-id="52ad9-132">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="52ad9-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="52ad9-133">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="52ad9-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="52ad9-134">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="52ad9-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="52ad9-135">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="52ad9-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="52ad9-136">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="52ad9-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="52ad9-137">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="52ad9-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="52ad9-138">значения</span><span class="sxs-lookup"><span data-stu-id="52ad9-138">Value</span></span>|<span data-ttu-id="52ad9-139">Описание</span><span class="sxs-lookup"><span data-stu-id="52ad9-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52ad9-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="52ad9-140">None</span></span>|<span data-ttu-id="52ad9-141">Анонимный клиент.</span><span class="sxs-lookup"><span data-stu-id="52ad9-141">The client is anonymous.</span></span> <span data-ttu-id="52ad9-142">Это требует сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="52ad9-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="52ad9-143">Windows</span><span class="sxs-lookup"><span data-stu-id="52ad9-143">Windows</span></span>|<span data-ttu-id="52ad9-144">Задает проверку подлинности Windows для клиента с использованием согласования SP (согласование Kerberos).</span><span class="sxs-lookup"><span data-stu-id="52ad9-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="52ad9-145">Сертификат</span><span class="sxs-lookup"><span data-stu-id="52ad9-145">Certificate</span></span>|<span data-ttu-id="52ad9-146">Проверка подлинности клиента выполняется с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="52ad9-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="52ad9-147">Это требует согласования SSL и сертификата для службы.</span><span class="sxs-lookup"><span data-stu-id="52ad9-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="52ad9-148">Атрибут protectionLevel</span><span class="sxs-lookup"><span data-stu-id="52ad9-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="52ad9-149">значения</span><span class="sxs-lookup"><span data-stu-id="52ad9-149">Value</span></span>|<span data-ttu-id="52ad9-150">Описание</span><span class="sxs-lookup"><span data-stu-id="52ad9-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52ad9-151">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="52ad9-151">None</span></span>|<span data-ttu-id="52ad9-152">Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="52ad9-152">No protection.</span></span>|  
|<span data-ttu-id="52ad9-153">Sign</span><span class="sxs-lookup"><span data-stu-id="52ad9-153">Sign</span></span>|<span data-ttu-id="52ad9-154">Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="52ad9-154">Messages are signed.</span></span>|  
|<span data-ttu-id="52ad9-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="52ad9-155">EncryptAndSign</span></span>|<span data-ttu-id="52ad9-156">— Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="52ad9-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52ad9-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52ad9-157">Child Elements</span></span>  
 <span data-ttu-id="52ad9-158">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="52ad9-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52ad9-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52ad9-159">Parent Elements</span></span>  
  
|<span data-ttu-id="52ad9-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="52ad9-160">Element</span></span>|<span data-ttu-id="52ad9-161">Описание</span><span class="sxs-lookup"><span data-stu-id="52ad9-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ad9-162">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="52ad9-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="52ad9-163">Указывает возможности безопасности [\<netTcpBinding >](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="52ad9-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ad9-164">Заметки</span><span class="sxs-lookup"><span data-stu-id="52ad9-164">Remarks</span></span>  
 <span data-ttu-id="52ad9-165">Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52ad9-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="52ad9-166">Если этот режим безопасности выбран для какой-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows (Negotiate) или SSL по TCP.</span><span class="sxs-lookup"><span data-stu-id="52ad9-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ad9-167">См. также</span><span class="sxs-lookup"><span data-stu-id="52ad9-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="52ad9-168">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="52ad9-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="52ad9-169">Привязки</span><span class="sxs-lookup"><span data-stu-id="52ad9-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="52ad9-170">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="52ad9-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="52ad9-171">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="52ad9-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="52ad9-172">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="52ad9-172">\<binding></span></span>](bindings.md)
