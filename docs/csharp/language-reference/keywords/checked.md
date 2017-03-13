---
title: "checked (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "checked_CSharpKeyword"
  - "checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked - ключевое слово [C#]"
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# checked (Справочник по C#)
Ключевое слово `checked` используется для явного включения проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.  
  
 По умолчанию выражение, содержащее только константные значения, вызывает ошибку компилятора в том случае, если результат его вычисления выходит за допустимые пределы значений конечного типа.  Если выражение содержит одно или несколько неконстантных значений, компилятор не выполняет проверку переполнения.  Вычисление выражения, присвоенного переменной `i2` в следующем примере, не вызывает ошибку компилятора.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 По умолчанию эти неконстантные выражения также не проверяются на переполнение во время выполнения, и они не создают исключений переполнения.  В предыдущем примере в качестве суммы двух положительных целых чисел выводится значение \-2 147 483 639.  
  
 Проверку переполнения можно включить посредством параметров компилятора, настройки среды или использования ключевого слова `checked`.  В следующих примерах демонстрируется использование выражения `checked` или блока `checked` для обнаружения переполнения, возникающего в результате предыдущего сложения во время выполнения.  В обоих примерах создается исключение переполнения.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 Для запрета проверки переполнения можно использовать ключевое слово [unchecked](../../../csharp/language-reference/keywords/unchecked.md).  
  
## Пример  
 В этом примере демонстрируется включение проверки переполнения во время выполнения посредством ключевого слова `checked`.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Checked и Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)