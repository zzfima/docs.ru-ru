---
title: '&lt;транспорт&gt; для &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 03e245acd8cb31630d6154e01d934ce6d293f4e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507968"
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a><span data-ttu-id="270e4-102">&lt;транспорт&gt; для &lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="270e4-102">&lt;transport&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="270e4-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="270e4-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="270e4-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="270e4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="270e4-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="270e4-105">\<bindings></span></span>  
<span data-ttu-id="270e4-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="270e4-106">\<netHttpBinding></span></span>  
<span data-ttu-id="270e4-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="270e4-107">\<binding></span></span>  
<span data-ttu-id="270e4-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="270e4-108">\<security></span></span>  
<span data-ttu-id="270e4-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="270e4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270e4-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="270e4-110">Syntax</span></span>  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="270e4-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="270e4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="270e4-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="270e4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="270e4-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="270e4-113">Attributes</span></span>  
  
|<span data-ttu-id="270e4-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="270e4-114">Attribute</span></span>|<span data-ttu-id="270e4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="270e4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="270e4-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="270e4-116">clientCredentialType</span></span>|<span data-ttu-id="270e4-117">— Указывает тип учетных данных, используемых при проверке подлинности клиента с проверкой подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="270e4-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="270e4-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="270e4-118">The default is `None`.</span></span> <span data-ttu-id="270e4-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="270e4-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="270e4-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="270e4-120">proxyCredentialType</span></span>|<span data-ttu-id="270e4-121">— Указывает тип учетных данных, используемых при проверке подлинности клиента из домена с использованием прокси-сервер по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="270e4-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="270e4-122">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="270e4-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="270e4-123">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="270e4-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="270e4-124">realm</span><span class="sxs-lookup"><span data-stu-id="270e4-124">realm</span></span>|<span data-ttu-id="270e4-125">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="270e4-126">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="270e4-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="270e4-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="270e4-127">policyEnforcement</span></span>|<span data-ttu-id="270e4-128">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="270e4-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="270e4-129">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="270e4-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="270e4-130">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="270e4-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="270e4-131">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="270e4-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="270e4-132">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="270e4-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="270e4-133">protectionScenario</span></span>|<span data-ttu-id="270e4-134">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="270e4-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="270e4-135">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="270e4-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="270e4-136">Значение</span><span class="sxs-lookup"><span data-stu-id="270e4-136">Value</span></span>|<span data-ttu-id="270e4-137">Описание</span><span class="sxs-lookup"><span data-stu-id="270e4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="270e4-138">Нет</span><span class="sxs-lookup"><span data-stu-id="270e4-138">None</span></span>|<span data-ttu-id="270e4-139">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="270e4-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="270e4-140">Basic</span><span class="sxs-lookup"><span data-stu-id="270e4-140">Basic</span></span>|<span data-ttu-id="270e4-141">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="270e4-142">Digest</span><span class="sxs-lookup"><span data-stu-id="270e4-142">Digest</span></span>|<span data-ttu-id="270e4-143">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="270e4-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="270e4-144">Ntlm</span></span>|<span data-ttu-id="270e4-145">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="270e4-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="270e4-146">Windows</span><span class="sxs-lookup"><span data-stu-id="270e4-146">Windows</span></span>|<span data-ttu-id="270e4-147">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="270e4-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="270e4-148">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="270e4-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="270e4-149">Значение</span><span class="sxs-lookup"><span data-stu-id="270e4-149">Value</span></span>|<span data-ttu-id="270e4-150">Описание</span><span class="sxs-lookup"><span data-stu-id="270e4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="270e4-151">Нет</span><span class="sxs-lookup"><span data-stu-id="270e4-151">None</span></span>|<span data-ttu-id="270e4-152">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="270e4-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="270e4-153">Basic</span><span class="sxs-lookup"><span data-stu-id="270e4-153">Basic</span></span>|<span data-ttu-id="270e4-154">Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="270e4-155">Digest</span><span class="sxs-lookup"><span data-stu-id="270e4-155">Digest</span></span>|<span data-ttu-id="270e4-156">Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="270e4-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="270e4-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="270e4-157">Ntlm</span></span>|<span data-ttu-id="270e4-158">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="270e4-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="270e4-159">Windows</span><span class="sxs-lookup"><span data-stu-id="270e4-159">Windows</span></span>|<span data-ttu-id="270e4-160">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="270e4-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="270e4-161">Сертификат</span><span class="sxs-lookup"><span data-stu-id="270e4-161">Certificate</span></span>|<span data-ttu-id="270e4-162">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="270e4-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="270e4-163">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="270e4-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="270e4-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="270e4-164">Child Elements</span></span>  
 <span data-ttu-id="270e4-165">Нет</span><span class="sxs-lookup"><span data-stu-id="270e4-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="270e4-166">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="270e4-166">Parent Elements</span></span>  
  
|<span data-ttu-id="270e4-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="270e4-167">Element</span></span>|<span data-ttu-id="270e4-168">Описание</span><span class="sxs-lookup"><span data-stu-id="270e4-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="270e4-169">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="270e4-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="270e4-170">Определяет возможности безопасности для [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="270e4-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="270e4-171">Пример</span><span class="sxs-lookup"><span data-stu-id="270e4-171">Example</span></span>  
 <span data-ttu-id="270e4-172">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="270e4-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="270e4-173">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="270e4-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="270e4-174">См. также</span><span class="sxs-lookup"><span data-stu-id="270e4-174">See Also</span></span>  
 <span data-ttu-id="270e4-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span><span class="sxs-lookup"><span data-stu-id="270e4-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="270e4-176">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="270e4-176">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="270e4-177">Привязки</span><span class="sxs-lookup"><span data-stu-id="270e4-177">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="270e4-178">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="270e4-178">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="270e4-179">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="270e4-179">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="270e4-180">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="270e4-180">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
