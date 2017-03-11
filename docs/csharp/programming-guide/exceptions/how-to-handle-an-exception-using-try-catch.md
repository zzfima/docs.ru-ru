---
title: "Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "обработка исключений [C#], блоки try/catch"
  - "исключения [C#], блоки try/catch"
  - "блоки try/catch [C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#)
Блок [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде.  Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного создания исключения. Но в большинстве случаев на этом этапе можно только проверить, что создано подходящее исключение.  
  
## Пример  
 В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, поскольку ошибка вызвана переданным методу параметром `index`.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/csharp/how-to-handle-an-excepti_1.cs)]  
  
## Комментарии  
 Код, вызывающий исключение, находится в блоке `try`.  Инструкция `catch` помещается сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит.  В блоке `catch` исключение `IndexOutOfRangeException` обрабатывается, и вместо него создается более подходящее исключение `ArgumentOutOfRangeException`.  Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения.  Поскольку свойство <xref:System.Exception.InnerException%2A> [доступно только для чтения](../../../csharp/language-reference/keywords/readonly.md), его значение необходимо присваивать только в конструкторе нового исключения.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)