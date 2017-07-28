---
title: "Элемент &lt;idn&gt; (параметры URI) | Microsoft Docs"
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
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;idn&gt; (параметры URI)
Указывает, применяется ли синтаксический анализ международного доменного имени \(IDN\) к имени домена.  
  
## Схема иерархии  
 [Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [Элемент \<Uri\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn\>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## Синтаксис  
  
```  
<idn  
  enabled="All|AllExceptIntranet|None"  
/idn>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|`enabled`|Задает, применяется ли синтаксический анализ международного доменного имени к имени домена. Значение по умолчанию — нет.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб\-адреса, выраженные с использованием универсальных кодов ресурсов \(URI\).|  
  
## Примечания  
 Существующий класс <xref:System.Uri> был расширен в .NET Framework 3.5, 3.0 SP1 и 2.0 SP1 поддержкой международных идентификаторов ресурсов \(IRI\) и международных доменных имен \(IDN\).  Пользователи не увидят никаких функциональных изменений в сравнении с .NET Framework 2.0, если специально не включат поддержку IRI и IDN.  Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Для включения поддержки IRI требуется внести два изменения.  
  
1.  Добавить следующую строку в файл machine.config в каталоге .NET Framework 2.0.  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Указать, применяется ли синтаксический анализ международного доменного имени к имени домена и должны ли применяться правила синтаксического анализа IRI.  Это можно сделать в файле machine.config или в файле app.config.  
  
 Имеются три возможных значения для IDN в зависимости от используемых DNS\-серверов:  
  
-   idn enabled \= All  
  
     При этом значении имена доменов из Юникода будут преобразовываться в их эквиваленты в Punycode \(IDN\-имена\).  
  
-   idn enabled \= AllExceptIntranet  
  
     При этом значении все находящиеся за пределами локальной интрасети имена доменов в кодировке Юникод, будут преобразовываться в их эквиваленты в Punycode \(IDN\-имена\).  В этом случае для обработки международных имен в локальной интрасети, используемые для интрасети DNS\-серверы должны поддерживать разрешение имен в Юникоде.  
  
-   idn enabled \= None  
  
     При этом значении имена доменов в Юникоде не будут преобразовываться в их эквиваленты в Punycode.  Это значение по умолчанию, которое совместимо с поведением .NET Framework 2.0.  
  
 Включение IDN все метки в Юникоде в именах доменов будут преобразовываться в их эквиваленты в Punycode.  Имена в Punycode содержат только символы ASCII и всегда начинаются с приставки xn\-\-.  Это сделано для того, чтобы поддерживать существующие DNS\-серверы в интрасети, так как большинство DNS\-серверов поддерживает только символы ASCII \(см. RFC 3940\).  
  
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
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)