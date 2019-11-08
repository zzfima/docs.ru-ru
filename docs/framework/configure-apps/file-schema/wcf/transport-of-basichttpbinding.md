---
title: <transport> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: c563339e4f854cc4e60f92dd5b8c0b39112dc000
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736119"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="190c7-102">\<> транспорта \<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="190c7-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="190c7-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="190c7-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="190c7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="190c7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="190c7-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="190c7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="190c7-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="190c7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="190c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BasicHttpBinding**](basichttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="190c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="190c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="190c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="190c7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="190c7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="190c7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="190c7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="190c7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="190c7-111">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="190c7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="190c7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="190c7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="190c7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="190c7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="190c7-114">Attributes</span></span>  
  
|<span data-ttu-id="190c7-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="190c7-115">Attribute</span></span>|<span data-ttu-id="190c7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="190c7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="190c7-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="190c7-117">clientCredentialType</span></span>|<span data-ttu-id="190c7-118">— Указывает тип учетных данных, используемых при проверке подлинности клиента с помощью проверки подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="190c7-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="190c7-119">Значение по умолчанию: `None`.</span><span class="sxs-lookup"><span data-stu-id="190c7-119">The default is `None`.</span></span> <span data-ttu-id="190c7-120">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="190c7-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="190c7-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="190c7-121">proxyCredentialType</span></span>|<span data-ttu-id="190c7-122">— Указывает тип учетных данных, используемых при выполнении проверки подлинности клиента в домене с использованием прокси-сервера через HTTP.</span><span class="sxs-lookup"><span data-stu-id="190c7-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="190c7-123">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="190c7-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="190c7-124">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="190c7-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="190c7-125">realm</span><span class="sxs-lookup"><span data-stu-id="190c7-125">realm</span></span>|<span data-ttu-id="190c7-126">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="190c7-127">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="190c7-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="190c7-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="190c7-128">policyEnforcement</span></span>|<span data-ttu-id="190c7-129">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="190c7-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="190c7-130">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="190c7-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="190c7-131">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="190c7-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="190c7-132">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="190c7-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="190c7-133">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="190c7-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="190c7-134">protectionScenario</span></span>|<span data-ttu-id="190c7-135">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="190c7-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="190c7-136">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="190c7-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="190c7-137">значения</span><span class="sxs-lookup"><span data-stu-id="190c7-137">Value</span></span>|<span data-ttu-id="190c7-138">Описание</span><span class="sxs-lookup"><span data-stu-id="190c7-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="190c7-139">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="190c7-139">None</span></span>|<span data-ttu-id="190c7-140">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="190c7-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="190c7-141">Basic</span><span class="sxs-lookup"><span data-stu-id="190c7-141">Basic</span></span>|<span data-ttu-id="190c7-142">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="190c7-143">Digest</span><span class="sxs-lookup"><span data-stu-id="190c7-143">Digest</span></span>|<span data-ttu-id="190c7-144">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="190c7-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="190c7-145">Ntlm</span></span>|<span data-ttu-id="190c7-146">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="190c7-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="190c7-147">Windows</span><span class="sxs-lookup"><span data-stu-id="190c7-147">Windows</span></span>|<span data-ttu-id="190c7-148">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="190c7-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="190c7-149">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="190c7-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="190c7-150">значения</span><span class="sxs-lookup"><span data-stu-id="190c7-150">Value</span></span>|<span data-ttu-id="190c7-151">Описание</span><span class="sxs-lookup"><span data-stu-id="190c7-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="190c7-152">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="190c7-152">None</span></span>|<span data-ttu-id="190c7-153">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="190c7-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="190c7-154">Basic</span><span class="sxs-lookup"><span data-stu-id="190c7-154">Basic</span></span>|<span data-ttu-id="190c7-155">Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="190c7-156">Digest</span><span class="sxs-lookup"><span data-stu-id="190c7-156">Digest</span></span>|<span data-ttu-id="190c7-157">Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="190c7-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="190c7-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="190c7-158">Ntlm</span></span>|<span data-ttu-id="190c7-159">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="190c7-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="190c7-160">Windows</span><span class="sxs-lookup"><span data-stu-id="190c7-160">Windows</span></span>|<span data-ttu-id="190c7-161">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="190c7-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="190c7-162">Сертификат</span><span class="sxs-lookup"><span data-stu-id="190c7-162">Certificate</span></span>|<span data-ttu-id="190c7-163">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="190c7-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="190c7-164">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="190c7-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="190c7-165">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="190c7-165">Child Elements</span></span>  
 <span data-ttu-id="190c7-166">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="190c7-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="190c7-167">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="190c7-167">Parent Elements</span></span>  
  
|<span data-ttu-id="190c7-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="190c7-168">Element</span></span>|<span data-ttu-id="190c7-169">Описание</span><span class="sxs-lookup"><span data-stu-id="190c7-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="190c7-170">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="190c7-170">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="190c7-171">Определяет возможности безопасности для [\<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="190c7-171">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="190c7-172">Пример</span><span class="sxs-lookup"><span data-stu-id="190c7-172">Example</span></span>  
 <span data-ttu-id="190c7-173">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="190c7-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="190c7-174">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="190c7-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="190c7-175">См. также</span><span class="sxs-lookup"><span data-stu-id="190c7-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="190c7-176">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="190c7-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="190c7-177">Привязки</span><span class="sxs-lookup"><span data-stu-id="190c7-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="190c7-178">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="190c7-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="190c7-179">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="190c7-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="190c7-180">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="190c7-180">\<binding></span></span>](bindings.md)
