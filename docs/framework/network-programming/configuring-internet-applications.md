---
title: Настройка веб-приложений
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
ms.openlocfilehash: ee4dc87383153ae4e8df0a3bed7cce5220e65405
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048632"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="de445-102">Настройка веб-приложений</span><span class="sxs-lookup"><span data-stu-id="de445-102">Configuring Internet Applications</span></span>
<span data-ttu-id="de445-103">[Элемент \<system.Net> (сетевые параметры)](../configure-apps/file-schema/network/system-net-element-network-settings.md) содержит сведения о конфигурации сети для приложений.</span><span class="sxs-lookup"><span data-stu-id="de445-103">The [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="de445-104">С помощью [элемента \<system.Net> (сетевые параметры)](../configure-apps/file-schema/network/system-net-element-network-settings.md) можно задавать прокси-серверы, устанавливать параметры управления подключениями и включать в приложение пользовательские модули проверки подлинности и запросов.</span><span class="sxs-lookup"><span data-stu-id="de445-104">Using the [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="de445-105">[Элемент \<defaultProxy> (сетевые параметры)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) определяет прокси-сервер, который возвращается классом `GlobalProxySelection`.</span><span class="sxs-lookup"><span data-stu-id="de445-105">The [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="de445-106">Любой объект <xref:System.Net.HttpWebRequest>, для которого не установлено свойство <xref:System.Net.HttpWebRequest.Proxy%2A>, использует прокси-сервер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de445-106">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="de445-107">Помимо настройки адреса прокси-сервера можно создать список адресов серверов, которые не будут использовать прокси-сервер. Кроме того, можно запретить использование прокси-сервера локальным адресам.</span><span class="sxs-lookup"><span data-stu-id="de445-107">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="de445-108">Важно отметить, что параметры Microsoft Internet Explorer объединены с параметрами конфигурации, причем последние имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="de445-108">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="de445-109">В следующем примере устанавливается адрес прокси-сервера по умолчанию `http://proxyserver`, а также указывается, что прокси-сервер не должен использоваться локальными адресами и все запросы к серверам в домене contoso.com должны направляться в обход прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="de445-109">The following example sets the default proxy server address to `http://proxyserver`, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="de445-110">[Элемент \<connectionManagement> (сетевые параметры)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) задает число постоянных подключений, которые могут устанавливаться к конкретному серверу или ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="de445-110">Use the [\<connectionManagement> Element (Network Settings)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="de445-111">В следующем примере показано приложение, которое использует два постоянных подключения к серверу `www.contoso.com`, четыре постоянных подключения к серверу с IP-адресом 192.168.1.2, а также одно постоянное подключение ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="de445-111">The following example configures the application to use two persistent connections to the server `www.contoso.com`, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="de445-112">Для настройки пользовательских модулей проверки подлинности используется [элемент \<authenticationModules> (сетевые параметры)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="de445-112">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="de445-113">Пользовательские модули проверки подлинности должны реализовывать интерфейс <xref:System.Net.IAuthenticationModule>.</span><span class="sxs-lookup"><span data-stu-id="de445-113">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="de445-114">В следующем примере выполняется настройка пользовательского модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="de445-114">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="de445-115">С помощью [элемента \<webRequestModules> (сетевые параметры)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) можно настроить приложение для работы с пользовательскими модулями определенного протокола, которые позволяют запрашивать данные из интернет-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="de445-115">You can use the [\<webRequestModules> Element (Network Settings)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="de445-116">Указанные модули должны реализовывать интерфейс <xref:System.Net.IWebRequestCreate>.</span><span class="sxs-lookup"><span data-stu-id="de445-116">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="de445-117">Вы можете переопределить установленные по умолчанию модули запросов HTTP, HTTPS и файлов, указав в файле конфигурации собственный модуль, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="de445-117">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de445-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="de445-118">See also</span></span>

- [<span data-ttu-id="de445-119">Сетевое программирование в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="de445-119">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="de445-120">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="de445-120">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="de445-121">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="de445-121">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
