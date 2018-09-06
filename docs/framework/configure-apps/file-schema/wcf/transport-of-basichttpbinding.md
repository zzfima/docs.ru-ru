---
title: '&lt;transport&gt; для &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: f3f9ad2c8b587a87abea7dc22abb98fdfb6ea77e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864606"
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a><span data-ttu-id="9854d-102">&lt;transport&gt; для &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9854d-102">&lt;transport&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="9854d-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="9854d-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="9854d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9854d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9854d-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9854d-105">\<bindings></span></span>  
<span data-ttu-id="9854d-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9854d-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="9854d-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9854d-107">\<binding></span></span>  
<span data-ttu-id="9854d-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9854d-108">\<security></span></span>  
<span data-ttu-id="9854d-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="9854d-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9854d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9854d-110">Syntax</span></span>  
  
```xml  
<basicHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9854d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9854d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9854d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9854d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9854d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9854d-113">Attributes</span></span>  
  
|<span data-ttu-id="9854d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9854d-114">Attribute</span></span>|<span data-ttu-id="9854d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9854d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9854d-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9854d-116">clientCredentialType</span></span>|<span data-ttu-id="9854d-117">— Указывает тип учетных данных, используемых при проверке подлинности клиента с проверкой подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="9854d-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="9854d-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="9854d-118">The default is `None`.</span></span> <span data-ttu-id="9854d-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9854d-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="9854d-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="9854d-120">proxyCredentialType</span></span>|<span data-ttu-id="9854d-121">— Указывает тип учетных данных, используемых при проверке подлинности клиента из домена с использованием прокси-сервер по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="9854d-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="9854d-122">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="9854d-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="9854d-123">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9854d-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="9854d-124">realm</span><span class="sxs-lookup"><span data-stu-id="9854d-124">realm</span></span>|<span data-ttu-id="9854d-125">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="9854d-126">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="9854d-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="9854d-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="9854d-127">policyEnforcement</span></span>|<span data-ttu-id="9854d-128">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="9854d-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9854d-129">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="9854d-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9854d-130">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="9854d-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9854d-131">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="9854d-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9854d-132">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="9854d-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="9854d-133">protectionScenario</span></span>|<span data-ttu-id="9854d-134">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="9854d-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9854d-135">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9854d-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9854d-136">Значение</span><span class="sxs-lookup"><span data-stu-id="9854d-136">Value</span></span>|<span data-ttu-id="9854d-137">Описание</span><span class="sxs-lookup"><span data-stu-id="9854d-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9854d-138">Нет</span><span class="sxs-lookup"><span data-stu-id="9854d-138">None</span></span>|<span data-ttu-id="9854d-139">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="9854d-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="9854d-140">Basic</span><span class="sxs-lookup"><span data-stu-id="9854d-140">Basic</span></span>|<span data-ttu-id="9854d-141">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="9854d-142">Digest</span><span class="sxs-lookup"><span data-stu-id="9854d-142">Digest</span></span>|<span data-ttu-id="9854d-143">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="9854d-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9854d-144">Ntlm</span></span>|<span data-ttu-id="9854d-145">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9854d-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="9854d-146">Windows</span><span class="sxs-lookup"><span data-stu-id="9854d-146">Windows</span></span>|<span data-ttu-id="9854d-147">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9854d-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9854d-148">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="9854d-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9854d-149">Значение</span><span class="sxs-lookup"><span data-stu-id="9854d-149">Value</span></span>|<span data-ttu-id="9854d-150">Описание</span><span class="sxs-lookup"><span data-stu-id="9854d-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9854d-151">Нет</span><span class="sxs-lookup"><span data-stu-id="9854d-151">None</span></span>|<span data-ttu-id="9854d-152">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="9854d-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="9854d-153">Basic</span><span class="sxs-lookup"><span data-stu-id="9854d-153">Basic</span></span>|<span data-ttu-id="9854d-154">Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="9854d-155">Digest</span><span class="sxs-lookup"><span data-stu-id="9854d-155">Digest</span></span>|<span data-ttu-id="9854d-156">Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="9854d-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="9854d-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9854d-157">Ntlm</span></span>|<span data-ttu-id="9854d-158">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9854d-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="9854d-159">Windows</span><span class="sxs-lookup"><span data-stu-id="9854d-159">Windows</span></span>|<span data-ttu-id="9854d-160">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9854d-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="9854d-161">Сертификат</span><span class="sxs-lookup"><span data-stu-id="9854d-161">Certificate</span></span>|<span data-ttu-id="9854d-162">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="9854d-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="9854d-163">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="9854d-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9854d-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9854d-164">Child Elements</span></span>  
 <span data-ttu-id="9854d-165">Нет</span><span class="sxs-lookup"><span data-stu-id="9854d-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9854d-166">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9854d-166">Parent Elements</span></span>  
  
|<span data-ttu-id="9854d-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="9854d-167">Element</span></span>|<span data-ttu-id="9854d-168">Описание</span><span class="sxs-lookup"><span data-stu-id="9854d-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9854d-169">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9854d-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="9854d-170">Определяет возможности безопасности для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9854d-170">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9854d-171">Пример</span><span class="sxs-lookup"><span data-stu-id="9854d-171">Example</span></span>  
 <span data-ttu-id="9854d-172">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="9854d-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="9854d-173">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="9854d-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9854d-174">См. также</span><span class="sxs-lookup"><span data-stu-id="9854d-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="9854d-175">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9854d-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9854d-176">Привязки</span><span class="sxs-lookup"><span data-stu-id="9854d-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9854d-177">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="9854d-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9854d-178">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="9854d-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9854d-179">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9854d-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
