---
title: "Элемент &lt;httpWebRequest&gt; (параметры сети) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<httpWebRequest> - элемент"
  - "httpWebRequest - элемент"
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Элемент &lt;httpWebRequest&gt; (параметры сети)
Настраивает параметры веб\-запроса.  
  
## Синтаксис  
  
```  
  
      <httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`maximumResponseHeadersLength`|Задает максимальную длину заголовка ответа в килобайтах.  Значение по умолчанию — 64.  Значение \-1 показывает, что на длину заголовков ответа не накладывается никаких ограничений.|  
|`maximumErrorResponseLength`|Задает максимальную длину ответа с сообщением об ошибке в килобайтах.  Значение по умолчанию — 64.  Значение \-1 показывает, что на ответ с сообщением об ошибке не накладывается никаких ограничений.|  
|`maximumUnauthorizedUploadLength`|Задает максимальный объем данных, передаваемых в ответ на код ошибки доступа \(в байтах\).  Значение по умолчанию — \-1.  Значение \-1 указывает на отсутствие ограничений.|  
|`useUnsafeHeaderParsing`|Указывает, используется ли разбор небезопасных заголовков.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
 По умолчанию платформа .NET Framework при анализе URI точно следует RFC 2616.  Некоторые ответы сервера могут содержать управляющие символы в запрещенных полях. Это приводит к тому, что метод <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> вызывает исключение <xref:System.Net.WebException>.   Если **useUnsafeHeaderParsing** имеет значение **true**, то исключение <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> создано не будет. Тем не менее приложение будет уязвимо для некоторых форм атак на анализатор URI\-адресов.  Оптимальным решением будет такая настройка сервера, при которой управляющие символы не включаются в ответ.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 Следующий пример кода показывает, как задать большую чем обычно длину заголовка.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## См. также  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)