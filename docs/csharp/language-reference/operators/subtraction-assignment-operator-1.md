---
title: "Оператор -= (Справочник по C#) | Microsoft Docs"
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
  - "-=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-= - оператор (назначение вычитания) [C#]"
  - "оператор назначения вычитания (-=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор -= (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор назначения вычитания.  
  
## Заметки  
 Выражение, использующее оператор назначения `-=`, такое как  
  
```  
x -= y  
```  
  
 , эквивалентно выражению  
  
```  
x = x - y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Значение [оператора \-](../../../csharp/language-reference/operators/subtraction-operator.md) зависит от типа `x` и `y` \(вычитание для числовых операндов, удаление делегата для операндов, представляющих делегаты и т.д.\).  
  
 Оператор `-=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \-](../../../csharp/language-reference/operators/subtraction-operator.md) \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
 Оператор \-\= также используется в C\# для отмены подписки на событие.  Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## Пример  
 [!code-cs[csRefOperators#6](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-assignment-operator-1_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)