---
title: "Элемент &lt;system.codedom&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.codedom> - элемент"
  - "элементы конфигурации компилятора, <system.codedom> - элемент"
  - "system.codedom - элемент"
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Элемент &lt;system.codedom&gt;
Задает параметры конфигурации компилятора для доступных поставщиков языков.  
  
## Синтаксис  
  
```  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<компиляторы\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Заметки  
  
## .NET Framework версии 2.0  
 Элемент [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) содержит параметры конфигурации компилятора для поставщиков языков, установленных на компьютере дополнительно к поставщикам по умолчанию, установленным вместе с платформой .NET Framework, например <xref:Microsoft.CSharp.CSharpCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider>.  Элемент [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) может содержать любое число элементов [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md), включая ноль.  Каждый элемент [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 Разработчики и поставщики компиляторов могут добавлять параметры конфигурации в файл конфигурации компьютера \(Machine.config\) для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.  Используйте метод <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>, чтобы программно перечислить поставщиков языка по умолчанию и поставщиков языка, указанных в параметрах конфигурации компилятора на компьютере.  
  
> [!NOTE]
>  В платформе .NET Framework версий 1.0 и 1.1 поставщики языка по умолчанию, устанавливаемые вместе с платформой .NET Framework, указываются в элементе [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md).  В платформе .NET Framework версии 2.0 поставщики языка по умолчанию не указываются в элементе [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md), но могут быть перечислены с помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>.  
  
## .NET Framework версий 1.0 и 1.1  
 Элемент [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) содержит параметры конфигурации компилятора для поставщиков языка на компьютере.  Элемент [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) может содержать любое число элементов [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md), включая ноль.  Каждый элемент [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 В .NET Framework исходные настройки компилятора определены в файле конфигурации компьютера \(Machine.config\).  Разработчики и поставщики компиляторов могут добавлять настройки конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.  Для программного перечисления параметров конфигурации поставщика языка и компилятора на компьютере следует использовать метод <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>.  
  
## Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации компьютера и в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показана типичная конфигурация компилятора.  
  
```  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
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