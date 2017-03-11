---
title: "do (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "do_CSharpKeyword"
  - "do"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "do - ключевое слово [C#]"
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# do (Справочник по C#)
Оператор `do` повторно выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.  Тело цикла должен быть заключен в фигурные скобки, `{}`, если он не состоит из одной инструкции.  В этом случае фигурные скобки необязательны.  
  
## Пример  
 В следующем примере операторы цикла `do-while` выполняются до тех пор, пока значение переменной `x` остается меньше 5.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/csharp/do_1.cs)]  
  
 В отличие от оператора [while](../../../csharp/language-reference/keywords/while.md), цикл `do-while` выполняется один раз до вычисления значения условного выражения.  
  
 В любой точке блока `do-while` цикл можно разорвать с помощью оператора [break](../../../csharp/language-reference/keywords/break.md).  Можно перейти непосредственно к оператору оценки выражения `while`, воспользовавшись оператором [continue](../../../csharp/language-reference/keywords/continue.md).  Если выражение `while` имеет значение true, выполнение продолжается с первого оператора цикла.  Если выражение имеет значение false, выполнение продолжается в первом операторе после цикла `do-while`.  
  
 Цикл `do-while` также можно разорвать посредством операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Выражение do\-while \(C\+\+\)](/visual-cpp/cpp/do-while-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)