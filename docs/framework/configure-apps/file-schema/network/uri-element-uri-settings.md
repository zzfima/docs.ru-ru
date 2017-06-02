---
title: "Элемент &lt;Uri&gt; (параметры URI) | Microsoft Docs"
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
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;Uri&gt; (параметры URI)
Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб\-адреса, выраженные с использованием универсальных кодов ресурсов \(URI\).  
  
## Схема иерархии  
 [Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri\>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## Синтаксис  
  
```  
<uri>  
</uri>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Указывает, применяется ли синтаксический анализ IDN к именам доменов.|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Определение того, применяется ли анализ международного ресурса идентификаторов \(IRI\) к именам <xref:System.Uri>, а также следует ли применять правила синтаксического анализа IRI.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Указывает, как <xref:System.Uri> будет анализироваться по конкретным схемам.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[configuration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Содержит настройки всех пространств имен.|  
  
## Примечания  
 Элемент `uri` содержит настройки для членов класса <xref:System.Uri>, используемые в пространстве имен <xref:System.Net>.  В этих настройках задается поддержка для IRI и IDN.  
  
## Пример  
  
### Описание  
 В следующем примере кода показывается, как использовать класс <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN.  В примере также сбрасываются все параметры схем и добавляется поддержка отмены использования процентных escape\-символов для разделителей пути в схеме HTTP.  
  
### Код  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## См. также  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)