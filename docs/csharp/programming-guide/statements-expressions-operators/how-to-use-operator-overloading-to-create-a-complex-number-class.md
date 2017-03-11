---
title: "Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "классы [C#], перегрузка операторов"
  - "комплексные числа [C#]"
  - "перегрузка операторов [C#], комплексные числа"
  - "перегрузка операторов [C#], использование для создания классов"
  - "операторы [C#], использование перегрузки для создания класса комплексных чисел"
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)
В следующем примере показано, как использовать перегрузку операторов при определении класса комплексных чисел `Complex`, в котором реализовано комплексное сложение.  Для отображения действительной и мнимой частей чисел и результатов сложения в программе используется переопределенная версия метода `ToString`.  
  
## Пример  
 [!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-use-operator-over_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [оператор](../../../csharp/language-reference/keywords/operator.md)   
 [Why are overloaded operators always static in C\#?](http://go.microsoft.com/fwlink/?LinkId=112383)