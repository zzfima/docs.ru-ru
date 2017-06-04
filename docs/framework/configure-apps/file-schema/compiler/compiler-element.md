---
title: "Элемент &lt;compiler&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compiler> - элемент"
  - "атрибуты конфигурации компилятора"
  - "элементы конфигурации компилятора, <compiler> - элемент"
  - "compiler - элемент"
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# Элемент &lt;compiler&gt;
Задает атрибуты конфигурации компилятора для поставщика языка.  
  
## Синтаксис  
  
```  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`compilerOptions`|Необязательный атрибут.<br /><br /> Задает дополнительные аргументы компилятора для использования при компиляции.  Значения атрибута `compilerOptions` обычно перечислены в разделе компилятора, посвященном параметрам компилятора.  Чтобы найти информацию о параметрах компилятора в документации по Visual Studio 2005, см. "параметры компилятора" в предметном указателе.|  
|`extension`|Обязательный атрибут.<br /><br /> Отображение списка разделенных точкой с запятой расширений имен файлов, используемых исходными файлами поставщика языка.  Например, ".cs".|  
|`language`|Обязательный атрибут.<br /><br /> Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языков.  Например, "c\#;cs;csharp".|  
|`type`|Обязательный атрибут.<br /><br /> Указывает имя типа поставщика языка, включая имя сборки, содержащее реализацию поставщика.  Имя типа должно соответствовать требованиям, описанным в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`warningLevel`|Необязательный атрибут.<br /><br /> Определяет уровень предупреждений компилятора по умолчанию; определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<providerOption\>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Задает атрибуты версии компилятора для поставщика языков.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|[Элемент \<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[Элемент \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; не содержит или содержит от одного и более элементов `<compiler>`.|  
  
## Заметки  
 Каждый элемент `<compiler>` задает атрибуты конфигурации компилятора для конкретного поставщика языка.  Поставщик расширяет класс <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> для конкретного языка; элемент `<compiler>` определяет настройки компилятора и генератора кода для поставщика языка.  
  
 В .NET Framework исходные настройки компилятора определены в файле конфигурации компьютера \(Machine.config\).  Разработчики и поставщики компиляторов могут добавлять настройки конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.  Для программного перечисления параметров конфигурации поставщика языка и компилятора на компьютере следует использовать метод <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName>.  
  
 Элементы компилятора в файле конфигурации приложения или файле веб\-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера.  Если для одного имени языка или расширения файла настроено более одной реализации поставщика, последняя подходящая конфигурация переопределяет всех ранее настроенных поставщиков для данного имени языка или расширения файла.  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
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