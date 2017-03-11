---
title: "Оператор &lt;&lt;= (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<<= - оператор (назначение сдвига влево) [C#]"
  - "оператор назначения сдвига влево (<<=) [C#]"
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Оператор &lt;&lt;= (Справочник по C#)
Оператор присваивания сдвига влево.  
  
## Заметки  
 Выражение формы  
  
```  
x <<= y  
```  
  
 вычисляется как  
  
```  
x = x << y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Оператор [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md)сдвигает`x` влево на число бит, указанное в `y`.  
  
 Оператор `<<=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \<\<](../../../csharp/language-reference/operators/left-shift-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#12)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)