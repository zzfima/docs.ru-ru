---
title: '&lt;transport&gt; для &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 35af47551f742b0e48220611a874605fb752b626
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533382"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="e3fac-102">&lt;transport&gt; для &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e3fac-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="e3fac-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="e3fac-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="e3fac-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e3fac-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e3fac-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e3fac-105">\<bindings></span></span>  
<span data-ttu-id="e3fac-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e3fac-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="e3fac-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e3fac-107">\<binding></span></span>  
<span data-ttu-id="e3fac-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e3fac-108">\<security></span></span>  
<span data-ttu-id="e3fac-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="e3fac-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fac-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3fac-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="e3fac-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e3fac-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3fac-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3fac-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e3fac-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3fac-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3fac-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3fac-114">Attributes</span></span>  
  
|<span data-ttu-id="e3fac-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3fac-115">Attribute</span></span>|<span data-ttu-id="e3fac-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e3fac-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="e3fac-117">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e3fac-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="e3fac-118">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3fac-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="e3fac-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="e3fac-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="e3fac-120">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3fac-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="e3fac-121">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="e3fac-122">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="e3fac-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e3fac-123">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="e3fac-124">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="e3fac-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="e3fac-125">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e3fac-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e3fac-126">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3fac-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e3fac-127">Значение</span><span class="sxs-lookup"><span data-stu-id="e3fac-127">Value</span></span>|<span data-ttu-id="e3fac-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e3fac-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3fac-129">Нет</span><span class="sxs-lookup"><span data-stu-id="e3fac-129">None</span></span>|<span data-ttu-id="e3fac-130">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e3fac-130">Security is disabled.</span></span>|  
|<span data-ttu-id="e3fac-131">Basic</span><span class="sxs-lookup"><span data-stu-id="e3fac-131">Basic</span></span>|<span data-ttu-id="e3fac-132">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="e3fac-133">Digest</span><span class="sxs-lookup"><span data-stu-id="e3fac-133">Digest</span></span>|<span data-ttu-id="e3fac-134">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="e3fac-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e3fac-135">Ntlm</span></span>|<span data-ttu-id="e3fac-136">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="e3fac-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="e3fac-137">Windows</span><span class="sxs-lookup"><span data-stu-id="e3fac-137">Windows</span></span>|<span data-ttu-id="e3fac-138">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3fac-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="e3fac-139">Сертификат</span><span class="sxs-lookup"><span data-stu-id="e3fac-139">Certificate</span></span>|<span data-ttu-id="e3fac-140">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="e3fac-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e3fac-141">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3fac-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e3fac-142">Значение</span><span class="sxs-lookup"><span data-stu-id="e3fac-142">Value</span></span>|<span data-ttu-id="e3fac-143">Описание</span><span class="sxs-lookup"><span data-stu-id="e3fac-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3fac-144">Нет</span><span class="sxs-lookup"><span data-stu-id="e3fac-144">None</span></span>|<span data-ttu-id="e3fac-145">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e3fac-145">Security is disabled.</span></span>|  
|<span data-ttu-id="e3fac-146">Basic</span><span class="sxs-lookup"><span data-stu-id="e3fac-146">Basic</span></span>|<span data-ttu-id="e3fac-147">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="e3fac-148">Digest</span><span class="sxs-lookup"><span data-stu-id="e3fac-148">Digest</span></span>|<span data-ttu-id="e3fac-149">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3fac-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="e3fac-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e3fac-150">Ntlm</span></span>|<span data-ttu-id="e3fac-151">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="e3fac-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="e3fac-152">Windows</span><span class="sxs-lookup"><span data-stu-id="e3fac-152">Windows</span></span>|<span data-ttu-id="e3fac-153">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3fac-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="e3fac-154">Сертификат</span><span class="sxs-lookup"><span data-stu-id="e3fac-154">Certificate</span></span>|<span data-ttu-id="e3fac-155">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="e3fac-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3fac-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3fac-156">Child Elements</span></span>  
 <span data-ttu-id="e3fac-157">Нет</span><span class="sxs-lookup"><span data-stu-id="e3fac-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3fac-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3fac-158">Parent Elements</span></span>  
  
|<span data-ttu-id="e3fac-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3fac-159">Element</span></span>|<span data-ttu-id="e3fac-160">Описание</span><span class="sxs-lookup"><span data-stu-id="e3fac-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3fac-161">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e3fac-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="e3fac-162">Представляет возможности безопасности [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="e3fac-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3fac-163">См. также</span><span class="sxs-lookup"><span data-stu-id="e3fac-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="e3fac-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e3fac-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e3fac-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="e3fac-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e3fac-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e3fac-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e3fac-167">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="e3fac-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e3fac-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e3fac-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
