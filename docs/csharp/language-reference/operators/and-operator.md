---
title: "Оператор &amp; (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "побитовый оператор AND [C#]"
  - "амперсанд - оператор (&) [C#]"
  - "& - оператор [C#]"
  - "AND - оператор (&) [C#]"
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Оператор &amp; (Справочник по C#)
Оператор & может функционировать как унарный или как бинарный оператор.  
  
## Заметки  
 Унарный оператор & возвращает адрес своего операнда \(требуется [небезопасный](../../../csharp/language-reference/keywords/unsafe.md) контекст\).  
  
 Бинарные операторы & являются предопределенными для целых типов и `bool`.  Для целых типов оператор & выполняет битовую операцию логического умножения операндов.  Для операндов `bool` оператор & выполняет операцию логического умножения операндов, то есть, если один или оба оператора — `true`, результатом будет являться значение `true`.  
  
 Оператор `&` вычисляет оба оператора независимо от значения первого из них.  Например:  
  
 [!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Типы, определенные пользователем, могут вызвать перегрузку бинарного оператора `&` \(см [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Операции над целыми типами обычно разрешены в перечислениях.  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)