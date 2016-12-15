---
title: "Оператор *= (Справочник по C#) | Microsoft Docs"
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
  - "*=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "*= - оператор [C#]"
  - "(*=) - оператор присвоения двоичного умножения [C#]"
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор *= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор присвоения двоичного умножения.  
  
## Заметки  
 Выражение, использующее оператор назначения `*=`, такое как  
  
```  
x *= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x * y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  [Оператор \*](../../../csharp/language-reference/operators/multiplication-operator.md) предопределен для числовых типов для выполнения умножения.  
  
 Оператор `*=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \*](../../../csharp/language-reference/operators/multiplication-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Пример  
 [!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)