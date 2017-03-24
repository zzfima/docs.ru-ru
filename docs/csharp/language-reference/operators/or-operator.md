---
title: "Оператор | (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "|_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "| - оператор [C#]"
  - "бинарный оператор (|) [C#]"
  - "оператор побитового OR [C#]"
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Оператор | (Справочник по C#)
Binary        `|`  являются предопределенными для целочисленных типов и `bool`.  Для целочисленных типов  `|`вычисляет результат битовой операции ИЛИ для своих операндов.  Для операндов `bool` `|` выполняет операцию логического ИЛИ для своих операндов, то есть результатом будет значение `false` тогда и только тогда, когда оба операнда имеют значение `false`.  
  
## Заметки  
 Пользовательские типы могут перегрузить оператор          `|` \(см. [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)