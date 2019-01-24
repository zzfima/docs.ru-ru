---
title: '&lt;transport&gt; для &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 6f09a71a7ec7dbfae5eb6f1896f1fba68456973f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642598"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="7619a-102">&lt;transport&gt; для &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7619a-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="7619a-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="7619a-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="7619a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7619a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7619a-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7619a-105">\<bindings></span></span>  
<span data-ttu-id="7619a-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7619a-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="7619a-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7619a-107">\<binding></span></span>  
<span data-ttu-id="7619a-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="7619a-108">\<security></span></span>  
<span data-ttu-id="7619a-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="7619a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7619a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7619a-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="7619a-111">Тип</span><span class="sxs-lookup"><span data-stu-id="7619a-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7619a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7619a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7619a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7619a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7619a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7619a-114">Attributes</span></span>  
  
|<span data-ttu-id="7619a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7619a-115">Attribute</span></span>|<span data-ttu-id="7619a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7619a-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="7619a-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="7619a-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="7619a-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7619a-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="7619a-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="7619a-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="7619a-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7619a-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="7619a-121">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="7619a-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="7619a-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7619a-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="7619a-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="7619a-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="7619a-125">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="7619a-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7619a-126">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7619a-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7619a-127">Значение</span><span class="sxs-lookup"><span data-stu-id="7619a-127">Value</span></span>|<span data-ttu-id="7619a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="7619a-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7619a-129">Нет</span><span class="sxs-lookup"><span data-stu-id="7619a-129">None</span></span>|<span data-ttu-id="7619a-130">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="7619a-130">Security is disabled.</span></span>|  
|<span data-ttu-id="7619a-131">Basic</span><span class="sxs-lookup"><span data-stu-id="7619a-131">Basic</span></span>|<span data-ttu-id="7619a-132">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="7619a-133">Digest</span><span class="sxs-lookup"><span data-stu-id="7619a-133">Digest</span></span>|<span data-ttu-id="7619a-134">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="7619a-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7619a-135">Ntlm</span></span>|<span data-ttu-id="7619a-136">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="7619a-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="7619a-137">Windows</span><span class="sxs-lookup"><span data-stu-id="7619a-137">Windows</span></span>|<span data-ttu-id="7619a-138">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7619a-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="7619a-139">Сертификат</span><span class="sxs-lookup"><span data-stu-id="7619a-139">Certificate</span></span>|<span data-ttu-id="7619a-140">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="7619a-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7619a-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="7619a-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7619a-142">Значение</span><span class="sxs-lookup"><span data-stu-id="7619a-142">Value</span></span>|<span data-ttu-id="7619a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="7619a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7619a-144">Нет</span><span class="sxs-lookup"><span data-stu-id="7619a-144">None</span></span>|<span data-ttu-id="7619a-145">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="7619a-145">Security is disabled.</span></span>|  
|<span data-ttu-id="7619a-146">Basic</span><span class="sxs-lookup"><span data-stu-id="7619a-146">Basic</span></span>|<span data-ttu-id="7619a-147">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="7619a-148">Digest</span><span class="sxs-lookup"><span data-stu-id="7619a-148">Digest</span></span>|<span data-ttu-id="7619a-149">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7619a-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="7619a-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7619a-150">Ntlm</span></span>|<span data-ttu-id="7619a-151">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="7619a-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="7619a-152">Windows</span><span class="sxs-lookup"><span data-stu-id="7619a-152">Windows</span></span>|<span data-ttu-id="7619a-153">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="7619a-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="7619a-154">Сертификат</span><span class="sxs-lookup"><span data-stu-id="7619a-154">Certificate</span></span>|<span data-ttu-id="7619a-155">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="7619a-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7619a-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7619a-156">Child Elements</span></span>  
 <span data-ttu-id="7619a-157">Нет</span><span class="sxs-lookup"><span data-stu-id="7619a-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7619a-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7619a-158">Parent Elements</span></span>  
  
|<span data-ttu-id="7619a-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="7619a-159">Element</span></span>|<span data-ttu-id="7619a-160">Описание:</span><span class="sxs-lookup"><span data-stu-id="7619a-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7619a-161">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="7619a-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="7619a-162">Представляет возможности безопасности [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="7619a-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7619a-163">См. также</span><span class="sxs-lookup"><span data-stu-id="7619a-163">See also</span></span>
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="7619a-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7619a-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7619a-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="7619a-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7619a-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7619a-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7619a-167">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7619a-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7619a-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7619a-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
