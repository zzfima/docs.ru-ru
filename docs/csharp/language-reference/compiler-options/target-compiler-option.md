---
title: "/target (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/target"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#]"
  - "/target compiler options [C#]"
  - "assemblies [C#], compiling"
  - "-target compiler options [C#]"
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр компилятора **\/target** можно указать в одной из четырех форм:  
  
 [\/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Создание EXE\-файла для приложений [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
 [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Создание EXE\-файла  
  
 [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Создание библиотеки кода.  
  
 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Создание модуля.  
  
 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Создание программы Windows.  
  
 [\/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Создание промежуточного файла .winmdobj.  
  
 Если не указывается параметр **\/target:module**, то использование параметра **\/target** приводит к включению манифеста сборки .NET Framework в выходной файл.  Дополнительные сведения см. в разделах [Сборки в среде CLR](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md) и [Общие атрибуты](../Topic/Common%20Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Манифест сборки помещается в первый выходной EXE\-файл в компиляции или в первый DLL\-файл, если выходной EXE\-файл не создается.  Например, в следующей командной строке манифест будет помещен в файл `1.exe`:  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 Компилятор создает только один манифест сборки для каждой компиляции.  В манифест сборки заносятся сведения о всех файлах, участвующих в компиляции.  Все выходные файлы, за исключением тех, которые были созданы с помощью параметра **\/target:module**, содержат манифест сборки.  При создании нескольких выходных файлов из командной строки создается только один манифест сборки, который помещается в первый выходной файл, указанный в командной строке.  Вне зависимости от типа первого выходного файла \(**\/target:exe**, **\/target:winexe**, **\/target:library** или **\/target:module**\), все остальные файлы, создаваемые в той же компиляции, должны быть модулями \(**\/target:module**\).  
  
 При создании сборки можно указать весь код или его часть как CLS\-совместимые с помощью атрибута <xref:System.CLSCompliantAttribute>.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [\/subsystemversion \(Specify minimum subsystem version\)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)