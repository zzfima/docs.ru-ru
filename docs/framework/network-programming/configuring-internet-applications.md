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
# <a name="configuring-internet-applications"></a>Настройка веб-приложений
[Элемент \<system.Net> (сетевые параметры)](../configure-apps/file-schema/network/system-net-element-network-settings.md) содержит сведения о конфигурации сети для приложений. С помощью [элемента \<system.Net> (сетевые параметры)](../configure-apps/file-schema/network/system-net-element-network-settings.md) можно задавать прокси-серверы, устанавливать параметры управления подключениями и включать в приложение пользовательские модули проверки подлинности и запросов.  
  
 [Элемент \<defaultProxy> (сетевые параметры)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) определяет прокси-сервер, который возвращается классом `GlobalProxySelection`. Любой объект <xref:System.Net.HttpWebRequest>, для которого не установлено свойство <xref:System.Net.HttpWebRequest.Proxy%2A>, использует прокси-сервер по умолчанию. Помимо настройки адреса прокси-сервера можно создать список адресов серверов, которые не будут использовать прокси-сервер. Кроме того, можно запретить использование прокси-сервера локальным адресам.  
  
 Важно отметить, что параметры Microsoft Internet Explorer объединены с параметрами конфигурации, причем последние имеют приоритет.  
  
 В следующем примере устанавливается адрес прокси-сервера по умолчанию `http://proxyserver`, а также указывается, что прокси-сервер не должен использоваться локальными адресами и все запросы к серверам в домене contoso.com должны направляться в обход прокси-сервера.  
  
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
  
 [Элемент \<connectionManagement> (сетевые параметры)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) задает число постоянных подключений, которые могут устанавливаться к конкретному серверу или ко всем остальным серверам. В следующем примере показано приложение, которое использует два постоянных подключения к серверу `www.contoso.com`, четыре постоянных подключения к серверу с IP-адресом 192.168.1.2, а также одно постоянное подключение ко всем остальным серверам.  
  
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
  
 Для настройки пользовательских модулей проверки подлинности используется [элемент \<authenticationModules> (сетевые параметры)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md). Пользовательские модули проверки подлинности должны реализовывать интерфейс <xref:System.Net.IAuthenticationModule>.  
  
 В следующем примере выполняется настройка пользовательского модуля проверки подлинности.  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 С помощью [элемента \<webRequestModules> (сетевые параметры)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) можно настроить приложение для работы с пользовательскими модулями определенного протокола, которые позволяют запрашивать данные из интернет-ресурсов. Указанные модули должны реализовывать интерфейс <xref:System.Net.IWebRequestCreate>. Вы можете переопределить установленные по умолчанию модули запросов HTTP, HTTPS и файлов, указав в файле конфигурации собственный модуль, как показано в следующем примере.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Сетевое программирование в .NET Framework](index.md)
- [Схема параметров сети](../configure-apps/file-schema/network/index.md)
- [Элемент \<system.Net> (сетевые параметры)](../configure-apps/file-schema/network/system-net-element-network-settings.md)
