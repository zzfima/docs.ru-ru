---
title: "Оператор ^= (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^= - оператор [C#]"
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Оператор ^= (справочник по C#)
Оператор назначения исключающего OR.  
  
## Заметки  
 Выражение формы  
  
```  
x ^= y  
```  
  
 вычисляется как  
  
```  
x = x ^ y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Оператор [^ operator](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего OR для интегральных операндов и логическую операцию исключающего OR для [логических](../../../csharp/language-reference/keywords/bool.md) операндов.  
  
 Оператор "^\=" нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)