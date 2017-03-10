---
title: "/target:library (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:library"
  - "target compiler options [C#], /target:library"
  - "/target compiler options [C#], /target:library"
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# /target:library (C# Compiler Options)
Параметр **\/target:library** заставляет компилятор создавать динамически подключаемую библиотеку \(DLL\), а не исполняемый файл \(EXE\).  
  
## Синтаксис  
  
```  
/target:library  
```  
  
## Заметки  
 Библиотека DLL создается с расширением DLL.  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Для создания DLL\-файла используются все файлы, указанные в командной строке до следующего параметра **\/out** или **\/target:module**.  
  
 При построении библиотеки DLL метод [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) не требуется.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 Компиляция файла `in.cs`, создание библиотеки `in.dll`:  
  
```  
csc /target:library in.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)