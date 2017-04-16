---
title: "Элемент &lt;assemblyIdentity&gt; для &lt;runtime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyIdentity> - элемент"
  - "assemblyIdentity - элемент"
  - "теги контейнеров, <assemblyIdentity> - элемент"
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Элемент &lt;assemblyIdentity&gt; для &lt;runtime&gt;
Содержит идентификационные сведения о сборке.  
  
## Синтаксис  
  
```  
  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя сборки.|  
|`culture`|Необязательный атрибут.<br /><br /> Строка, задающая язык и страну или регион сборки.|  
|`publicKeyToken`|Необязательный атрибут.<br /><br /> Шестнадцатеричное значение, указывающее строгое имя сборки.|  
|`processorArchitecture`|Необязательный атрибут.<br /><br /> Одно из значений "x86", "amd64", "msil" или "ia64", задающих архитектуру процессора для сборки, содержащей код для определенного процессора.  Эти значения нечувствительны к регистру.  Если этому атрибуту присваивается любое другое значение, весь элемент `<assemblyIdentity>` игнорируется.  См. раздел <xref:System.Reflection.ProcessorArchitecture>.|  
  
## Атрибут processorArchitecture  
  
|Значение|Описание|  
|--------------|--------------|  
|`amd64`|Только для 64\-разрядных процессоров AMD.|  
|`ia64`|Только для 64\-разрядных процессоров Intel.|  
|`msil`|Код нейтрален по отношению к процессору и разрядности слова.|  
|`x86`|Для 32\-разрядного процессора Intel — реального либо среды Windows on Windows \(WOW\) на 64\-разрядной платформе.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположении сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`dependentAssembly`|Инкапсуляция политики привязки и расположения для каждой сборки.  Используйте один элемент `<dependentAssembly>` для каждой сборки.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Каждый элемент **\<dependentAssembly\>** должен иметь один дочерний элемент **\<assemblyIdentity\>**.  
  
 Если присутствует атрибут `processorArchitecture`, элемент `<assemblyIdentity>` относится только к сборке для соответствующей архитектуры процессора.  Если атрибут `processorArchitecture` отсутствует, элемент `<assemblyIdentity>` может относиться к сборке для любой архитектуры процессора.  
  
 В следующем примере показан файл конфигурации для двух сборок с одним и тем же именем, предназначенных для двух различных архитектур процессоров и не синхронизированных по версиям.  При выполнении приложения на платформе x86 действует первый элемент `<assemblyIdentity>`, а второй игнорируется.  При выполнении приложения на платформе, отличной от x86 или ia64, оба элемента игнорируются.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Если файл конфигурации содержит элемент `<assemblyIdentity>` без атрибута `processorArchitecture` и не содержит элемент, соответствующий используемой платформе, используется элемент без атрибута `processorArchitecture`.  
  
## Пример  
 В следующем примере показан способ предоставления сведений о сборке.  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)