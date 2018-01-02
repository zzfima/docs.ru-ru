---
title: "&lt;прокси-сервер&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b0b397e66e0f73d10f482bc9151a6fbacf3e774d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="2cd21-102">&lt;прокси-сервер&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2cd21-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2cd21-103">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2cd21-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="2cd21-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2cd21-104">\<configuration></span></span>  
<span data-ttu-id="2cd21-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="2cd21-105">\<system.net></span></span>  
<span data-ttu-id="2cd21-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="2cd21-106">\<defaultProxy></span></span>  
<span data-ttu-id="2cd21-107">\<прокси-сервера ></span><span class="sxs-lookup"><span data-stu-id="2cd21-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd21-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cd21-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cd21-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2cd21-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2cd21-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2cd21-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cd21-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2cd21-111">Attributes</span></span>  
  
|<span data-ttu-id="2cd21-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="2cd21-112">**Attribute**</span></span>|<span data-ttu-id="2cd21-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2cd21-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="2cd21-114">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="2cd21-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="2cd21-115">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2cd21-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="2cd21-116">Указывает, пропускает ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2cd21-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="2cd21-117">Локальные ресурсы включают локальный сервер (http://localhost, http://loopback или http://127.0.0.1) и URI без точки (http://webserver).</span><span class="sxs-lookup"><span data-stu-id="2cd21-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="2cd21-118">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2cd21-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="2cd21-119">Указывает URI, который используется прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2cd21-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="2cd21-120">Указывает расположение скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2cd21-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="2cd21-121">Указывает, следует ли использовать параметры прокси-сервера обозревателя Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2cd21-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="2cd21-122">Если значение `true`, следующие атрибуты переопределят параметры прокси Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2cd21-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="2cd21-123">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2cd21-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cd21-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2cd21-124">Child Elements</span></span>  
 <span data-ttu-id="2cd21-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2cd21-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2cd21-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2cd21-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2cd21-127">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2cd21-127">**Element**</span></span>|<span data-ttu-id="2cd21-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2cd21-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2cd21-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2cd21-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="2cd21-130">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2cd21-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="2cd21-131">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2cd21-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cd21-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="2cd21-132">Remarks</span></span>  
 <span data-ttu-id="2cd21-133">`proxy` Элемент определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="2cd21-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="2cd21-134">Если этот элемент отсутствует в файле конфигурации, .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2cd21-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2cd21-135">Значение для `proxyaddress` атрибут должен иметь правильный формат унифицированного указателя ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="2cd21-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="2cd21-136">`scriptLocation` Атрибут ссылается на автоматическое обнаружение сценариев настройки прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2cd21-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="2cd21-137"><xref:System.Net.WebProxy> Класс попытается обнаружить сценарий конфигурации (обычно именованный Wpad.dat) при **использовать сценарий автоматической настройки** флажок в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2cd21-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2cd21-138">Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1.1, выполняется миграция в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cd21-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="2cd21-139">Исключение возникает, если `proxyaddress` атрибут указывает на недопустимое значение по умолчанию прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2cd21-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="2cd21-140">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о корневой причине ошибки.</span><span class="sxs-lookup"><span data-stu-id="2cd21-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2cd21-141">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2cd21-141">Configuration Files</span></span>  
 <span data-ttu-id="2cd21-142">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2cd21-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cd21-143">Пример</span><span class="sxs-lookup"><span data-stu-id="2cd21-143">Example</span></span>  
 <span data-ttu-id="2cd21-144">Следующий пример использует значения по умолчанию из прокси-сервера обозревателя Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервера для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="2cd21-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2cd21-145">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd21-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="2cd21-146">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2cd21-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
