---
title: "/target:module (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:module"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:module"
  - "target compiler options [C#], /target:module"
  - "/target compiler options [C#], /target:module"
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:module (C# Compiler Options)
Данный параметр указывает компилятору не создавать манифест сборки.  
  
## Синтаксис  
  
```  
/target:module  
```  
  
## Заметки  
 По умолчанию выходной файл, созданный при компиляции с этим параметром, имеет расширение .netmodule.  
  
 Файл, который не содержит манифест сборки, не может быть загружен средой CLR платформы .NET Framework.  Тем не менее, такой файл можно включить в манифест сборки с помощью параметра [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Если в процессе одной компиляции создается несколько модулей, [внутренние](../../../csharp/language-reference/keywords/internal.md) типы одного модуля будут доступны другим модулям в компиляции.  Если код одного модуля ссылается на внутренние \(`internal`\) типы другого модуля, то оба модуля должны быть включены в манифест сборки с помощью параметра **\/addmodule**.  
  
 Создание модулей не поддерживается в среде разработки Visual Studio.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 Компиляция файла `in.cs`, создание библиотеки `in.netmodule`:  
  
```  
csc /target:module in.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)