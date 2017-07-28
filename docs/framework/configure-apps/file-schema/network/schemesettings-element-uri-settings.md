---
title: "Элемент &lt;schemeSettings&gt; (параметры URI) | Microsoft Docs"
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
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Элемент &lt;schemeSettings&gt; (параметры URI)
Указывает, как <xref:System.Uri> будет анализироваться по конкретным схемам.  
  
## Синтаксис  
  
```  
  
      <schemeSettings>   
</schemeSettings>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет  
  
### Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[добавление;](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|Добавляет параметр схемы для имени схемы.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|Удаляет все существующие параметры схемы.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|Удаляет параметр схемы для имени схемы.|  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб\-адреса, выраженные с использованием универсальных кодов ресурсов \(URI\).|  
  
## Заметки  
 По умолчанию класс <xref:System.Uri?displayProperty=fullName> разэкранирует закодированные знаками процента разделители путей до выполнения сжатия пути.  Это было реализовано следующим образом, как механизм обеспечения безопасности от атак:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Если этот URI передается вниз к модулям, не обрабатывающим корректно символы, закодированные знаками процента, это может привести к выполнению сервером следующей команды:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 По этой причине класс <xref:System.Uri?displayProperty=fullName> сначала разэкранирует разделители пути, а затем применяет сжатие пути.  Результат передачи вредоносного URL\-адреса выше в конструктор класса <xref:System.Uri?displayProperty=fullName> приводит к следующему виду универсального кода ресурса \(URI\):  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Это поведение по умолчанию может быть изменено так, чтобы закодированные знаками процента разделители пути не разэкранировались; для этого к конкретной схеме следует применить параметр конфигурации schemeSettings.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода показывается конфигурация, используемая классом <xref:System.Uri> для поддержки отмены использования процентных escape\-символов для разделителей пути в схеме HTTP.  
  
```  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## Сведения об элементе  
  
|||  
|-|-|  
|Пространство имен|Система|  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## См. также  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)