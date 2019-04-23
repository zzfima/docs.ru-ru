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
ms.openlocfilehash: 8df9bbf2615776c2e023f03401785da95b2226eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204826"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="ff9a4-102">\<прокси-сервер > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="ff9a4-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="ff9a4-103">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="ff9a4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ff9a4-104">\<configuration></span></span>  
<span data-ttu-id="ff9a4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ff9a4-105">\<system.net></span></span>  
<span data-ttu-id="ff9a4-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="ff9a4-106">\<defaultProxy></span></span>  
<span data-ttu-id="ff9a4-107">\<прокси-сервера ></span><span class="sxs-lookup"><span data-stu-id="ff9a4-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9a4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff9a4-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff9a4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff9a4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff9a4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff9a4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff9a4-111">Attributes</span></span>  
  
|<span data-ttu-id="ff9a4-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="ff9a4-112">**Attribute**</span></span>|<span data-ttu-id="ff9a4-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ff9a4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="ff9a4-114">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="ff9a4-115">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="ff9a4-116">Указывает, пропускает ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="ff9a4-117">Локальные ресурсы включают локальный сервер (`http://localhost`, `http://loopback`, или `http://127.0.0.1`) и URI без точки (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="ff9a4-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="ff9a4-118">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="ff9a4-119">Указывает URI, используемый прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="ff9a4-120">Указывает расположение скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="ff9a4-121">Не используйте `bypassonlocal` атрибута с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="ff9a4-122">Указывает, следует ли использовать параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="ff9a4-123">Если значение `true`, следующие атрибуты переопределят параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="ff9a4-124">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff9a4-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff9a4-125">Child Elements</span></span>  
 <span data-ttu-id="ff9a4-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff9a4-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff9a4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ff9a4-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ff9a4-128">**Element**</span></span>|<span data-ttu-id="ff9a4-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ff9a4-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ff9a4-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="ff9a4-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="ff9a4-131">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="ff9a4-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="ff9a4-132">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ff9a4-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff9a4-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff9a4-133">Remarks</span></span>  
 <span data-ttu-id="ff9a4-134">`proxy` Элемент определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="ff9a4-135">Если этот элемент отсутствует в файле конфигурации, то платформа .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="ff9a4-136">Значение для `proxyaddress` атрибут должен иметь правильный формат универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="ff9a4-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="ff9a4-137">`scriptLocation` Атрибут ссылается на автоматическое обнаружение сценариев настройки прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="ff9a4-138"><xref:System.Net.WebProxy> Класс будет пытаться обнаружить сценарий конфигурации (обычно именованный Wpad.dat) при **использовать сценарий автоматической настройки** установлен флажок в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="ff9a4-139">Если `bypassonlocal` присвоено любое значение `scriptLocation` учитывается.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="ff9a4-140">Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1.1, которые переносят до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="ff9a4-141">Исключение возникает в том случае, если `proxyaddress` атрибут указывает на недопустимое значение по умолчанию прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="ff9a4-142">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ff9a4-143">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff9a4-143">Configuration Files</span></span>  
 <span data-ttu-id="ff9a4-144">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ff9a4-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff9a4-145">Пример</span><span class="sxs-lookup"><span data-stu-id="ff9a4-145">Example</span></span>  
 <span data-ttu-id="ff9a4-146">В следующем примере используются значения по умолчанию от прокси-сервера Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервера для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="ff9a4-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff9a4-147">См. также</span><span class="sxs-lookup"><span data-stu-id="ff9a4-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ff9a4-148">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ff9a4-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
