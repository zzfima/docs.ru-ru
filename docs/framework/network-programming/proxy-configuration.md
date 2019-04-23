---
title: Настройка прокси-сервера
ms.date: 06/18/2018
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
ms.openlocfilehash: c6b3808a2d73070cc07b31eb0fca7ca9d6af8cdb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200549"
---
# <a name="proxy-configuration"></a><span data-ttu-id="11e4d-102">Настройка прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="11e4d-102">Proxy Configuration</span></span>
<span data-ttu-id="11e4d-103">Прокси-сервер обрабатывает клиентские запросы на ресурсы.</span><span class="sxs-lookup"><span data-stu-id="11e4d-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="11e4d-104">Прокси-сервер может возвращать запрошенный ресурс из своего кэша или пересылать запрос на сервер, на котором находится данный ресурс.</span><span class="sxs-lookup"><span data-stu-id="11e4d-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="11e4d-105">Прокси-серверы могут повышать производительность сети, благодаря уменьшению числа запросов, отправляемых на удаленные серверы.</span><span class="sxs-lookup"><span data-stu-id="11e4d-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="11e4d-106">Прокси-серверы также можно использовать для ограничения доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="11e4d-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="11e4d-107">Адаптивные прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="11e4d-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="11e4d-108">На платформе .NET Framework могут иметься прокси-серверы двух видов: адаптивные и статические.</span><span class="sxs-lookup"><span data-stu-id="11e4d-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="11e4d-109">Адаптивный прокси-серверы настраивают свои параметры при изменении конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="11e4d-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="11e4d-110">Например, если пользователь ноутбука запускает коммутируемое сетевое соединение, то адаптивный прокси-сервер определит это изменение, обнаружит и выполнит свой новый скрипт конфигурации, а также настроит свои параметры соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="11e4d-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="11e4d-111">Адаптивные прокси-серверы настраиваются с помощью скрипта конфигурации (см. раздел [Автоматическое обнаружение прокси-сервера](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="11e4d-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="11e4d-112">Скрипт создает набор протоколов приложений и прокси-сервер для каждого протокола.</span><span class="sxs-lookup"><span data-stu-id="11e4d-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="11e4d-113">В сетевой среде может потребоваться внесение изменений, если система использует новый набор прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="11e4d-113">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="11e4d-114">Если сетевое соединение пропадает, или выполняется инициализация нового сетевого соединения, то система должна обнаружить соответствующий источник скрипта конфигурации в новой среде и запустить новый скрипт.</span><span class="sxs-lookup"><span data-stu-id="11e4d-114">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="11e4d-115">Можно использовать атрибут `usesystemdefault` элемента [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="11e4d-115">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="11e4d-116">Атрибут `usesystemdefault` определяет, должны ли параметры статического прокси-сервера (адрес прокси-сервера, список обхода и локальный обход) считываться из параметров прокси Internet Explorer для пользователя.</span><span class="sxs-lookup"><span data-stu-id="11e4d-116">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="11e4d-117">Если установлено значение `true`, будут использоваться параметры статического прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="11e4d-117">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="11e4d-118">Если установлено значение `false` (или значение вообще не задано), то параметры статического прокси-сервера можно указать в конфигурации, и они будут переопределять параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="11e4d-118">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="11e4d-119">Для включения адаптивного прокси-сервера необходимо установить значение `false` (либо вообще не задавать).</span><span class="sxs-lookup"><span data-stu-id="11e4d-119">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="11e4d-120">В следующем примере показана конфигурация обычного адаптивного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="11e4d-120">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="11e4d-121">Статические прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="11e4d-121">Static Proxies</span></span>  
 <span data-ttu-id="11e4d-122">Статические прокси-серверы обычно настраиваются явным образом приложением, или когда файл конфигурации вызывается приложением или системой.</span><span class="sxs-lookup"><span data-stu-id="11e4d-122">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="11e4d-123">Статические прокси-серверы применяются в сетях, топология которых изменяется редко, например, когда настольный компьютер подключен к корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="11e4d-123">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="11e4d-124">Работой статического прокси-сервера управляют несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="11e4d-124">Several options control how a static proxy operates.</span></span> <span data-ttu-id="11e4d-125">Можно задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="11e4d-125">You can specify the following:</span></span>  
  
-   <span data-ttu-id="11e4d-126">Адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="11e4d-126">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="11e4d-127">Определяет, нужно ли обходить прокси-сервер для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="11e4d-127">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="11e4d-128">Определяет, нужно ли обходить прокси-сервер для набора адресов.</span><span class="sxs-lookup"><span data-stu-id="11e4d-128">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="11e4d-129">Ниже указаны параметры конфигурации для статического прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="11e4d-129">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="11e4d-130">Параметр атрибута, свойства или файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="11e4d-130">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="11e4d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="11e4d-131">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="11e4d-132">`proxyaddress` или <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="11e4d-132">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="11e4d-133">Адрес используемого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="11e4d-133">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="11e4d-134">`bypassonlocal` или <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="11e4d-134">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="11e4d-135">Определяет, выполняется ли обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="11e4d-135">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="11e4d-136">`bypasslist` или <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="11e4d-136">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="11e4d-137">Описывает (с помощью регулярных выражений) набор адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="11e4d-137">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="11e4d-138">Определяет, должны ли параметры статического прокси-сервера (адрес прокси-сервера, список обхода и локальный обход) считываться из параметров прокси-сервера Internet Explorer для пользователя.</span><span class="sxs-lookup"><span data-stu-id="11e4d-138">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="11e4d-139">Если установлено значение `true`, будут использоваться параметры статического прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="11e4d-139">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="11e4d-140">На платформе .NET Framework 2.0 (если установлено значение `true`) параметры прокси-сервера обозревателя Internet Explorer не переопределяются другими параметрами прокси-сервера в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="11e4d-140">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="11e4d-141">На платформе .NET Framework 1.1 параметры прокси-сервера обозревателя Internet Explorer могут переопределяться другими параметрами прокси-сервера в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="11e4d-141">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="11e4d-142">Если установлено значение `false` (или значение вообще не задано), то параметры статического прокси-сервера можно указать в конфигурации, и они будут переопределять параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="11e4d-142">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="11e4d-143">Для включения адаптивного прокси-сервера необходимо установить значение `false` (либо вообще не задавать).</span><span class="sxs-lookup"><span data-stu-id="11e4d-143">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="11e4d-144">В следующем примере показана типовая конфигурация адаптивного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="11e4d-144">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11e4d-145">См. также</span><span class="sxs-lookup"><span data-stu-id="11e4d-145">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="11e4d-146">Автоматическое обнаружение прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="11e4d-146">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
