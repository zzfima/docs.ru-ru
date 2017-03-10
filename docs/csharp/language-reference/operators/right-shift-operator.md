---
title: "Оператор &gt;&gt; (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">> - оператор [C#]"
  - "оператор сдвига вправо (>>) [C#]"
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Оператор &gt;&gt; (Справочник по C#)
Оператор сдвига вправо \(`>>`\) сдвигает первый операнд вправо в соответствии с количеством бит, заданным вторым операндом.  
  
## Заметки  
 Если тип первого операнда — [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) \(32\-разрядное число\), начало сдвига задается пятью младшими разрядами второго операнда \(второй операнд & 0x1f\).  
  
 Если тип первого операнда — [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) \(64\-разрядное число\), начало сдвига задается пятью младшими разрядами второго операнда \(второй операнд & 0x3f\).  
  
 Если тип первого операнда — [int](../../../csharp/language-reference/keywords/int.md) или [long](../../../csharp/language-reference/keywords/long.md), сдвиг вправо является арифметическим сдвигом \(пустым старшим разрядам задан знаковый бит\).  Если тип первого операнда — [init](../../../csharp/language-reference/keywords/uint.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md), сдвиг вправо является логическим сдвигом \(старшие разряды заполняются нулями\).  
  
 Определенные пользователем типы могут вызвать перегрузку оператора `>>`; тип первого операнда должен быть определен пользователем, а тип второго должен быть [int](../../../csharp/language-reference/keywords/int.md).  Дополнительные сведения см. [оператор](../../../csharp/language-reference/keywords/operator.md).  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#26)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)