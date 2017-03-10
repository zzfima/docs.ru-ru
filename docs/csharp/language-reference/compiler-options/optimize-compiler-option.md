---
title: "/optimize (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/optimize"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/optimize compiler option [C#]"
  - "-o compiler option [C#]"
  - "optimize compiler option [C#]"
  - "/o compiler option [C#]"
  - "-optimize compiler option [C#]"
  - "compiler optimization [C#]"
  - "o compiler option [C#]"
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /optimize (C# Compiler Options)
Параметр **\/optimize** позволяет включать или отключать оптимизацию, которая выполняется компилятором для уменьшения размеров выходного файла, повышения его производительности и эффективности.  
  
## Синтаксис  
  
```  
/optimize[+ | -]  
```  
  
## Заметки  
 **\/optimize** также заставляет среду CLR выполнять оптимизацию кода во время выполнения.  
  
 По умолчанию оптимизация отключена.  Задайте **\/optimize\+** для включения оптимизации.  
  
 При построении модуля, который будет использован сборкой, используйте параметр **\/optimize** сборки.  
  
 **\/o** является короткой формой **\/optimize**.  
  
 Параметры **\/optimize** и [\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) можно объединять.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Измените значение свойства **Оптимизация кода**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## Пример  
 Компиляция `t2.cs` и включение оптимизации компилятором:  
  
```  
csc t2.cs /optimize  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)