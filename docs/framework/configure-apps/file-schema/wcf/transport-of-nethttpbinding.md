---
title: <transport> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 521aaf3913a1d30d10a674b71d4d98affcabc296
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399343"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="7d0f0-102">\<транспортное \<> из NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7d0f0-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="7d0f0-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="7d0f0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d0f0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d0f0-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d0f0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d0f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7d0f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7d0f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7d0f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="7d0f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="7d0f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7d0f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7d0f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="7d0f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="7d0f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0f0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d0f0-111">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d0f0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7d0f0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7d0f0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d0f0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d0f0-114">Attributes</span></span>  
  
|<span data-ttu-id="7d0f0-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7d0f0-115">Attribute</span></span>|<span data-ttu-id="7d0f0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7d0f0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d0f0-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7d0f0-117">clientCredentialType</span></span>|<span data-ttu-id="7d0f0-118">— Указывает тип учетных данных, используемых при проверке подлинности клиента с помощью проверки подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="7d0f0-119">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-119">The default is `None`.</span></span> <span data-ttu-id="7d0f0-120">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="7d0f0-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="7d0f0-121">proxyCredentialType</span></span>|<span data-ttu-id="7d0f0-122">— Указывает тип учетных данных, используемых при выполнении проверки подлинности клиента в домене с использованием прокси-сервера через HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="7d0f0-123">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="7d0f0-124">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="7d0f0-125">realm</span><span class="sxs-lookup"><span data-stu-id="7d0f0-125">realm</span></span>|<span data-ttu-id="7d0f0-126">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="7d0f0-127">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="7d0f0-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="7d0f0-128">policyEnforcement</span></span>|<span data-ttu-id="7d0f0-129">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7d0f0-130">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="7d0f0-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7d0f0-131">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7d0f0-132">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7d0f0-133">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="7d0f0-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="7d0f0-134">protectionScenario</span></span>|<span data-ttu-id="7d0f0-135">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7d0f0-136">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7d0f0-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7d0f0-137">Значение</span><span class="sxs-lookup"><span data-stu-id="7d0f0-137">Value</span></span>|<span data-ttu-id="7d0f0-138">Описание</span><span class="sxs-lookup"><span data-stu-id="7d0f0-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d0f0-139">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7d0f0-139">None</span></span>|<span data-ttu-id="7d0f0-140">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7d0f0-141">Стандартная</span><span class="sxs-lookup"><span data-stu-id="7d0f0-141">Basic</span></span>|<span data-ttu-id="7d0f0-142">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="7d0f0-143">Digest</span><span class="sxs-lookup"><span data-stu-id="7d0f0-143">Digest</span></span>|<span data-ttu-id="7d0f0-144">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="7d0f0-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7d0f0-145">Ntlm</span></span>|<span data-ttu-id="7d0f0-146">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="7d0f0-147">Windows</span><span class="sxs-lookup"><span data-stu-id="7d0f0-147">Windows</span></span>|<span data-ttu-id="7d0f0-148">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7d0f0-149">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="7d0f0-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7d0f0-150">Значение</span><span class="sxs-lookup"><span data-stu-id="7d0f0-150">Value</span></span>|<span data-ttu-id="7d0f0-151">Описание</span><span class="sxs-lookup"><span data-stu-id="7d0f0-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d0f0-152">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7d0f0-152">None</span></span>|<span data-ttu-id="7d0f0-153">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7d0f0-154">Стандартная</span><span class="sxs-lookup"><span data-stu-id="7d0f0-154">Basic</span></span>|<span data-ttu-id="7d0f0-155">Указывает обычную проверку подлинности, определенную в стандарте RFC 2617 — проверка подлинности HTTP: Обычная и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="7d0f0-156">Digest</span><span class="sxs-lookup"><span data-stu-id="7d0f0-156">Digest</span></span>|<span data-ttu-id="7d0f0-157">Указывает дайджест-проверку подлинности, как определено в RFC 2617 — проверка подлинности HTTP: Обычная и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="7d0f0-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7d0f0-158">Ntlm</span></span>|<span data-ttu-id="7d0f0-159">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="7d0f0-160">Windows</span><span class="sxs-lookup"><span data-stu-id="7d0f0-160">Windows</span></span>|<span data-ttu-id="7d0f0-161">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="7d0f0-162">Сертификат</span><span class="sxs-lookup"><span data-stu-id="7d0f0-162">Certificate</span></span>|<span data-ttu-id="7d0f0-163">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="7d0f0-164">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d0f0-165">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d0f0-165">Child Elements</span></span>  
 <span data-ttu-id="7d0f0-166">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7d0f0-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d0f0-167">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d0f0-167">Parent Elements</span></span>  
  
|<span data-ttu-id="7d0f0-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d0f0-168">Element</span></span>|<span data-ttu-id="7d0f0-169">Описание</span><span class="sxs-lookup"><span data-stu-id="7d0f0-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d0f0-170">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="7d0f0-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="7d0f0-171">Определяет возможности безопасности для [ \<> NetHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7d0f0-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d0f0-172">Пример</span><span class="sxs-lookup"><span data-stu-id="7d0f0-172">Example</span></span>  
 <span data-ttu-id="7d0f0-173">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="7d0f0-174">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d0f0-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="7d0f0-175">См. также</span><span class="sxs-lookup"><span data-stu-id="7d0f0-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="7d0f0-176">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7d0f0-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7d0f0-177">Привязки</span><span class="sxs-lookup"><span data-stu-id="7d0f0-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7d0f0-178">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7d0f0-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7d0f0-179">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7d0f0-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7d0f0-180">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7d0f0-180">\<binding></span></span>](../../../misc/binding.md)
