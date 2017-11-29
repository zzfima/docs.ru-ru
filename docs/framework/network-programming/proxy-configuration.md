---
title: "Настройка прокси-сервера"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b543097d0fc85c502bd36f22225958f9239ccd71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="proxy-configuration"></a><span data-ttu-id="07408-102">Настройка прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="07408-102">Proxy Configuration</span></span>
<span data-ttu-id="07408-103">Прокси-сервер обрабатывает клиентские запросы на ресурсы.</span><span class="sxs-lookup"><span data-stu-id="07408-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="07408-104">Прокси-сервер может возвращать запрошенный ресурс из своего кэша или пересылать запрос на сервер, на котором находится данный ресурс.</span><span class="sxs-lookup"><span data-stu-id="07408-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="07408-105">Прокси-серверы могут повышать производительность сети, благодаря уменьшению числа запросов, отправляемых на удаленные серверы.</span><span class="sxs-lookup"><span data-stu-id="07408-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="07408-106">Прокси-серверы также можно использовать для ограничения доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="07408-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="07408-107">Адаптивные прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="07408-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="07408-108">На платформе .NET Framework могут иметься прокси-серверы двух видов: адаптивные и статические.</span><span class="sxs-lookup"><span data-stu-id="07408-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="07408-109">Адаптивный прокси-серверы настраивают свои параметры при изменении конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="07408-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="07408-110">Например, если пользователь ноутбука запускает коммутируемое сетевое соединение, то адаптивный прокси-сервер определит это изменение, обнаружит и выполнит свой новый скрипт конфигурации, а также настроит свои параметры соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="07408-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="07408-111">Адаптивные прокси-серверы настраиваются с помощью скрипта конфигурации (см. раздел [Автоматическое обнаружение прокси-сервера](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="07408-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="07408-112">Скрипт создает набор протоколов приложений и прокси-сервер для каждого протокола.</span><span class="sxs-lookup"><span data-stu-id="07408-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="07408-113">Управление режимом выполнения скрипта конфигурации обеспечивают несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="07408-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="07408-114">Можно задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="07408-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="07408-115">Частота загрузки и выполнения скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="07408-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="07408-116">Время ожидания загрузки скрипта.</span><span class="sxs-lookup"><span data-stu-id="07408-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="07408-117">Учетные данные, которые ваша система должна использовать для доступа к прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="07408-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="07408-118">Учетные данные, которые ваша система должна использовать для загрузки скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="07408-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="07408-119">В сетевой среде может потребоваться внесение изменений, если система использует новый набор прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="07408-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="07408-120">Если сетевое соединение пропадает, или выполняется инициализация нового сетевого соединения, то система должна обнаружить соответствующий источник скрипта конфигурации в новой среде и запустить новый скрипт.</span><span class="sxs-lookup"><span data-stu-id="07408-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="07408-121">В следующей таблице содержатся параметры конфигурации для адаптивного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="07408-122">Параметр атрибута, свойства или файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="07408-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="07408-123">Описание</span><span class="sxs-lookup"><span data-stu-id="07408-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="07408-124">Интервал времени в секундах между сеансами загрузки скрипта.</span><span class="sxs-lookup"><span data-stu-id="07408-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="07408-125">Время ожидания (в секундах) загрузки скрипта.</span><span class="sxs-lookup"><span data-stu-id="07408-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="07408-126">`useDefaultCredentials` или <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="07408-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="07408-127">Определяет, использует ли система для доступа к прокси-серверу сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07408-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="07408-128">Определяет, использует ли система для загрузки скрипта конфигурации сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07408-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="07408-129">Определяет, должны ли параметры статического прокси-сервера (адрес прокси-сервера, список обхода и локальный обход) считываться из параметров прокси-сервера Internet Explorer для пользователя.</span><span class="sxs-lookup"><span data-stu-id="07408-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="07408-130">Если установлено значение «true», то будут использоваться параметры статического прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="07408-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="07408-131">Если установлено значение «false» (или значение вообще не задано), то параметры статического прокси-сервера можно указать в конфигурации, и они будут переопределять параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="07408-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="07408-132">Для включения адаптивного прокси-сервера необходимо установить значение «false» (либо вообще не задавать).</span><span class="sxs-lookup"><span data-stu-id="07408-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="07408-133">В следующем примере показана конфигурация обычного адаптивного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="07408-134">Статические прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="07408-134">Static Proxies</span></span>  
 <span data-ttu-id="07408-135">Статические прокси-серверы обычно настраиваются явным образом приложением, или когда файл конфигурации вызывается приложением или системой.</span><span class="sxs-lookup"><span data-stu-id="07408-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="07408-136">Статические прокси-серверы применяются в сетях, топология которых изменяется редко, например, когда настольный компьютер подключен к корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="07408-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="07408-137">Работой статического прокси-сервера управляют несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="07408-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="07408-138">Можно задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="07408-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="07408-139">Адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="07408-140">Определяет, нужно ли обходить прокси-сервер для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="07408-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="07408-141">Определяет, нужно ли обходить прокси-сервер для набора адресов.</span><span class="sxs-lookup"><span data-stu-id="07408-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="07408-142">Ниже указаны параметры конфигурации для статического прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="07408-143">Параметр атрибута, свойства или файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="07408-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="07408-144">Описание</span><span class="sxs-lookup"><span data-stu-id="07408-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="07408-145">`proxyaddress` или <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="07408-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="07408-146">Адрес используемого прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="07408-147">`bypassonlocal` или <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="07408-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="07408-148">Определяет, выполняется ли обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="07408-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="07408-149">`bypasslist` или <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="07408-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="07408-150">Описывает (с помощью регулярных выражений) набор адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="07408-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="07408-151">Определяет, должны ли параметры статического прокси-сервера (адрес прокси-сервера, список обхода и локальный обход) считываться из параметров прокси-сервера Internet Explorer для пользователя.</span><span class="sxs-lookup"><span data-stu-id="07408-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="07408-152">Если установлено значение «true», то будут использоваться параметры статического прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="07408-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="07408-153">На платформе .NET Framework 2.0 (если установлено значение «true») параметры прокси-сервера обозревателя Internet Explorer не переопределяются другими параметрами прокси-сервера в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="07408-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="07408-154">На платформе .NET Framework 1.1 параметры прокси-сервера обозревателя Internet Explorer могут переопределяться другими параметрами прокси-сервера в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="07408-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="07408-155">Если установлено значение «false» (или значение вообще не задано), то параметры статического прокси-сервера можно указать в конфигурации, и они будут переопределять параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="07408-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="07408-156">Для включения адаптивного прокси-сервера необходимо установить значение «false» (либо вообще не задавать).</span><span class="sxs-lookup"><span data-stu-id="07408-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="07408-157">В следующем примере показана типовая конфигурация адаптивного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="07408-157">The following example shows a typical static proxy configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07408-158">См. также</span><span class="sxs-lookup"><span data-stu-id="07408-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="07408-159">Автоматическое обнаружение прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="07408-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
