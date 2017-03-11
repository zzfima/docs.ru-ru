---
title: "Checked и Unchecked (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked - оператор [C#]"
  - "исключения [C#], проверка переполнения"
  - "операторы [C#], операторы checked и unchecked"
  - "проверка переполнения [C#]"
  - "операторы [C#], операторы checked и unchecked"
  - "unchecked - оператор [C#]"
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Checked и Unchecked (Справочник по C#)
Строка кода C\# может выполняться как в проверенном, так и в непроверенном контексте.  В проверенном контексте арифметическое переполнение создает исключение.  В непроверенном контексте арифметическое переполнение игнорируется, а результат усекается.  
  
-   [проверенный](../../../csharp/language-reference/keywords/checked.md) Укажите проверенный контекст.  
  
-   [непроверенный](../../../csharp/language-reference/keywords/unchecked.md) Укажите непроверенный контекст.  
  
 Если не выбран ни `checked`, ни `unchecked` контекст, используется контекст по умолчанию, который зависит от таких внешних факторов, как параметры компилятора.  
  
 Следующие операции не затрагиваются проверкой переполнения.  
  
-   Выражения, использующие следующие предопределенные операторы на целочисленных типах:  
  
     `++`  `--` — \(унарные\)   `+` —   `*` `/`  
  
-   Явные числовые преобразования между целочисленными типами.  
  
 [Проверенные](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) параметры компилятора позволяют указать проверенный или непроверенный контекст для всех целочисленных арифметических выражений, которые явно попадают в область действия ключевого слова `checked` или `unchecked`.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)