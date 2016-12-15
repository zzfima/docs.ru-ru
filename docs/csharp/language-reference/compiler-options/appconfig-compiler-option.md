---
title: "/appconfig (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/appconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/appconfig compiler option [C#]"
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /appconfig (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр компилятора **\/appconfig** позволяет приложению C\# задать расположение файла конфигурации приложения сборки \(app.config\) в среде CLR во время привязки сборки.  
  
## Синтаксис  
  
```  
/appconfig:file  
```  
  
## Аргументы  
 `file`  
 Обязательный.  Файл конфигурации приложения, содержащий параметры привязки сборки.  
  
## Заметки  
 Параметр **\/appconfig**, в частности, применяется в развернутых сценариях, когда в сборке имеются ссылки на версию .NET Framework и на версию .NET Framework для Silverlight конкретной базовой сборки одновременно.  Например, для конструктора XAML, написанного в Windows Presentation Foundation \(WPF\), может потребоваться ссылаться на оба рабочих стола WPF, для пользовательского интерфейса конструктора и для подмножества WPF, поставляемого с Silverlight.  Одна и та же сборка конструктора имеет доступ к обеим сборкам.  По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки.  
  
 Параметр компилятора **\/appconfig** позволяет указать расположение файла app.config, который отключает поведение по умолчанию с помощью тега `<supportPortability>`, как показано в следующем примере.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 Компилятор передает расположение файла в логику с привязкой сборки среды CLR.  
  
> [!NOTE]
>  При построении приложения с помощью Microsoft Build Engine \(MSBuild\) можно задать параметр компилятора **\/appconfig**, добавив тег свойства в CSPROJ\-файл.  Чтобы использовать файл app.config, уже заданный в проекте, добавьте тег свойства `<UseAppConfigForCompiler>` в CSPROJ\-файл и задайте для него значение `true`.  Чтобы указать другой файл app.config, добавьте тег свойства `<AppConfigForCompiler>` и задайте в качестве его значения расположение требуемого файла.  
  
## Пример  
 В следующем примере показан файл app.config, позволяющий приложению иметь ссылки на реализации .NET Framework и .NET Framework для реализации Silverlight любой сборки .NET Framework, существующей в обеих реализациях.  Параметр компилятора **\/appconfig** указывает расположение этого файла app.config.  
  
```  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## См. также  
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/ru-ru/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)   
 [Элемент \<supportPortability\>](../Topic/%3CsupportPortability%3E%20Element.md)   
 [C\# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)