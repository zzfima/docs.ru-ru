---
title: "Оператор &amp;&amp; (справочник по C#) | Microsoft Docs"
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
  - "&&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&& - оператор [C#]"
  - "логическое AND - оператор [C#]"
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &amp;&amp; (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Условный оператор AND \(`&&`\) выполняет логическое AND своих операндов типа `bool`, но вычисляет только второй операнд при необходимости.  
  
## Заметки  
 Операция  
  
```  
x && y  
```  
  
 соответствует операции  
  
```  
x & y  
```  
  
 за исключением того, что если `x`существует  `false`"  `y` не вычисляется, поскольку результат операции И  `false` независимо от того, какие значения  `y` .  Это называется сокращенным вычислением.  
  
 Оператор условного AND не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.  
  
## Пример  
 В следующем примере выражение условия во втором `if` оператор оценивает только первый операнд, поскольку операндом возвращает  `false`.  
  
 [!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)