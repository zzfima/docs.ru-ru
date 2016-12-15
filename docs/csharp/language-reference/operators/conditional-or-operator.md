---
title: "Оператор || (Справочник по C#) | Microsoft Docs"
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
  - "||_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|| - оператор [C#]"
  - "OR - условный оператор (||) [C#]"
  - "OR - логический оператор [C#]"
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор || (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Условный\- оператор OR \(`||`\) выполняет a логически\- ИЛИ для своих операндов `bool`.  Если первый операнд имеет значение `true` операнд, то второй не вычисляется.  Если первый операнд имеет значение `false`, то второй оператор определяет, имеет ли выражение в целом к `true` или `false`.  
  
## Заметки  
 Операция  
  
```  
x || y  
```  
  
 соответствует операции  
  
```  
x | y  
```  
  
 за исключением того, что если `x``true`, то `y` не вычисляется, поскольку ИЛИ операция `true` независимо от значения `y`.  Это понятие как вычисление "короткого замыкания".  
  
 Условный\- ИЛИ оператор не может быть перегружатьо, но считается, что перегруженные версии стандартных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md), с некоторыми ограничениями, также перегрузками условной логических операторов.  
  
## Пример  
 В следующих примерах `||` оценивает выражение, которое использует только первый операнд.  Выражение, использующее `|`вычисляет оба операнда.  Во втором примере исключение во время выполнения возникает, если выполняются оба операнда.  
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)