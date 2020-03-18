---
title: Автоматическое обнаружение прокси-сервера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: 4c5bc9e0efb39032d388d141e8bccf3e520ebd45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180896"
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="0a908-102">Автоматическое обнаружение прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="0a908-102">Automatic Proxy Detection</span></span>
<span data-ttu-id="0a908-103">В ходе автоматического обнаружения прокси-сервера система определяет сервер веб-прокси, который используется для отправки запросов от имени клиента.</span><span class="sxs-lookup"><span data-stu-id="0a908-103">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="0a908-104">Эта функция также называется автообнаружением веб-прокси (WPAD).</span><span class="sxs-lookup"><span data-stu-id="0a908-104">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="0a908-105">Если автоматическое обнаружение прокси-сервера включено, система пытается обнаружить скрипт конфигурации прокси-сервера, возвращающий набор прокси-серверов, который можно использовать для обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="0a908-105">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="0a908-106">Если такой скрипт обнаружен, он скачивается, компилируется и запускается на локальном компьютере при получении информации о прокси-сервере, потока запроса или ответа для запроса, который использует экземпляр <xref:System.Net.WebProxy>.</span><span class="sxs-lookup"><span data-stu-id="0a908-106">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="0a908-107">Автоматическое обнаружение прокси-сервера реализуется с помощью класса <xref:System.Net.WebProxy>. Параметры этого процесса могут задаваться на уровне запроса, в файлах конфигурации, а также в диалоговом окне **Локальная сеть (LAN)** браузера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0a908-107">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a908-108">Чтобы открыть диалоговое окно **Параметры локальной сети** Internet Explorer, выберите **Сервис** в главном меню этого браузера, а затем пункт **Свойства браузера**.</span><span class="sxs-lookup"><span data-stu-id="0a908-108">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="0a908-109">Перейдите на вкладку **Подключения** и выберите **Параметры локальной сети**.</span><span class="sxs-lookup"><span data-stu-id="0a908-109">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="0a908-110">Если автоматическое обнаружение прокси-сервера включено, класс <xref:System.Net.WebProxy> пытается найти скрипт конфигурации прокси-сервера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0a908-110">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1. <span data-ttu-id="0a908-111">Функция WinINet `InternetQueryOption` используется для поиска скрипта конфигурации прокси-сервера, который был обнаружен браузером Internet Explorer в последний раз.</span><span class="sxs-lookup"><span data-stu-id="0a908-111">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2. <span data-ttu-id="0a908-112">Если найти этот скрипт не удается, класс <xref:System.Net.WebProxy> использует для его поиска протокола DHCP.</span><span class="sxs-lookup"><span data-stu-id="0a908-112">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="0a908-113">DHCP-сервер может вернуть в ответе расположение (имя узла) скрипта или полный URL-адрес скрипта.</span><span class="sxs-lookup"><span data-stu-id="0a908-113">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3. <span data-ttu-id="0a908-114">Если с помощью DHCP не удалось определить узел автообнаружения веб-прокси (WPAD), выполняется запрос узла DNS, в качестве имени или псевдонима которого используется WPAD.</span><span class="sxs-lookup"><span data-stu-id="0a908-114">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4. <span data-ttu-id="0a908-115">Если обнаружить узел не удается и расположение скрипта конфигурации прокси-сервера задается в файле конфигурации или параметрах локальной сети браузера Internet Explorer, используется это расположение.</span><span class="sxs-lookup"><span data-stu-id="0a908-115">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a908-116">Приложения, выполняемые как службы NT или в составе ASP.NET, используют параметры прокси-сервера, задаваемые Internet Explorer (если доступны), вызывающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a908-116">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="0a908-117">Эти параметры могут быть доступны не для всех приложений службы.</span><span class="sxs-lookup"><span data-stu-id="0a908-117">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="0a908-118">Прокси-серверы настраиваются отдельно для каждого устройства подключения.</span><span class="sxs-lookup"><span data-stu-id="0a908-118">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="0a908-119">Устройство подключения — это элемент в диалоговом окне сетевого подключения, который может быть как физическим сетевым устройством (модем или плата Ethernet), так и виртуальным интерфейсом (например, VPN-подключение, работающее через сетевое устройство).</span><span class="sxs-lookup"><span data-stu-id="0a908-119">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="0a908-120">При изменении устройства подключения (например, при смене точки доступа для беспроводного подключения или включении VPN) алгоритм обнаружения прокси-сервера запускается снова.</span><span class="sxs-lookup"><span data-stu-id="0a908-120">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="0a908-121">По умолчанию для обнаружения прокси-сервера используются параметры прокси, задаваемые браузером Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0a908-121">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="0a908-122">Если приложение выполняется под учетной записью, не являющейся интерактивной (не поддерживает удобный способ настройки параметров прокси-сервера в Internet Explorer), или требуется использовать другие параметры прокси-сервера, вы можете настроить собственный прокси-сервер, создав файл конфигурации, в котором определены [элемент \<defaultProxy> (сетевые параметры)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) и [элемент \<proxy> (сетевые параметры)](../configure-apps/file-schema/network/proxy-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0a908-122">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="0a908-123">Для создаваемых вами запросов можно отключить автоматическое обнаружение прокси-сервера на уровне запроса, указав в нем <xref:System.Net.WebRequest.Proxy%2A> NULL, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0a908-123">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 <span data-ttu-id="0a908-124">Для обработки запросов, не указывающих прокси-сервер, используется прокси-сервер по умолчанию домена приложения, который доступен в свойстве <xref:System.Net.WebRequest.DefaultWebProxy%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a908-124">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a908-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0a908-125">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="0a908-126">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="0a908-126">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
