---
title: "Элемент &lt;assemblyBinding&gt; для &lt;runtime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> - элемент"
  - "assemblyBinding - элемент"
  - "теги контейнеров, <assemblyBinding> - элемент"
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Элемент &lt;assemblyBinding&gt; для &lt;runtime&gt;
Содержит сведения о перенаправлении версии сборки и о расположениях сборок.  
  
## Синтаксис  
  
```  
  
        <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**xmlns**|Обязательный атрибут.<br /><br /> Задает пространство имен XML, необходимое для привязки сборок.  Используйте строку urn:schemas\-microsoft\-com:asm.v1 в качестве значения.|  
|**appliesTo**|Задает версию среды выполнения, к которой применяется перенаправление сборки .NET Framework.  Этот необязательный атрибут содержит номер версии .NET Framework, к которой применяется перенаправление.  Если атрибут **appliesTo** не указан, элемент **\<assemblyBinding\>** применяется ко всем версиям платформы .NET Framework.  Атрибут **appliesTo** появился в .NET Framework 1.1; он игнорируется в .NET Framework 1.0.  Это означает, что все элементы **\<assemblyBinding\>** применяются при использовании платформы .NET Framework версии 1.0, даже если задан атрибут **appliesTo**.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<dependentAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Инкапсулирует политику привязки и расположение сборки.  Для каждой сборки используется один тег **\<dependentAssembly\>**.|  
|[\<probing\>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Задает вложенные папки, в которых среда CLR выполняет поиск при загрузке сборки.|  
|[\<publisherPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Указывает, применяет ли среда выполнения политику издателя.|  
|[\<qualifyAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## Пример  
 В следующем примере показан способ перенаправления одной версии сборки на другую и предоставлена база кода.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 В следующем примере показано, как использовать атрибут **appliesTo** для перенаправления привязки сборки платформы .NET Framework.  
  
```  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)