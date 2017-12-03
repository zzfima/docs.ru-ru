---
title: "&lt;transport&gt; для &lt;webHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d5c0d17f756c4cca84a48cf6849c4d0945cc2b3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="e289f-102">&lt;transport&gt; для &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e289f-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="e289f-103">Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="e289f-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="e289f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e289f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e289f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e289f-105">\<bindings></span></span>  
<span data-ttu-id="e289f-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e289f-106">\<webHttpBinding></span></span>  
<span data-ttu-id="e289f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e289f-107">\<binding></span></span>  
<span data-ttu-id="e289f-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e289f-108">\<security></span></span>  
<span data-ttu-id="e289f-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="e289f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e289f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e289f-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>  
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
</WebHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="e289f-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e289f-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e289f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e289f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e289f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e289f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e289f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e289f-114">Attributes</span></span>  
  
|<span data-ttu-id="e289f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e289f-115">Attribute</span></span>|<span data-ttu-id="e289f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e289f-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="e289f-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e289f-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="e289f-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e289f-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="e289f-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="e289f-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="e289f-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e289f-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="e289f-121">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="e289f-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="e289f-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e289f-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="e289f-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="e289f-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="e289f-125">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e289f-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="e289f-126">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="e289f-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e289f-127">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="e289f-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e289f-128">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="e289f-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e289f-129">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="e289f-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e289f-130">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e289f-131">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e289f-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e289f-132">Значение</span><span class="sxs-lookup"><span data-stu-id="e289f-132">Value</span></span>|<span data-ttu-id="e289f-133">Описание</span><span class="sxs-lookup"><span data-stu-id="e289f-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e289f-134">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e289f-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="e289f-135">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="e289f-136">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="e289f-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="e289f-137">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="e289f-138">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="e289f-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="e289f-139">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e289f-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e289f-140">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e289f-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e289f-141">Значение</span><span class="sxs-lookup"><span data-stu-id="e289f-141">Value</span></span>|<span data-ttu-id="e289f-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e289f-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e289f-143">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e289f-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="e289f-144">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="e289f-145">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e289f-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="e289f-146">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="e289f-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="e289f-147">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e289f-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e289f-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e289f-148">Child Elements</span></span>  
 <span data-ttu-id="e289f-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e289f-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e289f-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e289f-150">Parent Elements</span></span>  
  
|<span data-ttu-id="e289f-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="e289f-151">Element</span></span>|<span data-ttu-id="e289f-152">Описание</span><span class="sxs-lookup"><span data-stu-id="e289f-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e289f-153">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e289f-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="e289f-154">Представляет функциональные возможности безопасности [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="e289f-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e289f-155">См. также</span><span class="sxs-lookup"><span data-stu-id="e289f-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="e289f-156">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e289f-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e289f-157">Привязки</span><span class="sxs-lookup"><span data-stu-id="e289f-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e289f-158">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e289f-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e289f-159">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="e289f-159">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e289f-160">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e289f-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="e289f-161">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="e289f-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
