---
title: <transport> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732735"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="d0c98-102">\<транспортную > \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d0c98-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="d0c98-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="d0c98-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="d0c98-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d0c98-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d0c98-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d0c98-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d0c98-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="d0c98-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="d0c98-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d0c98-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="d0c98-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="d0c98-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d0c98-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d0c98-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="d0c98-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="d0c98-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d0c98-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0c98-111">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="d0c98-112">Type</span><span class="sxs-lookup"><span data-stu-id="d0c98-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="d0c98-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0c98-113">Attributes and Elements</span></span>

<span data-ttu-id="d0c98-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0c98-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d0c98-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0c98-115">Attributes</span></span>

|<span data-ttu-id="d0c98-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0c98-116">Attribute</span></span>|<span data-ttu-id="d0c98-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d0c98-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="d0c98-118">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="d0c98-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="d0c98-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d0c98-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="d0c98-120">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="d0c98-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="d0c98-121">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d0c98-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="d0c98-122">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="d0c98-123">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="d0c98-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d0c98-124">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="d0c98-125">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="d0c98-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="d0c98-126">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="d0c98-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="d0c98-127">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="d0c98-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="d0c98-128">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="d0c98-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="d0c98-129">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="d0c98-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="d0c98-130">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="d0c98-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="d0c98-131">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d0c98-132">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d0c98-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="d0c98-133">значения</span><span class="sxs-lookup"><span data-stu-id="d0c98-133">Value</span></span>|<span data-ttu-id="d0c98-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d0c98-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="d0c98-135">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="d0c98-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="d0c98-136">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="d0c98-137">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="d0c98-138">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c98-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="d0c98-139">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c98-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="d0c98-140">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="d0c98-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="d0c98-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="d0c98-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="d0c98-142">значения</span><span class="sxs-lookup"><span data-stu-id="d0c98-142">Value</span></span>|<span data-ttu-id="d0c98-143">Описание</span><span class="sxs-lookup"><span data-stu-id="d0c98-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="d0c98-144">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="d0c98-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="d0c98-145">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="d0c98-146">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0c98-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="d0c98-147">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c98-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="d0c98-148">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d0c98-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="d0c98-149">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="d0c98-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d0c98-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0c98-150">Child Elements</span></span>

<span data-ttu-id="d0c98-151">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0c98-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d0c98-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0c98-152">Parent Elements</span></span>

|<span data-ttu-id="d0c98-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0c98-153">Element</span></span>|<span data-ttu-id="d0c98-154">Описание</span><span class="sxs-lookup"><span data-stu-id="d0c98-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d0c98-155">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="d0c98-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="d0c98-156">Представляет возможности безопасности [\<wsHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d0c98-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="d0c98-157">См. также</span><span class="sxs-lookup"><span data-stu-id="d0c98-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="d0c98-158">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d0c98-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d0c98-159">Привязки</span><span class="sxs-lookup"><span data-stu-id="d0c98-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d0c98-160">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d0c98-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d0c98-161">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d0c98-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d0c98-162">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="d0c98-162">\<binding></span></span>](bindings.md)
