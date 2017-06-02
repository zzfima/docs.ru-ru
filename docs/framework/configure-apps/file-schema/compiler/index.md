---
title: "Схема параметров поставщиков языков и компиляторов | Microsoft Docs"
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
helpviewer_keywords: 
  - "элементы конфигурации компилятора"
  - "элементы конфигурации компилятора, схема"
  - "параметры конфигурации компилятора"
  - "параметры конфигурации компилятора, схема"
  - "схема конфигурации [платформа .NET Framework], параметры компилятора"
  - "параметры конфигурации [платформа .NET Framework], компиляторы"
  - "поставщики языков"
  - "поставщики языков, схема параметров"
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Схема параметров поставщиков языков и компиляторов
В настройках компилятора и поставщика языка указываются элементы конфигурации компилятора для доступных поставщиков языков.  В каждом элементе конфигурации компилятора указывается имя типа поставщика кода, параметры компилятора, имена поддерживаемых языков, а также поддерживаемые расширения файлов.  
  
 В .NET Framework исходные настройки компилятора определены в файле конфигурации компьютера \(Machine.config\).  Разработчики и поставщики компиляторов могут добавлять настройки конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.  Для программного перечисления параметров конфигурации поставщика языка и компилятора на компьютере следует использовать метод <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>.  
  
 [Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<компиляторы\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<компилятор\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[\<компиляторы\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).|  
|[\<компилятор\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
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
 [Элемент \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)