---
title: "Настройка веб-приложений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "загрузка ресурсов Интернета, прокси-сервер по умолчанию"
  - "отправка данных, прокси-сервер по умолчанию"
  - "получение данных, прокси-сервер по умолчанию"
  - "загрузка интернет-ресурсов, настройка веб-приложений"
  - "модули для определенных протоколов"
  - "модули пользовательской проверки подлинности"
  - "получение данных, настройка веб-приложений"
  - "параметры конфигурации [платформа .NET Framework], веб-приложения"
  - "запрос данных из Интернета, настройка веб-приложений"
  - "запрос данных из Интернета, прокси-сервер по умолчанию"
  - "ответ на интернет-запрос, прокси-сервер по умолчанию"
  - "Интернет, настройка веб-приложений"
  - "Ответ на интернет-запрос, настройка веб-приложений"
  - "прокси-сервер по умолчанию"
  - "сетевые ресурсы, прокси-сервер по умолчанию"
  - "отправка данных, настройка веб-приложений"
  - "сетевые ресурсы, настройка веб-приложений"
  - "Интернет, прокси-сервер по умолчанию"
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Настройка веб-приложений
Элемент конфигурации [Элемент \<system.Net\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) содержащий сведения о конфигурации сети для приложений.  Использование элемента [Элемент \<system.Net\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) можно задать учетные записи\-посредники, установить параметры управления соединения и указать нестандартные модули проверки подлинности и запросов в приложении.  
  
 Элемент [Элемент \<defaultProxy\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) указывает учетную запись\-посредник, возвращаемый классом `GlobalProxySelection`.  Любое <xref:System.Net.HttpWebRequest>, который не имеет собственный набор свойств <xref:System.Net.HttpWebRequest.Proxy%2A> к конкретному значению по умолчанию использует прокси\-сервер.  Помимо установки прокси\-адрес, можно создать список адресов сервера, которые не используют прокси\-сервер, и можно указать, что прокси\-сервер не должен использоваться для локальных адресов.  
  
 Важно отметить, что параметры Microsoft Internet Explorer объединяются с параметрами конфигурации с последним с приоритетом.  
  
 В следующем примере устанавливается по умолчанию адрес прокси\-сервера в http:\/\/proxyserver указывает, что прокси\-сервер не должен использоваться для локальных адресов и указывает на то, что все запросы к серверам, расположенном в домене contoso.com должны выполняться обход прокси\-сервера.  
  
```  
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
  
 Используйте элемент [Элемент \<connectionManagement\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) чтобы настроить количество постоянных подключений, которые можно устанавливать к конкретному серверу или к всем остальным серверам.  В следующем примере показана настройка приложения для использования постоянных подключений к серверу www.contoso.com 2, 4 постоянных подключения к серверу с ip\-адресом 192.168.1.2 и одно постоянного соединения на все другие серверы.  
  
```  
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
  
 Нестандартные модули проверки подлинности настроитьы с элементом [Элемент \<authenticationModules\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md).  Нестандартные модули проверки подлинности должны реализовывать интерфейс <xref:System.Net.IAuthenticationModule>.  
  
 В следующем примере показана настройка пользовательского модуля проверки подлинности.  
  
```  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 Можно использовать элемент [Элемент \<webRequestModules\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) чтобы настроить приложение на использование пользовательские модули протокол\- определенные для запроса сведений из ресурсов в интернете.  Указанные модули должны реализовывать интерфейс <xref:System.Net.IWebRequestCreate>.  Возможно, придется переопределить используемый по умолчанию HTTP, HTTPS, и модули запроса файла, указывая пользовательский модуль в файле конфигурации, как показано в следующем примере.  
  
```  
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
  
## См. также  
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Схема параметров сети](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Элемент \<system.Net\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)