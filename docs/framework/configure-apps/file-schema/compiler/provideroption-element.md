---
title: "Элемент &lt;providerOption&gt; | Microsoft Docs"
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
  - "provideroption"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<provideroption> - элемент"
  - "provideroption - элемент"
  - "providerOptions"
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: 22
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# Элемент &lt;providerOption&gt;
Задает атрибуты версии компилятора для доступных поставщиков языков.  
  
## Синтаксис  
  
```  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`name`|Обязательный атрибут.<br /><br /> Задает имя параметра, например "CompilerVersion".|  
|`value`|Обязательный атрибут.<br /><br /> Задает значение параметра, например "v3.5".|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями платформы .NET Framework.|  
|[Элемент \<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[Элемент \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; не содержит или содержит от одного и более элементов `<compiler>`.|  
|[Элемент \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
## Заметки  
 В .NET Framework версии 3.5 поставщики кода CodeDOM могут поддерживать специфичные для поставщика параметры, используя элемент `<providerOption>`.  
  
 .NET Framework 3.5 включает модифицированные сборки .NET Framework 2.0 и обеспечивает новые сборки версии 3.5, которые содержат новые типы.  Поставщики кодов Microsoft C\# и Visual Basic содержатся в сборках платформы .NET Framework 2.0, но были обновлены, чтобы поддерживать компиляторы версии 3.5.  По умолчанию обновленные поставщики кода генерируют код для компиляторов версии 2.0.  Элемент `<providerOption>` можно использовать для смены версии целевого компилятора на 3.5.  Для этого укажите "CompilerVersion" в атрибуте `name` и "v3.5" в атрибуте `value`.  Перед номером версии нужно добавить латинскую букву "v" в нижнем регистре.  
  
 Можно делать спецификацию версию глобальной, добавив элемент `<providerOption>` в файл .NET Framework 2.0 Machine.config или в корневой файл Web.config file.  Если обновляется версия по умолчанию компилятора до версии 3.5 в файле Machine.config, то можно вернуть ее к версии 2.0, на которой создано приложение, используя элемент `<providerOption>` в файле конфигурации приложения.  
  
 Реализации поставщика кода CodeDOM могут обрабатывать пользовательские параметры за счет конструктора, который принимает параметр `providerOptions` типа <xref:System.Collections.Generic.IDictionary%602>.  
  
## Пример  
 В следующем примере показано как указать, что должна использоваться версия 3.5 кода C\# поставщика.  
  
```  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## См. также  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Элемент \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)   
 [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)   
 [Элемент compiler для элемента compilers для элемента compilation \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)