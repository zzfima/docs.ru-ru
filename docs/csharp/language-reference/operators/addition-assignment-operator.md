---
title: "Оператор += (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+= - оператор [C#]"
  - "оператор присвоения сложения (+=) [C#]"
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Оператор += (справочник по C#)
Оператор назначения сложения.  
  
## Заметки  
 Выражение, использующее оператор назначения `+=`, такое как  
  
```  
x += y  
```  
  
 , эквивалентно выражению  
  
```  
x = x + y  
```  
  
 за исключением того, что значение `x` вычисляется только один раз.  Значение [оператора \+](../../../csharp/language-reference/operators/addition-operator.md) зависит от типа `x` и `y` \(сложение для числовых операндов, соединение для строковых операндов и т. д.\).  
  
 Оператор `+=` нельзя перегрузить непосредственно, однако пользовательские типы могут перегрузить [оператор \+](../../../csharp/language-reference/operators/addition-operator.md) \(см. [оператор](../../../csharp/language-reference/keywords/operator.md)\).  
  
 Оператор `+=` также используется для указания метода, который вызывается в ответ на событие; такие методы называются обработчиками событий.  Использование оператора `+=` в этом контексте называется *подпиской на событие*.  Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  и [Делегаты](../../../csharp/programming-guide/delegates/index.md).  
  
## Пример  
 [!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)