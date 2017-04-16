---
title: "Элемент &lt;iriParsing&gt; (параметры URI) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;iriParsing&gt; (параметры URI)
Указывает, применяется ли синтаксический анализ международного имени ресурса \(IRI\) к <xref:System.Uri>, а также следует ли применять правила синтаксического анализа IRI.  
  
## Схема иерархии  
 [Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Элемент \<Uri\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<iriParsing\>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## Синтаксис  
  
```  
<idn  
  enabled="true|false"  
/idn>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|`enabled`|Указание того, включен ли анализ IRI.  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб\-адреса, выраженные с использованием универсальных кодов ресурсов \(URI\).|  
  
## Примечания  
 Существующий класс <xref:System.Uri> был расширен в .NET Framework 3.5, 3.0 SP1 и 2.0 SP1 для поддержки международных идентификаторов ресурсов \(IRI\) и международных доменных имен \(IDN\).  Пользователи не увидят никаких функциональных изменений в сравнении с .NET Framework 2.0, если специально не включат поддержку IRI и IDN.  Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Для включения поддержки IRI требуется внести два изменения.  
  
1.  Добавить следующую строку в файл machine.config в каталоге .NET Framework 2.0.  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Указать, применяются ли правила анализа IRI.  Это можно сделать в файле machine.config или в файле app.config.  
  
 При включении синтаксического анализа IRI \(iriParsing enabled \= `true`\) нормализация и проверка символов выполняются в соответствии с новейшими правилами IRI в стандарте RFC 3987.  По умолчанию используется значение `false`, а нормализация и проверка символов выполняются в соответствии со стандартами RFC 2396 и RFC 3986 \(для литералов IPv6\).  
  
### Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
  
### Описание  
 В следующем примере кода показывается, как использовать класс <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN.  
  
### Код  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## См. также  
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)