---
title: '&lt;transport&gt; для &lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 771866a83d54ca9e4fc7f3ed6d351b4a6c755b4c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483857"
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a><span data-ttu-id="c1efd-102">&lt;transport&gt; для &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c1efd-102">&lt;transport&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="c1efd-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="c1efd-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="c1efd-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c1efd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c1efd-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c1efd-105">\<bindings></span></span>  
<span data-ttu-id="c1efd-106">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c1efd-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="c1efd-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c1efd-107">\<binding></span></span>  
<span data-ttu-id="c1efd-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c1efd-108">\<security></span></span>  
<span data-ttu-id="c1efd-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="c1efd-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1efd-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1efd-110">Syntax</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding>  
        <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport  
            clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"  
            proxyCredentialType="Basic|Digest|None|Ntlm|Windows"  
            realm="string" />  
                <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always" protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                </extendedProtecutionPolicy>  
            </transport>  
        </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="c1efd-111">Тип</span><span class="sxs-lookup"><span data-stu-id="c1efd-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1efd-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c1efd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c1efd-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c1efd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1efd-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c1efd-114">Attributes</span></span>  
  
|<span data-ttu-id="c1efd-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c1efd-115">Attribute</span></span>|<span data-ttu-id="c1efd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c1efd-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="c1efd-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="c1efd-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="c1efd-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c1efd-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="c1efd-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="c1efd-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="c1efd-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c1efd-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="c1efd-121">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="c1efd-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c1efd-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="c1efd-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="c1efd-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="c1efd-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="c1efd-125">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c1efd-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="c1efd-126">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="c1efd-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="c1efd-127">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="c1efd-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="c1efd-128">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="c1efd-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="c1efd-129">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="c1efd-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="c1efd-130">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="c1efd-131">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="c1efd-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="c1efd-132">Значение</span><span class="sxs-lookup"><span data-stu-id="c1efd-132">Value</span></span>|<span data-ttu-id="c1efd-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c1efd-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="c1efd-134">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c1efd-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="c1efd-135">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="c1efd-136">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="c1efd-137">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="c1efd-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="c1efd-138">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c1efd-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="c1efd-139">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="c1efd-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="c1efd-140">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="c1efd-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="c1efd-141">Значение</span><span class="sxs-lookup"><span data-stu-id="c1efd-141">Value</span></span>|<span data-ttu-id="c1efd-142">Описание</span><span class="sxs-lookup"><span data-stu-id="c1efd-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="c1efd-143">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c1efd-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="c1efd-144">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="c1efd-145">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c1efd-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="c1efd-146">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="c1efd-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="c1efd-147">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c1efd-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="c1efd-148">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="c1efd-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1efd-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c1efd-149">Child Elements</span></span>  
 <span data-ttu-id="c1efd-150">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c1efd-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1efd-151">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c1efd-151">Parent Elements</span></span>  
  
|<span data-ttu-id="c1efd-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1efd-152">Element</span></span>|<span data-ttu-id="c1efd-153">Описание</span><span class="sxs-lookup"><span data-stu-id="c1efd-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1efd-154">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c1efd-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="c1efd-155">Представляет возможности безопасности [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c1efd-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1efd-156">См. также</span><span class="sxs-lookup"><span data-stu-id="c1efd-156">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="c1efd-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c1efd-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c1efd-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="c1efd-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c1efd-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c1efd-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c1efd-160">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="c1efd-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c1efd-161">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c1efd-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
