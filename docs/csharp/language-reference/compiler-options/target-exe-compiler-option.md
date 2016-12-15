---
title: "/target:exe (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/exe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#], /target:exe"
  - "/target compiler options [C#], /target:exe"
  - "-target compiler options [C#], /target:exe"
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:exe (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/target:exe** предписывает компилятору создавать исполняемое \(EXE\) консольное приложение.  
  
## Синтаксис  
  
```  
/target:exe  
```  
  
## Заметки  
 Параметр **\/target:exe** действует по умолчанию.  Исполняемый файл создается с расширением ЕХЕ.  
  
 Используйте параметр [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) для создания исполняемого файла программы Windows.  
  
 Если не указано иное с помощью параметра [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
 Для создания EXE\-файла используются все файлы, указанные в командной строке до следующего параметра **\/out** или **\/target:module**.  
  
 В файле исходного кода, который компилируется в EXE\-файл, должен содержаться один и только один метод **Main**.  Если код содержит несколько классов с методом **Main**, то указать, какой класс содержит метод **Main**, можно с помощью параметра компилятора [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Тип выходных данных**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 В каждой из представленных ниже команд командной строки выполняется компиляция файла `in.cs` для создания файла `in.exe`:  
  
```  
csc /target:exe in.cs  
csc in.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)