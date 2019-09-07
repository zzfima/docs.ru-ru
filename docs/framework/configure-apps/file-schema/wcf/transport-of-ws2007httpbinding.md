---
title: <transport> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 4ea60ccaba58bc0b3fa8f2263295bf1413d25e89
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399272"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="c9125-102">\<транспортное \<> из WS2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c9125-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="c9125-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="c9125-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="c9125-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c9125-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c9125-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c9125-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c9125-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c9125-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c9125-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c9125-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="c9125-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="c9125-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c9125-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c9125-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="c9125-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="c9125-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9125-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9125-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="c9125-112">Тип</span><span class="sxs-lookup"><span data-stu-id="c9125-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9125-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9125-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c9125-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9125-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9125-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9125-115">Attributes</span></span>  
  
|<span data-ttu-id="c9125-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9125-116">Attribute</span></span>|<span data-ttu-id="c9125-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c9125-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="c9125-118">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="c9125-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="c9125-119">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c9125-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="c9125-120">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="c9125-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="c9125-121">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c9125-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="c9125-122">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="c9125-123">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c9125-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="c9125-124">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="c9125-125">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="c9125-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="c9125-126">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c9125-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="c9125-127">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="c9125-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="c9125-128">Значение</span><span class="sxs-lookup"><span data-stu-id="c9125-128">Value</span></span>|<span data-ttu-id="c9125-129">Описание</span><span class="sxs-lookup"><span data-stu-id="c9125-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c9125-130">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c9125-130">None</span></span>|<span data-ttu-id="c9125-131">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c9125-131">Security is disabled.</span></span>|  
|<span data-ttu-id="c9125-132">Стандартная</span><span class="sxs-lookup"><span data-stu-id="c9125-132">Basic</span></span>|<span data-ttu-id="c9125-133">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="c9125-134">Digest</span><span class="sxs-lookup"><span data-stu-id="c9125-134">Digest</span></span>|<span data-ttu-id="c9125-135">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="c9125-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="c9125-136">Ntlm</span></span>|<span data-ttu-id="c9125-137">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="c9125-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="c9125-138">Windows</span><span class="sxs-lookup"><span data-stu-id="c9125-138">Windows</span></span>|<span data-ttu-id="c9125-139">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c9125-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="c9125-140">Сертификат</span><span class="sxs-lookup"><span data-stu-id="c9125-140">Certificate</span></span>|<span data-ttu-id="c9125-141">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="c9125-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="c9125-142">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="c9125-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="c9125-143">Значение</span><span class="sxs-lookup"><span data-stu-id="c9125-143">Value</span></span>|<span data-ttu-id="c9125-144">Описание</span><span class="sxs-lookup"><span data-stu-id="c9125-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c9125-145">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c9125-145">None</span></span>|<span data-ttu-id="c9125-146">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c9125-146">Security is disabled.</span></span>|  
|<span data-ttu-id="c9125-147">Стандартная</span><span class="sxs-lookup"><span data-stu-id="c9125-147">Basic</span></span>|<span data-ttu-id="c9125-148">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="c9125-149">Digest</span><span class="sxs-lookup"><span data-stu-id="c9125-149">Digest</span></span>|<span data-ttu-id="c9125-150">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9125-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="c9125-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="c9125-151">Ntlm</span></span>|<span data-ttu-id="c9125-152">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="c9125-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="c9125-153">Windows</span><span class="sxs-lookup"><span data-stu-id="c9125-153">Windows</span></span>|<span data-ttu-id="c9125-154">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c9125-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="c9125-155">Сертификат</span><span class="sxs-lookup"><span data-stu-id="c9125-155">Certificate</span></span>|<span data-ttu-id="c9125-156">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="c9125-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9125-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9125-157">Child Elements</span></span>  
 <span data-ttu-id="c9125-158">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c9125-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9125-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9125-159">Parent Elements</span></span>  
  
|<span data-ttu-id="c9125-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9125-160">Element</span></span>|<span data-ttu-id="c9125-161">Описание</span><span class="sxs-lookup"><span data-stu-id="c9125-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9125-162">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="c9125-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="c9125-163">Представляет возможности [ \<безопасности элемента WS2007HttpBinding >](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c9125-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9125-164">См. также</span><span class="sxs-lookup"><span data-stu-id="c9125-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="c9125-165">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c9125-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c9125-166">Привязки</span><span class="sxs-lookup"><span data-stu-id="c9125-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c9125-167">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c9125-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c9125-168">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c9125-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c9125-169">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c9125-169">\<binding></span></span>](../../../misc/binding.md)
