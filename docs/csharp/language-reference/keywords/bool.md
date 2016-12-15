---
title: "bool (Справочник по C#) | Microsoft Docs"
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
  - "bool_CSharpKeyword"
  - "bool"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "bool - ключевое слово [C#]"
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# bool (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `bool` является псевдонимом свойства <xref:System.Boolean?displayProperty=fullName>.  Оно используется для объявления переменных для хранения логических значений, [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md).  
  
> [!NOTE]
>  Если вам нужна логическая переменная, которая также должна иметь значение `null`, воспользуйтесь переменной `bool?`.  Дополнительные сведения см. в разделе [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
## Литералы  
 Переменной `bool` можно присвоить логическое значение.  Выражение, вычисляемое как `bool`, также может быть присвоено переменной `bool`.  
  
 [!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 Значение по умолчанию переменной `bool` — `false`.  Значение по умолчанию переменной `bool?` — `null`.  
  
## Преобразования  
 В C\+\+ значение типа `bool` может быть преобразовано в значение типа `int`; другими словами, значение `false` эквивалентно нулю, а значение `true` — ненулевым значениям.  В C\# не существует преобразования между типом `bool` и другими типами.  Например, следующий оператор `if` недопустим в C\#:  
  
 [!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например нулем.  
  
 [!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## Пример  
 В данном примере вводится символ с клавиатуры, а программа проверяет, является ли введенный символ буквой.  Если да, проверяется, является ли буква прописной или строчной.  Эти проверки выполняются с помощью свойств <xref:System.Char.IsLetter%2A>, и <xref:System.Char.IsLower%2A>, каждое из которых возвращает тип `bool`.  
  
 [!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)