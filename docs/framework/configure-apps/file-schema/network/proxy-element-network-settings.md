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
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154794"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="2261a-102">\<прокси> элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="2261a-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="2261a-103">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2261a-103">Defines a proxy server.</span></span>  

<span data-ttu-id="2261a-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2261a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2261a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2261a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="2261a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2261a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="2261a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<прокси>**</span><span class="sxs-lookup"><span data-stu-id="2261a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2261a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2261a-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2261a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2261a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2261a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2261a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2261a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2261a-111">Attributes</span></span>  
  
|<span data-ttu-id="2261a-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="2261a-112">**Attribute**</span></span>|<span data-ttu-id="2261a-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2261a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="2261a-114">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="2261a-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="2261a-115">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2261a-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="2261a-116">Указывает, используется ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2261a-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="2261a-117">Местные ресурсы включают`http://localhost` `http://loopback`локальный `http://127.0.0.1`сервер (, или`http://webserver`) и URI без периода ().</span><span class="sxs-lookup"><span data-stu-id="2261a-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="2261a-118">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2261a-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="2261a-119">Определяет прокси URI для использования.</span><span class="sxs-lookup"><span data-stu-id="2261a-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="2261a-120">Определяет местоположение сценария конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2261a-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="2261a-121">Не используйте `bypassonlocal` атрибут с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="2261a-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="2261a-122">Определяет, следует ли использовать настройки прокси-серверов Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2261a-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="2261a-123">Если `true`установлено, последующие атрибуты переопределяют настройки прокси-серверов Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2261a-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="2261a-124">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2261a-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2261a-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2261a-125">Child Elements</span></span>  
 <span data-ttu-id="2261a-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="2261a-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2261a-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2261a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2261a-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2261a-128">**Element**</span></span>|<span data-ttu-id="2261a-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2261a-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2261a-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2261a-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2261a-131">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2261a-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="2261a-132">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2261a-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2261a-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="2261a-133">Remarks</span></span>  
 <span data-ttu-id="2261a-134">Элемент `proxy` определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="2261a-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="2261a-135">Если этот элемент отсутствует в файле конфигурации, то в рамке .NET будут использоваться настройки прокси в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2261a-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2261a-136">Значение атрибута `proxyaddress` должно быть хорошо сформированным единым индикатором ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="2261a-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="2261a-137">Атрибут `scriptLocation` относится к автоматическому обнаружению скриптов конфигурации прокси.</span><span class="sxs-lookup"><span data-stu-id="2261a-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="2261a-138">Класс <xref:System.Net.WebProxy> попытается найти сценарий конфигурации (обычно названный Wpad.dat), когда параметр **автоматической конфигурации «Использование»** выбран в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2261a-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="2261a-139">Если `bypassonlocal` настроен на какое-либо значение, `scriptLocation` игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2261a-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="2261a-140">Используйте `usesystemdefault` атрибут для приложений .NET Framework 1.1, которые мигрируют в версию 2.0.</span><span class="sxs-lookup"><span data-stu-id="2261a-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="2261a-141">Исключение брошено, `proxyaddress` если атрибут указывает недействительный прокси по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2261a-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="2261a-142">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="2261a-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2261a-143">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2261a-143">Configuration Files</span></span>  
 <span data-ttu-id="2261a-144">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2261a-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2261a-145">Пример</span><span class="sxs-lookup"><span data-stu-id="2261a-145">Example</span></span>  
 <span data-ttu-id="2261a-146">В следующем примере используются по умолчанию из прокси-сервера Internet Explorer, указывается прокси-адрес и обходит прокси для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="2261a-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2261a-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2261a-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2261a-148">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="2261a-148">Network Settings Schema</span></span>](index.md)
