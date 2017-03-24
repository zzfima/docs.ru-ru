---
title: "Оператор &gt;&gt;= (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">>= - оператор (назначение сдвига вправо) [C#]"
  - "оператор назначения сдвига вправо (>>=) [C#]"
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Оператор &gt;&gt;= (Справочник по C#)
Оператор присваивания сдвига вправо.  
  
## Заметки  
 Выражение формы  
  
```  
x >>= y  
```  
  
 вычисляется как  
  
```  
x = x >> y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на значение, заданное `y`.  
  
 Оператор \>\>\= нельзя перегрузить непосредственно, однако определенные пользователем типы могут перегрузить [оператор \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) \(см.[оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)