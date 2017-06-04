---
title: "Элемент &lt;qualifyAssembly&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<qualifyAssembly> - элемент"
  - "теги контейнеров, <qualifyAssembly> - элемент"
  - "qualifyAssembly - элемент"
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Элемент &lt;qualifyAssembly&gt;
Указывает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.  
  
## Синтаксис  
  
```  
  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`partialName`|Обязательный атрибут.<br /><br /> Неполное имя сборки в том виде, в котором оно указано в коде.|  
|`fullName`|Обязательный атрибут.<br /><br /> Полное имя сборки в том виде, в котором оно указано в глобальном кэше сборок.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположении сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 При вызове метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> с использованием неполного имени сборки среда CLR выполняет поиск сборки только в базовой папке приложения.  Для предоставления полных сведений о сборке \(имени, версии, маркера открытого ключа, а также языка и региональных параметров\) и для поиска сборки средой CLR в глобальном кэше сборок необходимо использовать элемент **\<qualifyAssembly\>** в файле конфигурации приложения.  
  
 Атрибут **fullName** должен включать четыре поля удостоверения сборки: имя, версию, маркер открытого ключа, а также язык и региональные параметры.  Атрибут **partialName** должен содержать неполную ссылку на сборку.  Достаточно указать текстовое имя сборки \(наиболее распространенный случай\), но можно также включить версию, маркер открытого ключа или язык и региональные параметры \(или любое сочетание четырех указанных параметров, но не все четыре параметра одновременно\).  Значение **partialName** должно соответствовать имени, указанному в вызове.  Например, нельзя указать в файле конфигурации `"math"` как значение атрибута **partialName** и вызвать в коде `Assembly.Load("math, Version=3.3.3.3")`.  
  
## Пример  
 В следующем примере показано логическое преобразование вызова `Assembly.Load("math")` в вызов `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [NIB: Partial Assembly References](http://msdn.microsoft.com/ru-ru/ec90f07a-398c-4306-9401-0fc5ff9cb59f)