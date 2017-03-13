---
title: "implicit (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "implicit"
  - "implicit_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "implicit - ключевое слово [C#]"
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# implicit (Справочник по C#)
Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа.  Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.  
  
## Пример  
 [!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 Неявное преобразование позволяет устранить ненужные операции приведения и повышает понятность кода.  Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты.  В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать.  Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`.  Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [явные](../../../csharp/language-reference/keywords/explicit.md)   
 [оператор](../../../csharp/language-reference/keywords/operator.md)   
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)