---
title: "Элемент &lt;dependentAssembly&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<dependentAssembly> - элемент"
  - "теги контейнеров, <dependentAssembly> - элемент"
  - "dependentAssembly - элемент"
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Элемент &lt;dependentAssembly&gt;
Инкапсуляция политики привязки и расположения для каждой сборки.  Используйте один элемент `dependentAssembly` для каждой сборки.  
  
## Синтаксис  
  
```  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`assemblyIdentity`|Содержит идентификационные сведения о сборке.  Этот элемент должен включаться в каждый элемент `dependentAssembly`.|  
|`codeBase`|Указывает место поиска средой выполнения общей сборки, если она не была установлена на компьютер.|  
|`bindingRedirect`|Перенаправление одной версии сборки к другой.|  
|`publisherPolicy`|Указывает, будет ли среда выполнения применять политику издателя для этой сборки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположении сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Пример  
 В следующем примере показан способ инкапсуляции данных для двух сборок.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)