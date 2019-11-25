---
title: Элемент <proxy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089195"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="b808b-102">Элемент > прокси-сервера \<(параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b808b-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="b808b-103">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b808b-103">Defines a proxy server.</span></span>  

<span data-ttu-id="b808b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b808b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b808b-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b808b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="b808b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b808b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="b808b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**proxy >**</span><span class="sxs-lookup"><span data-stu-id="b808b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b808b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b808b-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b808b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b808b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b808b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b808b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b808b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b808b-111">Attributes</span></span>  
  
|<span data-ttu-id="b808b-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="b808b-112">**Attribute**</span></span>|<span data-ttu-id="b808b-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b808b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="b808b-114">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="b808b-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="b808b-115">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="b808b-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="b808b-116">Указывает, пропускается ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b808b-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="b808b-117">Локальные ресурсы включают локальный сервер (`http://localhost`, `http://loopback`или `http://127.0.0.1`) и универсальный код ресурса (URI) без точки (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="b808b-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="b808b-118">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="b808b-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="b808b-119">Указывает используемый URI прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b808b-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="b808b-120">Указывает расположение скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b808b-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="b808b-121">Не используйте атрибут `bypassonlocal` с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="b808b-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="b808b-122">Указывает, следует ли использовать параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b808b-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="b808b-123">Если задано значение `true`, последующие атрибуты будут переопределять параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b808b-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="b808b-124">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="b808b-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b808b-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b808b-125">Child Elements</span></span>  
 <span data-ttu-id="b808b-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b808b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b808b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b808b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b808b-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b808b-128">**Element**</span></span>|<span data-ttu-id="b808b-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b808b-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b808b-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="b808b-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="b808b-131">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="b808b-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="b808b-132">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b808b-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b808b-133">Заметки</span><span class="sxs-lookup"><span data-stu-id="b808b-133">Remarks</span></span>  
 <span data-ttu-id="b808b-134">Элемент `proxy` определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="b808b-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="b808b-135">Если этот элемент отсутствует в файле конфигурации, .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b808b-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="b808b-136">Значением атрибута `proxyaddress` должен быть универсальный код ресурса (URI) правильного формата.</span><span class="sxs-lookup"><span data-stu-id="b808b-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="b808b-137">Атрибут `scriptLocation` относится к автоматическому обнаружению скриптов конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b808b-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="b808b-138">Класс <xref:System.Net.WebProxy> будет пытаться разместить скрипт конфигурации (обычно с именем WPAD. dat), если в Internet Explorer выбран параметр **использовать скрипт автоматической настройки** .</span><span class="sxs-lookup"><span data-stu-id="b808b-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="b808b-139">Если для `bypassonlocal` задано любое значение, `scriptLocation` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="b808b-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="b808b-140">Используйте атрибут `usesystemdefault` для приложений .NET Framework версии 1,1, которые переносятся на версию 2,0.</span><span class="sxs-lookup"><span data-stu-id="b808b-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="b808b-141">Исключение возникает, если атрибут `proxyaddress` указывает недопустимый прокси-сервер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b808b-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="b808b-142">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="b808b-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b808b-143">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b808b-143">Configuration Files</span></span>  
 <span data-ttu-id="b808b-144">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b808b-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b808b-145">Пример</span><span class="sxs-lookup"><span data-stu-id="b808b-145">Example</span></span>  
 <span data-ttu-id="b808b-146">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="b808b-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b808b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="b808b-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="b808b-148">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b808b-148">Network Settings Schema</span></span>](index.md)
