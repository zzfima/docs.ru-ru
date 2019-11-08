---
title: <transport> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732812"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="abb26-102">\<> транспорта \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="abb26-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="abb26-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="abb26-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="abb26-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="abb26-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="abb26-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="abb26-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="abb26-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="abb26-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="abb26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="abb26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="abb26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="abb26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="abb26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="abb26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="abb26-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="abb26-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abb26-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abb26-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abb26-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="abb26-112">Attributes and Elements</span></span>  
 <span data-ttu-id="abb26-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="abb26-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abb26-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="abb26-114">Attributes</span></span>  
  
|<span data-ttu-id="abb26-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="abb26-115">Attribute</span></span>|<span data-ttu-id="abb26-116">Описание</span><span class="sxs-lookup"><span data-stu-id="abb26-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abb26-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="abb26-117">clientCredentialType</span></span>|<span data-ttu-id="abb26-118">— Указывает тип учетных данных, используемых при проверке подлинности клиента с помощью проверки подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="abb26-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="abb26-119">Значение по умолчанию: `None`.</span><span class="sxs-lookup"><span data-stu-id="abb26-119">The default is `None`.</span></span> <span data-ttu-id="abb26-120">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="abb26-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="abb26-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="abb26-121">proxyCredentialType</span></span>|<span data-ttu-id="abb26-122">— Указывает тип учетных данных, используемых при выполнении проверки подлинности клиента в домене с использованием прокси-сервера через HTTP.</span><span class="sxs-lookup"><span data-stu-id="abb26-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="abb26-123">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="abb26-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="abb26-124">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="abb26-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="abb26-125">realm</span><span class="sxs-lookup"><span data-stu-id="abb26-125">realm</span></span>|<span data-ttu-id="abb26-126">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="abb26-127">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="abb26-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="abb26-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="abb26-128">policyEnforcement</span></span>|<span data-ttu-id="abb26-129">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="abb26-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="abb26-130">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="abb26-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="abb26-131">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="abb26-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="abb26-132">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="abb26-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="abb26-133">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="abb26-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="abb26-134">protectionScenario</span></span>|<span data-ttu-id="abb26-135">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="abb26-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="abb26-136">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="abb26-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="abb26-137">значения</span><span class="sxs-lookup"><span data-stu-id="abb26-137">Value</span></span>|<span data-ttu-id="abb26-138">Описание</span><span class="sxs-lookup"><span data-stu-id="abb26-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abb26-139">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="abb26-139">None</span></span>|<span data-ttu-id="abb26-140">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="abb26-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="abb26-141">Basic</span><span class="sxs-lookup"><span data-stu-id="abb26-141">Basic</span></span>|<span data-ttu-id="abb26-142">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="abb26-143">Digest</span><span class="sxs-lookup"><span data-stu-id="abb26-143">Digest</span></span>|<span data-ttu-id="abb26-144">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="abb26-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="abb26-145">Ntlm</span></span>|<span data-ttu-id="abb26-146">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="abb26-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="abb26-147">Windows</span><span class="sxs-lookup"><span data-stu-id="abb26-147">Windows</span></span>|<span data-ttu-id="abb26-148">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="abb26-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="abb26-149">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="abb26-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="abb26-150">значения</span><span class="sxs-lookup"><span data-stu-id="abb26-150">Value</span></span>|<span data-ttu-id="abb26-151">Описание</span><span class="sxs-lookup"><span data-stu-id="abb26-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abb26-152">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="abb26-152">None</span></span>|<span data-ttu-id="abb26-153">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="abb26-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="abb26-154">Basic</span><span class="sxs-lookup"><span data-stu-id="abb26-154">Basic</span></span>|<span data-ttu-id="abb26-155">Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="abb26-156">Digest</span><span class="sxs-lookup"><span data-stu-id="abb26-156">Digest</span></span>|<span data-ttu-id="abb26-157">Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="abb26-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="abb26-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="abb26-158">Ntlm</span></span>|<span data-ttu-id="abb26-159">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="abb26-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="abb26-160">Windows</span><span class="sxs-lookup"><span data-stu-id="abb26-160">Windows</span></span>|<span data-ttu-id="abb26-161">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="abb26-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="abb26-162">Сертификат</span><span class="sxs-lookup"><span data-stu-id="abb26-162">Certificate</span></span>|<span data-ttu-id="abb26-163">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="abb26-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="abb26-164">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="abb26-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abb26-165">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="abb26-165">Child Elements</span></span>  
 <span data-ttu-id="abb26-166">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="abb26-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abb26-167">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="abb26-167">Parent Elements</span></span>  
  
|<span data-ttu-id="abb26-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="abb26-168">Element</span></span>|<span data-ttu-id="abb26-169">Описание</span><span class="sxs-lookup"><span data-stu-id="abb26-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abb26-170">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="abb26-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="abb26-171">Определяет возможности безопасности для [\<netHttpBinding >](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="abb26-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="abb26-172">Пример</span><span class="sxs-lookup"><span data-stu-id="abb26-172">Example</span></span>  
 <span data-ttu-id="abb26-173">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="abb26-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="abb26-174">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="abb26-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="abb26-175">См. также</span><span class="sxs-lookup"><span data-stu-id="abb26-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="abb26-176">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="abb26-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="abb26-177">Привязки</span><span class="sxs-lookup"><span data-stu-id="abb26-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="abb26-178">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="abb26-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="abb26-179">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="abb26-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="abb26-180">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="abb26-180">\<binding></span></span>](bindings.md)
