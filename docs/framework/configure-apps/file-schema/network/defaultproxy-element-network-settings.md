---
title: "Элемент &lt;defaultProxy&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultProxy> - элемент"
  - "defaultProxy - элемент"
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# Элемент &lt;defaultProxy&gt; (параметры сети)
Настраивает прокси\-сервер протокола передачи гипертекста \(HTTP\).  
  
## Синтаксис  
  
```  
  
        <defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false"  
  <bypasslist> … </bypasslist>  
  <proxy> … </proxy>  
  <module> … </module>  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|`enabled`|Указывает, используется ли веб\-прокси.  Значение по умолчанию — `true`.|  
|`useDefaultCredentials`|Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб\-прокси.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси\-сервер.|  
|[модуль](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|Добавляет в приложение новый модуль прокси\-сервера.|  
|[прокси](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|Определяет прокси\-сервер.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[system.  net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## Заметки  
 Если элемент defaultProxy пуст, будут использоваться параметры прокси\-сервера из Internet Explorer.  Это поведение отличается от поведения в .NET Framework версии 1.1.  
  
 Исключение возникает, если элемент [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) задает тип закрытым, тип не является производным от класса <xref:System.Net.IWebProxy>, произошло исключение в конструкторе по умолчанию данного объекта или возникло исключение при получении прокси по умолчанию, заданного системой.  Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о корневой причине ошибки.  
  
## Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода используются значения по умолчанию из прокси\-сервера Internet Explorer, задается адрес прокси\-сервера и выполняется обход прокси\-сервера для локальных адресов и домена contoso.com.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)