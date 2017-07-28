---
title: "Элемент &lt;assemblyBinding&gt; для &lt;configuration&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> - элемент"
  - "assemblyBinding - элемент"
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Элемент &lt;assemblyBinding&gt; для &lt;configuration&gt;
Определяет политику привязки сборок на уровне конфигурации.  
  
## Синтаксис  
  
```  
<assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1">  
</assemblyBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`xmlns`|Обязательный атрибут.<br /><br /> Задает пространство имен XML, необходимое для привязки сборок.  В качестве значения следует использовать строку "urn:schemas\-microsoft\-com:asm.v1".|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<linkedConfiguration\>](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)|Указание файла конфигурации, который следует включить.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<configuration\>](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Заметки  
 Элемент [Элемент \<linkedConfiguration\>](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) упрощает управление сборками компонентов, позволяя файлам конфигурации приложений помещать файлы конфигурации сборки в общеизвестных расположениям, а не дублировать параметры конфигурации сборки.  
  
> [!NOTE]
>  Элемент `<linkedConfiguration>` не поддерживается приложениями с параллельными манифестами Windows.  
  
## Пример  
 В следующем примере кода показано, как поместить файл конфигурации на локальный жесткий диск.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## См. также  
 [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md)