---
title: <transport> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: 5d1ef059f8fde7c41e333571d1c025a9c0c7e03f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788392"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="f8b7c-102">\<Транспорт > из \<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="f8b7c-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="f8b7c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8b7c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8b7c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-105">\<bindings></span></span>  
<span data-ttu-id="f8b7c-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="f8b7c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-107">\<binding></span></span>  
<span data-ttu-id="f8b7c-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-108">\<security></span></span>  
<span data-ttu-id="f8b7c-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b7c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8b7c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8b7c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8b7c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f8b7c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8b7c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8b7c-113">Attributes</span></span>  
  
|<span data-ttu-id="f8b7c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f8b7c-114">Attribute</span></span>|<span data-ttu-id="f8b7c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f8b7c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8b7c-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f8b7c-116">clientCredentialType</span></span>|<span data-ttu-id="f8b7c-117">— Указывает тип учетных данных, используемых при проверке подлинности клиента с проверкой подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="f8b7c-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-118">The default is `None`.</span></span> <span data-ttu-id="f8b7c-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="f8b7c-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f8b7c-120">proxyCredentialType</span></span>|<span data-ttu-id="f8b7c-121">— Указывает тип учетных данных, используемых при проверке подлинности клиента из домена с использованием прокси-сервер по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="f8b7c-122">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="f8b7c-123">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="f8b7c-124">realm</span><span class="sxs-lookup"><span data-stu-id="f8b7c-124">realm</span></span>|<span data-ttu-id="f8b7c-125">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="f8b7c-126">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="f8b7c-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="f8b7c-127">policyEnforcement</span></span>|<span data-ttu-id="f8b7c-128">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f8b7c-129">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="f8b7c-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f8b7c-130">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f8b7c-131">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f8b7c-132">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="f8b7c-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="f8b7c-133">protectionScenario</span></span>|<span data-ttu-id="f8b7c-134">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f8b7c-135">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f8b7c-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f8b7c-136">Значение</span><span class="sxs-lookup"><span data-stu-id="f8b7c-136">Value</span></span>|<span data-ttu-id="f8b7c-137">Описание</span><span class="sxs-lookup"><span data-stu-id="f8b7c-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8b7c-138">Нет</span><span class="sxs-lookup"><span data-stu-id="f8b7c-138">None</span></span>|<span data-ttu-id="f8b7c-139">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="f8b7c-140">Basic</span><span class="sxs-lookup"><span data-stu-id="f8b7c-140">Basic</span></span>|<span data-ttu-id="f8b7c-141">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="f8b7c-142">Digest</span><span class="sxs-lookup"><span data-stu-id="f8b7c-142">Digest</span></span>|<span data-ttu-id="f8b7c-143">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="f8b7c-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f8b7c-144">Ntlm</span></span>|<span data-ttu-id="f8b7c-145">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="f8b7c-146">Windows</span><span class="sxs-lookup"><span data-stu-id="f8b7c-146">Windows</span></span>|<span data-ttu-id="f8b7c-147">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="f8b7c-148">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f8b7c-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f8b7c-149">Значение</span><span class="sxs-lookup"><span data-stu-id="f8b7c-149">Value</span></span>|<span data-ttu-id="f8b7c-150">Описание</span><span class="sxs-lookup"><span data-stu-id="f8b7c-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8b7c-151">Нет</span><span class="sxs-lookup"><span data-stu-id="f8b7c-151">None</span></span>|<span data-ttu-id="f8b7c-152">-Сообщения не защищены во время передачи.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="f8b7c-153">Basic</span><span class="sxs-lookup"><span data-stu-id="f8b7c-153">Basic</span></span>|<span data-ttu-id="f8b7c-154">Задает обычную проверку подлинности, как определено документом RFC 2617 – проверка подлинности HTTP: Основные и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="f8b7c-155">Digest</span><span class="sxs-lookup"><span data-stu-id="f8b7c-155">Digest</span></span>|<span data-ttu-id="f8b7c-156">Задает дайджест-проверки подлинности, как определено документом RFC 2617 – проверка подлинности HTTP: Основные и дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="f8b7c-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f8b7c-157">Ntlm</span></span>|<span data-ttu-id="f8b7c-158">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="f8b7c-159">Windows</span><span class="sxs-lookup"><span data-stu-id="f8b7c-159">Windows</span></span>|<span data-ttu-id="f8b7c-160">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="f8b7c-161">Сертификат</span><span class="sxs-lookup"><span data-stu-id="f8b7c-161">Certificate</span></span>|<span data-ttu-id="f8b7c-162">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="f8b7c-163">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8b7c-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8b7c-164">Child Elements</span></span>  
 <span data-ttu-id="f8b7c-165">Нет</span><span class="sxs-lookup"><span data-stu-id="f8b7c-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8b7c-166">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8b7c-166">Parent Elements</span></span>  
  
|<span data-ttu-id="f8b7c-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8b7c-167">Element</span></span>|<span data-ttu-id="f8b7c-168">Описание</span><span class="sxs-lookup"><span data-stu-id="f8b7c-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8b7c-169">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="f8b7c-170">Определяет возможности безопасности для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f8b7c-170">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8b7c-171">Пример</span><span class="sxs-lookup"><span data-stu-id="f8b7c-171">Example</span></span>  
 <span data-ttu-id="f8b7c-172">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="f8b7c-173">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8b7c-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8b7c-174">См. также</span><span class="sxs-lookup"><span data-stu-id="f8b7c-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="f8b7c-175">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f8b7c-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f8b7c-176">Привязки</span><span class="sxs-lookup"><span data-stu-id="f8b7c-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f8b7c-177">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f8b7c-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f8b7c-178">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f8b7c-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f8b7c-179">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f8b7c-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
