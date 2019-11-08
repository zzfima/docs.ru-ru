---
title: <transport> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732786"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="f5f11-102">\<> транспорта \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f5f11-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="f5f11-103">Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5f11-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="f5f11-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5f11-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5f11-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f5f11-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f5f11-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="f5f11-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="f5f11-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f5f11-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="f5f11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="f5f11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f5f11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f5f11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="f5f11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="f5f11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5f11-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5f11-111">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="f5f11-112">Type</span><span class="sxs-lookup"><span data-stu-id="f5f11-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5f11-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f5f11-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f5f11-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f5f11-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5f11-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5f11-115">Attributes</span></span>  
  
|<span data-ttu-id="f5f11-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f5f11-116">Attribute</span></span>|<span data-ttu-id="f5f11-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f11-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="f5f11-118">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="f5f11-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="f5f11-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f5f11-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="f5f11-120">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="f5f11-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="f5f11-121">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f5f11-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="f5f11-122">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="f5f11-123">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="f5f11-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="f5f11-124">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="f5f11-125">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="f5f11-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="f5f11-126">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="f5f11-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="f5f11-127">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f5f11-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f5f11-128">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="f5f11-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f5f11-129">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="f5f11-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f5f11-130">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="f5f11-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f5f11-131">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f5f11-132">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f5f11-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f5f11-133">значения</span><span class="sxs-lookup"><span data-stu-id="f5f11-133">Value</span></span>|<span data-ttu-id="f5f11-134">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f11-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="f5f11-135">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="f5f11-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="f5f11-136">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="f5f11-137">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="f5f11-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="f5f11-138">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="f5f11-139">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="f5f11-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="f5f11-140">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f5f11-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="f5f11-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f5f11-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f5f11-142">значения</span><span class="sxs-lookup"><span data-stu-id="f5f11-142">Value</span></span>|<span data-ttu-id="f5f11-143">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f11-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="f5f11-144">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="f5f11-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="f5f11-145">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="f5f11-146">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f5f11-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="f5f11-147">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="f5f11-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="f5f11-148">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f5f11-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5f11-149">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5f11-149">Child Elements</span></span>  
 <span data-ttu-id="f5f11-150">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f5f11-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5f11-151">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f5f11-151">Parent Elements</span></span>  
  
|<span data-ttu-id="f5f11-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5f11-152">Element</span></span>|<span data-ttu-id="f5f11-153">Описание</span><span class="sxs-lookup"><span data-stu-id="f5f11-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5f11-154">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="f5f11-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="f5f11-155">Представляет возможности безопасности элемента [\<wsHttpBinding >](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f5f11-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5f11-156">См. также</span><span class="sxs-lookup"><span data-stu-id="f5f11-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="f5f11-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f5f11-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f5f11-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="f5f11-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f5f11-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f5f11-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f5f11-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f5f11-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f5f11-161">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="f5f11-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="f5f11-162">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="f5f11-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
