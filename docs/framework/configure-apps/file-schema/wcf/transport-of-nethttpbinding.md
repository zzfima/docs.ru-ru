---
title: '&lt;транспорт&gt; для &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 3110a93d224ee2be078727df65b92e9987445c43
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151297"
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a><span data-ttu-id="b3962-102">&lt;транспорт&gt; для &lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b3962-102">&lt;transport&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="b3962-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3962-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="b3962-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b3962-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b3962-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b3962-105">\<bindings></span></span>  
<span data-ttu-id="b3962-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b3962-106">\<netHttpBinding></span></span>  
<span data-ttu-id="b3962-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b3962-107">\<binding></span></span>  
<span data-ttu-id="b3962-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b3962-108">\<security></span></span>  
<span data-ttu-id="b3962-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="b3962-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3962-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3962-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3962-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3962-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3962-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3962-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3962-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3962-113">Attributes</span></span>  
  
|<span data-ttu-id="b3962-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3962-114">Attribute</span></span>|<span data-ttu-id="b3962-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b3962-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3962-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="b3962-116">clientCredentialType</span></span>|<span data-ttu-id="b3962-117">— Указывает тип учетных данных, используемых при проверке подлинности клиента с проверкой подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3962-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="b3962-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="b3962-118">The default is `None`.</span></span> <span data-ttu-id="b3962-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b3962-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="b3962-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="b3962-120">proxyCredentialType</span></span>|<span data-ttu-id="b3962-121">— Указывает тип учетных данных, используемых при проверке подлинности клиента из домена с использованием прокси-сервер по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3962-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="b3962-122">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="b3962-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="b3962-123">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b3962-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="b3962-124">realm</span><span class="sxs-lookup"><span data-stu-id="b3962-124">realm</span></span>|<span data-ttu-id="b3962-125">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="b3962-126">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="b3962-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="b3962-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="b3962-127">policyEnforcement</span></span>|<span data-ttu-id="b3962-128">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="b3962-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="b3962-129">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="b3962-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="b3962-130">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="b3962-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="b3962-131">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="b3962-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="b3962-132">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="b3962-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="b3962-133">protectionScenario</span></span>|<span data-ttu-id="b3962-134">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="b3962-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="b3962-135">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="b3962-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b3962-136">Значение</span><span class="sxs-lookup"><span data-stu-id="b3962-136">Value</span></span>|<span data-ttu-id="b3962-137">Описание</span><span class="sxs-lookup"><span data-stu-id="b3962-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3962-138">Нет</span><span class="sxs-lookup"><span data-stu-id="b3962-138">None</span></span>|<span data-ttu-id="b3962-139">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="b3962-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="b3962-140">Basic</span><span class="sxs-lookup"><span data-stu-id="b3962-140">Basic</span></span>|<span data-ttu-id="b3962-141">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="b3962-142">Digest</span><span class="sxs-lookup"><span data-stu-id="b3962-142">Digest</span></span>|<span data-ttu-id="b3962-143">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="b3962-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b3962-144">Ntlm</span></span>|<span data-ttu-id="b3962-145">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b3962-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="b3962-146">Windows</span><span class="sxs-lookup"><span data-stu-id="b3962-146">Windows</span></span>|<span data-ttu-id="b3962-147">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b3962-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="b3962-148">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="b3962-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b3962-149">Значение</span><span class="sxs-lookup"><span data-stu-id="b3962-149">Value</span></span>|<span data-ttu-id="b3962-150">Описание</span><span class="sxs-lookup"><span data-stu-id="b3962-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3962-151">Нет</span><span class="sxs-lookup"><span data-stu-id="b3962-151">None</span></span>|<span data-ttu-id="b3962-152">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="b3962-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="b3962-153">Basic</span><span class="sxs-lookup"><span data-stu-id="b3962-153">Basic</span></span>|<span data-ttu-id="b3962-154">Задает обычную проверку подлинности, как определено документом RFC 2617 – проверка подлинности HTTP: Основные и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="b3962-155">Digest</span><span class="sxs-lookup"><span data-stu-id="b3962-155">Digest</span></span>|<span data-ttu-id="b3962-156">Задает дайджест-проверки подлинности, как определено документом RFC 2617 – проверка подлинности HTTP: Основные и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3962-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="b3962-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b3962-157">Ntlm</span></span>|<span data-ttu-id="b3962-158">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b3962-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="b3962-159">Windows</span><span class="sxs-lookup"><span data-stu-id="b3962-159">Windows</span></span>|<span data-ttu-id="b3962-160">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b3962-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="b3962-161">Сертификат</span><span class="sxs-lookup"><span data-stu-id="b3962-161">Certificate</span></span>|<span data-ttu-id="b3962-162">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="b3962-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="b3962-163">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="b3962-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3962-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3962-164">Child Elements</span></span>  
 <span data-ttu-id="b3962-165">Нет</span><span class="sxs-lookup"><span data-stu-id="b3962-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3962-166">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3962-166">Parent Elements</span></span>  
  
|<span data-ttu-id="b3962-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3962-167">Element</span></span>|<span data-ttu-id="b3962-168">Описание</span><span class="sxs-lookup"><span data-stu-id="b3962-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3962-169">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b3962-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="b3962-170">Определяет возможности безопасности для [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b3962-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b3962-171">Пример</span><span class="sxs-lookup"><span data-stu-id="b3962-171">Example</span></span>  
 <span data-ttu-id="b3962-172">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="b3962-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="b3962-173">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3962-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b3962-174">См. также</span><span class="sxs-lookup"><span data-stu-id="b3962-174">See Also</span></span>  
 <span data-ttu-id="b3962-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span><span class="sxs-lookup"><span data-stu-id="b3962-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="b3962-176">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b3962-176">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b3962-177">Привязки</span><span class="sxs-lookup"><span data-stu-id="b3962-177">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b3962-178">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b3962-178">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b3962-179">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b3962-179">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="b3962-180">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b3962-180">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
