---
title: <transport> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 98cdaa86441f91552c7133d8e5694f88019a6dbf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399284"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="0052b-102">\<транспортное \<> из WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0052b-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="0052b-103">Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="0052b-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="0052b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0052b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0052b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0052b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0052b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0052b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0052b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0052b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="0052b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="0052b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0052b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0052b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="0052b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="0052b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0052b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0052b-111">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="0052b-112">Тип</span><span class="sxs-lookup"><span data-stu-id="0052b-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0052b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0052b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0052b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0052b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0052b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0052b-115">Attributes</span></span>  
  
|<span data-ttu-id="0052b-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0052b-116">Attribute</span></span>|<span data-ttu-id="0052b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0052b-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="0052b-118">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="0052b-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="0052b-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0052b-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="0052b-120">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="0052b-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="0052b-121">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0052b-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="0052b-122">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="0052b-123">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="0052b-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0052b-124">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="0052b-125">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="0052b-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="0052b-126">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="0052b-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="0052b-127">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="0052b-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="0052b-128">1.  Never - политика никогда не применяется (расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="0052b-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="0052b-129">2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="0052b-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="0052b-130">3.  Always - политика применяется всегда.</span><span class="sxs-lookup"><span data-stu-id="0052b-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="0052b-131">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="0052b-132">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0052b-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0052b-133">Значение</span><span class="sxs-lookup"><span data-stu-id="0052b-133">Value</span></span>|<span data-ttu-id="0052b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="0052b-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0052b-135">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="0052b-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="0052b-136">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="0052b-137">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="0052b-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="0052b-138">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="0052b-139">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="0052b-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="0052b-140">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0052b-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="0052b-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="0052b-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0052b-142">Значение</span><span class="sxs-lookup"><span data-stu-id="0052b-142">Value</span></span>|<span data-ttu-id="0052b-143">Описание</span><span class="sxs-lookup"><span data-stu-id="0052b-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0052b-144">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="0052b-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="0052b-145">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="0052b-146">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0052b-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="0052b-147">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="0052b-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="0052b-148">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0052b-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0052b-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0052b-149">Child Elements</span></span>  
 <span data-ttu-id="0052b-150">Нет.</span><span class="sxs-lookup"><span data-stu-id="0052b-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0052b-151">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0052b-151">Parent Elements</span></span>  
  
|<span data-ttu-id="0052b-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="0052b-152">Element</span></span>|<span data-ttu-id="0052b-153">Описание</span><span class="sxs-lookup"><span data-stu-id="0052b-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0052b-154">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="0052b-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="0052b-155">Представляет возможности [ \<](wshttpbinding.md) безопасности элемента привязки wsHttpBinding >.</span><span class="sxs-lookup"><span data-stu-id="0052b-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0052b-156">См. также</span><span class="sxs-lookup"><span data-stu-id="0052b-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="0052b-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0052b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0052b-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="0052b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0052b-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="0052b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0052b-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0052b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0052b-161">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0052b-161">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="0052b-162">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="0052b-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
