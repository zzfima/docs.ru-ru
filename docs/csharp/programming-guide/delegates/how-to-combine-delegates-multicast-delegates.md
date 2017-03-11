---
title: "Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "делегаты [C#], объединение"
  - "групповые делегаты [C#]"
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)
В этом примере описано создание множественных делегатов.  Полезным свойством объектов [delegate](../../../csharp/language-reference/keywords/delegate.md) является возможность назначения нескольких объектов одному экземпляру делегата с помощью оператора `+`.  Множественный делегат содержит список назначенных делегатов.  При вызове множественный делегат вызывает делегаты из списка по порядку.  Можно комбинировать только делегаты одного и того же типа.  
  
 Оператор `-` можно использовать для удаления делегатов\-компонентов из множественного делегата.  
  
## Пример  
 [!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#11)]  
  
## См. также  
 <xref:System.MulticastDelegate>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)