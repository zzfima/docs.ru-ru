---
title: "Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "заданные пользователем преобразования [C#]"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В данном примере определяются две структуры `RomanNumeral` и `BinaryNumeral` и демонстрируется преобразование между ними.  
  
## Пример  
 [!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## Отказоустойчивость  
  
-   В предыдущем примере оператор  
  
     [!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     выполняет преобразование из `RomanNumeral` в `BinaryNumeral`.  Поскольку прямого преобразования из `RomanNumeral` в `BinaryNumeral` не существует, используется приведение для преобразования из `RomanNumeral` в `int` и другое приведение для преобразования из `int` в `BinaryNumeral`.  
  
-   Кроме того, оператор  
  
     [!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     выполняет преобразование из `BinaryNumeral` в `RomanNumeral`.  Поскольку `RomanNumeral` определяет неявное преобразование из `BinaryNumeral`, приведение не требуется.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)