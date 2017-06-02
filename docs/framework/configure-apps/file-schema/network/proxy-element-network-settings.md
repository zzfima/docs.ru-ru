---
title: "Элемент &lt;proxy&gt; (параметры сети) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<proxy> - элемент"
  - "proxy - элемент"
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# Элемент &lt;proxy&gt; (параметры сети)
Определение прокси\-сервера.  
  
## Синтаксис  
  
```  
  
      <proxy   
  autoDetect="true|false|unspecified"    
  bypassonlocal="true|false|unspecified"   
  proxyaddress="uriString"  
  scriptLocation="uriString"   
  usesystemdefault="true|false|unspecified "   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`autoDetect`|Указывает, обнаруживается ли прокси\-сервер автоматически.  Значение по умолчанию — `unspecified`.|  
|`bypassonlocal`|Указывает, используется ли прокси\-сервер для локальных ресурсов.  Адрес локального ресурса — это локальный адрес сервера \(http:\/\/localhost, http:\/\/loopback или http:\/\/127.0.0.1\) или URI без точки \(http:\/\/webserver\).  Значение по умолчанию — `unspecified`.|  
|`proxyaddress`|Указывает URI, используемый прокси\-сервером.|  
|`scriptLocation`|Указывает расположение скрипта конфигурации.|  
|`usesystemdefault`|Указывает, используются ли обозревателем Internet Explorer настройки прокси\-сервера.  Если используется значение `true`, следующие атрибуты переопределят настройки прокси\-сервера в обозревателе Internet Explorer.  Значение по умолчанию — `unspecified`.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает протокол HTTP прокси\-сервера.|  
  
## Текстовое значение  
  
## Заметки  
 Элемент `proxy` определяет прокси\-сервер для приложения.  Если этот элемент отсутствует в файле конфигурации, то платформа .NET Framework использует настройки прокси\-сервера из обозревателя Internet Explorer.  
  
 Значение атрибута `proxyaddress` должно иметь правильный формат URI.  
  
 Атрибут `scriptLocation` задает автоматическое определение размещения скрипта конфигурации прокси\-сервера.  Если в обозревателе Internet Explorer установлена опция **Использовать скрипт автоматической настройки**, класс <xref:System.Net.WebProxy> попытается обнаружить скрипт конфигурации \(обычно с названием Wpad.dat\).  
  
 Используйте атрибут `usesystemdefault` для приложений .NET Framework версии 1.1 при переходе на версию 2.0.  
  
 Если атрибут `proxyaddress` задает недопустимый прокси\-сервер по умолчанию, то возникает исключение.  Свойство <xref:System.Exception.InnerException%2A> при возникновении исключения должно содержать дополнительные сведения об основной причине ошибки.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода показано использование настроек прокси\-сервера из Internet Explorer, задание адреса прокси\-сервера и отмена использования прокси\-сервера для локальных адресов и домена contoso.com.  
  
```  
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
  
## См. также  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)