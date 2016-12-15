---
title: "/main (C# Compiler Options) | Microsoft Docs"
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
  - "/main"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-main compiler option [C#]"
  - "main compiler option [C#]"
  - "/main compiler option [C#]"
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /main (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Если метод **Main** содержится в нескольких классах, данный параметр указывает класс, который содержит точку входа в программу.  
  
## Синтаксис  
  
```  
/main:class  
```  
  
## Аргументы  
 `class`  
 Тип, в котором содержится метод **Main**.  
  
## Заметки  
 Если в компиляцию включено несколько типов с методом [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md), можно указать, какой тип содержит метод **Main**, который необходимо использовать в качестве точки входа в программу.  
  
 Этот параметр используется при компиляции EXE\-файлов.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Начальный объект**.  
  
     Сведения об установке этого параметра компилятора программным способом см. в описании свойства <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## Пример  
 Компиляция файлов `t2.cs` и `t3.cs`; указывается, что метод **Main** находится в классе `Test2`:  
  
```  
csc t2.cs t3.cs /main:Test2  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)