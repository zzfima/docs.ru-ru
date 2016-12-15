---
title: "/recurse (C# Compiler Options) | Microsoft Docs"
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
  - "/recurse"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/recurse compiler option [C#]"
  - "recurse compiler option [C#]"
  - "-recurse compiler option [C#]"
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /recurse (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр "\/recurse" позволяет компилировать файлы исходного кода, содержащиеся во всех дочерних каталогах, либо в указанном каталоге \(dir\), либо в каталоге проекта.  
  
## Синтаксис  
  
```  
/recurse:[dir\]file  
```  
  
## Аргументы  
 `dir` \(необязательно\)  
 Папка, в которой следует начать поиск.  Если не указан, поиск начинается в каталоге проекта.  
  
 `file`  
 Файлы, которые нужно найти.  Допускается использование специальных знаков.  
  
## Заметки  
 Параметр **\/recurse** позволяет компилировать файлы исходного кода, содержащиеся во всех дочерних каталогах, либо в указанном каталоге \(`dir`\), либо в каталоге проекта.  
  
 Для компиляции всех файлов из папки проекта без использования параметра **\/recurse** в имени файла можно использовать специальные знаки.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## Пример  
 Выполняется компиляция всех файлов C\# в текущем каталоге:  
  
```  
csc *.cs  
```  
  
 Выполняется компиляция всех файлов C\# в каталоге "dir1\\dir2" и во всех вложенных каталогах, а также создается dir2.dll:  
  
```  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)