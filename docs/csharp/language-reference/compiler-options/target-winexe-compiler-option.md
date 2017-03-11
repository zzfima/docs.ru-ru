---
title: "/target:winexe (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:winexe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/target compiler options [C#], /target:winexe"
  - "-target compiler options [C#], /target:winexe"
  - "target compiler options [C#], /target:winexe"
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:winexe (C# Compiler Options)
Параметр **\/target:winexe** указывает компилятору создавать исполняемый файл \(EXE\-файл\) программы Windows.  
  
## Синтаксис  
  
```  
/target:winexe  
```  
  
## Заметки  
 Исполняемый файл создается с расширением ЕХЕ.  Программа Windows предоставляет интерфейс пользователя из библиотеки .NET Framework или из API\-интерфейсов Win32.  
  
 Для создания консольного приложения используется параметр [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md).  
  
 Если не указано иное с помощью параметра [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
 Для создания программы Windows используются все файлы, указанные в командной строке до следующего параметра **\/out** или [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).  
  
 В файле исходного кода, который компилируется в EXE\-файл, должен содержаться один и только один метод **Main**.  Если код содержит несколько классов с методом **Main**, то указать, какой именно класс содержит метод **Main**, можно с помощью параметра [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 Компиляция файла `in.cs` в программу Windows:  
  
```  
csc /target:winexe in.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)