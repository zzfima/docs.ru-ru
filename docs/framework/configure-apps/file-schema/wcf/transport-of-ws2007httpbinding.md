---
title: "&lt;transport&gt; для &lt;ws2007HttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 573b7fb5cf130d0a638326b87ae49f90db881df4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="28c6a-102">&lt;transport&gt; для &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="28c6a-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="28c6a-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="28c6a-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="28c6a-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="28c6a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="28c6a-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="28c6a-105">\<bindings></span></span>  
<span data-ttu-id="28c6a-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="28c6a-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="28c6a-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="28c6a-107">\<binding></span></span>  
<span data-ttu-id="28c6a-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="28c6a-108">\<security></span></span>  
<span data-ttu-id="28c6a-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="28c6a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c6a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28c6a-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="28c6a-111">Тип</span><span class="sxs-lookup"><span data-stu-id="28c6a-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28c6a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="28c6a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="28c6a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="28c6a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28c6a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28c6a-114">Attributes</span></span>  
  
|<span data-ttu-id="28c6a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="28c6a-115">Attribute</span></span>|<span data-ttu-id="28c6a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="28c6a-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="28c6a-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="28c6a-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="28c6a-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="28c6a-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="28c6a-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="28c6a-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="28c6a-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="28c6a-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="28c6a-121">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="28c6a-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="28c6a-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="28c6a-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="28c6a-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="28c6a-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="28c6a-125">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="28c6a-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="28c6a-126">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="28c6a-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="28c6a-127">Значение</span><span class="sxs-lookup"><span data-stu-id="28c6a-127">Value</span></span>|<span data-ttu-id="28c6a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="28c6a-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28c6a-129">Нет</span><span class="sxs-lookup"><span data-stu-id="28c6a-129">None</span></span>|<span data-ttu-id="28c6a-130">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="28c6a-130">Security is disabled.</span></span>|  
|<span data-ttu-id="28c6a-131">Basic</span><span class="sxs-lookup"><span data-stu-id="28c6a-131">Basic</span></span>|<span data-ttu-id="28c6a-132">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="28c6a-133">Digest</span><span class="sxs-lookup"><span data-stu-id="28c6a-133">Digest</span></span>|<span data-ttu-id="28c6a-134">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="28c6a-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="28c6a-135">Ntlm</span></span>|<span data-ttu-id="28c6a-136">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="28c6a-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="28c6a-137">Windows</span><span class="sxs-lookup"><span data-stu-id="28c6a-137">Windows</span></span>|<span data-ttu-id="28c6a-138">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="28c6a-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="28c6a-139">Сертификат</span><span class="sxs-lookup"><span data-stu-id="28c6a-139">Certificate</span></span>|<span data-ttu-id="28c6a-140">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="28c6a-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="28c6a-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="28c6a-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="28c6a-142">Значение</span><span class="sxs-lookup"><span data-stu-id="28c6a-142">Value</span></span>|<span data-ttu-id="28c6a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="28c6a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28c6a-144">Нет</span><span class="sxs-lookup"><span data-stu-id="28c6a-144">None</span></span>|<span data-ttu-id="28c6a-145">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="28c6a-145">Security is disabled.</span></span>|  
|<span data-ttu-id="28c6a-146">Basic</span><span class="sxs-lookup"><span data-stu-id="28c6a-146">Basic</span></span>|<span data-ttu-id="28c6a-147">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="28c6a-148">Digest</span><span class="sxs-lookup"><span data-stu-id="28c6a-148">Digest</span></span>|<span data-ttu-id="28c6a-149">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="28c6a-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="28c6a-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="28c6a-150">Ntlm</span></span>|<span data-ttu-id="28c6a-151">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="28c6a-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="28c6a-152">Windows</span><span class="sxs-lookup"><span data-stu-id="28c6a-152">Windows</span></span>|<span data-ttu-id="28c6a-153">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="28c6a-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="28c6a-154">Сертификат</span><span class="sxs-lookup"><span data-stu-id="28c6a-154">Certificate</span></span>|<span data-ttu-id="28c6a-155">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="28c6a-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28c6a-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28c6a-156">Child Elements</span></span>  
 <span data-ttu-id="28c6a-157">Нет</span><span class="sxs-lookup"><span data-stu-id="28c6a-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28c6a-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="28c6a-158">Parent Elements</span></span>  
  
|<span data-ttu-id="28c6a-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="28c6a-159">Element</span></span>|<span data-ttu-id="28c6a-160">Описание</span><span class="sxs-lookup"><span data-stu-id="28c6a-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28c6a-161">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="28c6a-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="28c6a-162">Представляет функциональные возможности безопасности [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="28c6a-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28c6a-163">См. также</span><span class="sxs-lookup"><span data-stu-id="28c6a-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="28c6a-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="28c6a-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="28c6a-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="28c6a-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="28c6a-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="28c6a-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="28c6a-167">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="28c6a-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="28c6a-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="28c6a-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
