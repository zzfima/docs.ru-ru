---
title: "explicit (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit - ключевое слово [C#]"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# explicit (Справочник по C#)
Ключевое слово `explicit` служит для объявления оператора преобразования пользовательского типа, который следует вызывать во время приведения.  Например, следующий оператор выполняет преобразование из класса Fahrenheit в класс Celsius.  
  
 [!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 Такой оператор можно вызвать следующим образом.  
  
 [!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 Оператор преобразования выполняет преобразование из исходного типа в тип назначения.  Оператор преобразования предоставляется исходным типом.  В отличие от неявного преобразования операторы явного преобразования вызываются с помощью приведения.  Если операция преобразования может вызвать исключения или потерю информации, необходимо пометить ее ключевым словом `explicit`.  Это позволит избежать скрытого вызова компилятором операции преобразования, которая может привести к непредсказуемым последствиям.  
  
 Если приведение пропустить, произойдет ошибка времени компиляции CS0266.  
  
 Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Пример  
 В следующем примере показаны классы `Fahrenheit` и `Celsius`, в каждом из которых определен оператор явного преобразования в другой класс.  
  
 [!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## Пример  
 В следующем примере определена структура `Digit`, представляющая один разряд.  Для преобразования типа `byte` в тип `Digit` определен оператор, но поскольку не все значения типа byte можно преобразовать в `Digit`, преобразование выполняется явным образом.  
  
 [!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [неявные](../../../csharp/language-reference/keywords/implicit.md)   
 [оператор](../../../csharp/language-reference/keywords/operator.md)   
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Определяемые пользователем цепного явные преобразования в C\#](http://go.microsoft.com/fwlink/?LinkId=112384)