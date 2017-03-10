---
title: "Оператор /= (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (оператор назначения деления) [C#]"
  - "оператор назначения деления (/=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Оператор /= (Справочник по C#)
Оператор назначения деления.  
  
## Заметки  
 Выражение, использующее оператор назначения `/=`, такое как  
  
```  
x /= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x / y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор \/](../../../csharp/language-reference/operators/division-operator.md) предопределен для числовых типов для выполнения деления.  
  
 Оператор `/=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \/](../../../csharp/language-reference/operators/division-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Для всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.  
  
## Пример  
 [!code-cs[csRefOperators#5](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#5)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)