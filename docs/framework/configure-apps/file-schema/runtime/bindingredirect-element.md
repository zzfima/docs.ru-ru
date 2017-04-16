---
title: "Элемент &lt;bindingRedirect&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bindingRedirect> - элемент"
  - "bindingRedirect - элемент"
  - "теги контейнеров, <bindingRedirect> - элемент"
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;bindingRedirect&gt;
Перенаправляет одну версию сборки на другую.  
  
## Синтаксис  
  
```  
  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`oldVersion`|Обязательный атрибут.<br /><br /> Задает первоначально запрошенную версию сборки.  Формат номера версии сборки — *major.minor.build.revision*.  Допустимые значения для каждой части этого номера версии — от 0 до 65535.<br /><br /> Диапазон версий можно также задать в следующем формате:<br /><br /> *n.n.n.n \- n.n.n.n*|  
|`newVersion`|Обязательный атрибут.<br /><br /> Задает версию сборки, которая будет использоваться вместо первоначально запрошенной, в формате: *n.n.n.n*<br /><br /> Это значение может указывать более раннюю версию, чем `oldVersion`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|Отсутствуют||  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки.  Для каждой сборки используется только один элемент dependentAssembly.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 При сборке приложения .NET Framework с использованием сборки со строгим именем приложение во время выполнения по умолчанию будет использовать эту версию сборки, даже если доступна новая версия.  Однако приложение можно настроить для выполнения с новой версией сборки.  Подробные сведения об использовании этих файлов средой выполнения для определения нужной версии сборки см. в разделе [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Перенаправление нескольких версий сборок можно выполнить, включив в элемент `dependentAssembly` несколько элементов `bindingRedirect`.  Можно также выполнить перенаправление с более новой версии на более раннюю версию сборки.  
  
 Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.  Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.  Разрешение можно получить путем установки флага [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) в классе [SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  Дополнительные сведения см. в разделе [Разрешение безопасности перенаправления привязки сборок](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Пример  
 В следующем примере показан способ перенаправления одной версии сборки на другую.  
  
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
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)