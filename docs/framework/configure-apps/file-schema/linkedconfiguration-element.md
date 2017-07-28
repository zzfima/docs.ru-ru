---
title: "Элемент &lt;linkedConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<linkedConfiguration> - элемент"
  - "файлы конфигурации [платформа .NET Framework], связанные файлы конфигурации"
  - "включение файлов конфигурации"
  - "связанные файлы конфигурации"
  - "linkedConfiguration - элемент"
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Элемент &lt;linkedConfiguration&gt;
Указание файла конфигурации, который следует включить.  
  
## Синтаксис  
  
```  
<linkedConfiguration  
   href="URL of linked configuration file"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`href`|URL\-адрес файла конфигурации, который необходимо включить.  Для атрибута `href` поддерживается только один формат — "file:\/\/".  Поддерживаются локальные файлы и файлы UNC.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<assemblyBinding\>](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Определяет политику привязки сборок на уровне конфигурации.|  
  
## Заметки  
 Элемент `<linkedConfiguration>` упрощает обслуживание для сборок компонентов.  Если одно или несколько приложений используют сборку, файл конфигурации которой находится в общеизвестном местоположении, файлы конфигурации приложений, использующих сборку, могут включать файл конфигурации сборки с помощью элемента `<linkedConfiguration>` и не использовать непосредственное включение информации о конфигурации.  При обслуживании сборки компонентов обновление общего файла конфигурации позволяет обновить информацию о конфигурации для всех приложений, использующих эту сборку.  
  
> [!NOTE]
>  Элемент `<linkedConfiguration>` не поддерживается приложениями с параллельными манифестами Windows.  
  
 Для связанных файлов конфигурации действуют следующие правила.  
  
-   Настройки включенного файла конфигурации затрагивают только политику привязки загрузчика и используются только загрузчиком.  Включенные файлы конфигурации могут содержать настройки, не имеющие отношения к политикам привязки, но эти настройки не используются.  
  
-   Для атрибута `href` поддерживается только один формат — "file:\/\/".  Поддерживаются локальные файлы и файлы UNC.  
  
-   Ограничение числа связанных конфигураций для файла конфигурации отсутствует.  
  
-   Все связанные файлы конфигурации объединяются в один файл; схожим образом работает директива `#include` в C\/C\+\+.  
  
-   Элемент `<linkedConfiguration>` разрешен только в файлах конфигурации приложений; в файле Machine.config этот элемент игнорируется.  
  
-   Обнаружены и удалены циклические ссылки.  Если элементы `<linkedConfiguration>` ряда файлов конфигурации образуют цикл, этот цикл обнаруживается и обрывается.  
  
## Пример  
 В следующем примере кода показано, как можно включить файл конфигурации с локального жесткого диска.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## См. также  
 [Элемент \<assemblyBinding\>](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
 [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md)