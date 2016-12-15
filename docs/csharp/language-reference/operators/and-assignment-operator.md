---
title: "Оператор &amp;= (справочник по C#) | Microsoft Docs"
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
  - "&=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&= - оператор [C#]"
  - "оператор присваивания AND (&=) [C#]"
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор &amp;= (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор назначения AND.  
  
## Заметки  
 Выражение, использующее оператор назначения `&=`, например  
  
```  
x &= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x & y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор &](../../../csharp/language-reference/operators/and-operator.md) выполняет битовую логическую операцию AND для целых операндов и логическую операцию OR для операндов `bool`.  
  
 Оператор `&=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить двоичный [оператор &](../../../csharp/language-reference/operators/and-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)