---
title: "Элемент &lt;compilers&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compilers> - элемент"
  - "элементы конфигурации компилятора, <compilers> - элемент"
  - "compilers - элемент"
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;compilers&gt;
Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).  
  
## Синтаксис  
  
```  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|[Элемент \<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
  
## Заметки  
 Элемент [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) содержит параметры конфигурации компилятора для поставщиков языков на компьютере.  Каждый элемент [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 В .NET Framework исходные настройки компилятора и поставщика языка определены в файле конфигурации компьютера \(Machine.config\).  Разработчики и поставщики компиляторов могут добавлять настройки конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>.  Для программного перечисления параметров конфигурации поставщика языка и компилятора на компьютере следует использовать метод <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>.  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показан типичный элемент конфигурации компилятора.  
  
```  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## См. также  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Схема параметров поставщиков языков и компиляторов](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)   
 [Элемент \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)