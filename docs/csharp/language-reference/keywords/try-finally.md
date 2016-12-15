---
title: "try-finally (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "finally"
  - "finally_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "finally - ключевое слово [C#]"
  - "try-finally - оператор [C#]"
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# try-finally (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

С помощью блока `finally` можно выполнить очистку всех ресурсов, выделенных в блоке [try](../../../csharp/language-reference/keywords/try-catch.md), и можно запускать код даже при возникновении исключения в блоке `try`.  Как правило, операторы блока `finally` выполняются, когда элемент управления покидает оператор `try`.  Передача управления может возникать в результате выполнения нормального выполнения, `break`, `continue`, `goto` или оператора `return`, или распространения исключения из оператора `try`.  
  
 Внутри обработанного исключения гарантируется выполнение соответствующий блок `finally`.  Однако если исключение не обработано, то выполнение блока `finally` зависит от того, как запускается операция развертывания исключения.  Это, в свою очередь, зависит от способа настройки компьютера.  Дополнительные сведения см. в статье [Обработка необработанных исключений в CLR](http://go.microsoft.com/fwlink/?LinkId=128371).  
  
 Как правило, когда необработанное исключение завершения работы приложения, выполняется ли блок `finally` не имеет значения.  Однако если имеются операторы в блоке `finally`, которые необходимо запускать даже в такой ситуации, одним из решений является добавление блока `catch` в оператор `try`\-`finally`.  Кроме того, можно перехватить исключение, которое может создаваться в блоке `try` оператора `try`\-`finally` выше по стеку вызовов.  То есть можно перехватить исключение в метод, который вызывает метод, содержащий оператора `try`\-`finally`, или в метод, который вызывает этот метод, или в любом методе в стеке вызовов.  Если исключение не обработано, среда выполнения блока `finally` зависит от того, активирует ли операционная система операцию развертывания исключения.  
  
## Пример  
 В следующем примере недопустимая инструкция преобразования вызывает исключение `System.InvalidCastException`.  Исключение является необработанным.  
  
 [!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 В следующем примере исключения из метода `TryCast` перехватывается в методе далее вверх по стеку вызовов.  
  
 [!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 Дополнительные сведения о `finally` см. в разделе [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C\# также содержит [оператор using](../../../csharp/language-reference/keywords/using-statement.md), который предоставляет аналогичную функциональность для объектов <xref:System.IDisposable> в удобном синтаксисе.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы try, throw и catch \(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)