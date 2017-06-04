---
title: "Элемент &lt;remove&gt; для schemeSettings (параметры URI) | Microsoft Docs"
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
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Элемент &lt;remove&gt; для schemeSettings (параметры URI)
Удаляет параметр схемы для имени схемы.  
  
## Синтаксис  
  
```  
  
      <remove   
   <name = "http|https"/>  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|name|Имя схемы, для которой применяется этот параметр.  Единственные поддерживаемые значения — name\="http"и имя\="https".|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<schemeSettings\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Указывает, как <xref:System.Uri> будет анализироваться по конкретным схемам.|  
  
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
 В следующем примере кода показана конфигурация, используемая классом <xref:System.Uri>, которая удаляет все параметры схемы для схемы HTTP.  
  
```  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## См. также  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)