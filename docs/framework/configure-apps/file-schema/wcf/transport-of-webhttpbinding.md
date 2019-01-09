---
title: '&lt;transport&gt; для &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 70145678048b3e7843d9d458f80d3d149544447a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149479"
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="0b338-102">&lt;transport&gt; для &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="0b338-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="0b338-103">Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="0b338-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="0b338-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0b338-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b338-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="0b338-105">\<bindings></span></span>  
<span data-ttu-id="0b338-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0b338-106">\<webHttpBinding></span></span>  
<span data-ttu-id="0b338-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0b338-107">\<binding></span></span>  
<span data-ttu-id="0b338-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="0b338-108">\<security></span></span>  
<span data-ttu-id="0b338-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="0b338-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b338-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b338-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
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
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="0b338-111">Тип</span><span class="sxs-lookup"><span data-stu-id="0b338-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b338-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b338-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0b338-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b338-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b338-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b338-114">Attributes</span></span>  
  
|<span data-ttu-id="0b338-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b338-115">Attribute</span></span>|<span data-ttu-id="0b338-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0b338-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="0b338-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0b338-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="0b338-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0b338-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="0b338-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="0b338-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="0b338-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0b338-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="0b338-121">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="0b338-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="0b338-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0b338-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="0b338-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="0b338-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="0b338-125">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="0b338-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="0b338-126">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="0b338-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="0b338-127">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="0b338-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="0b338-128">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="0b338-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="0b338-129">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="0b338-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="0b338-130">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="0b338-131">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0b338-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0b338-132">Значение</span><span class="sxs-lookup"><span data-stu-id="0b338-132">Value</span></span>|<span data-ttu-id="0b338-133">Описание</span><span class="sxs-lookup"><span data-stu-id="0b338-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0b338-134">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="0b338-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="0b338-135">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="0b338-136">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="0b338-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="0b338-137">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="0b338-138">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="0b338-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="0b338-139">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0b338-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="0b338-140">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="0b338-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0b338-141">Значение</span><span class="sxs-lookup"><span data-stu-id="0b338-141">Value</span></span>|<span data-ttu-id="0b338-142">Описание</span><span class="sxs-lookup"><span data-stu-id="0b338-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0b338-143">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="0b338-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="0b338-144">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="0b338-145">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0b338-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="0b338-146">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="0b338-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="0b338-147">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0b338-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b338-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b338-148">Child Elements</span></span>  
 <span data-ttu-id="0b338-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b338-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b338-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b338-150">Parent Elements</span></span>  
  
|<span data-ttu-id="0b338-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b338-151">Element</span></span>|<span data-ttu-id="0b338-152">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b338-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b338-153">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="0b338-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="0b338-154">Представляет возможности безопасности [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0b338-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b338-155">См. также</span><span class="sxs-lookup"><span data-stu-id="0b338-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="0b338-156">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0b338-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="0b338-157">Привязки</span><span class="sxs-lookup"><span data-stu-id="0b338-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0b338-158">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="0b338-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0b338-159">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0b338-159">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="0b338-160">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0b338-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="0b338-161">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="0b338-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
