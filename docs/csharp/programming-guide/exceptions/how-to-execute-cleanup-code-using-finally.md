---
title: "Практическое руководство. Выполнение кода очистки с использованием блока finally (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "обработка исключений [C#], try/finally - блок"
  - "исключения [C#], try/finally - блок"
  - "try/finally - блоки [C#]"
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Выполнение кода очистки с использованием блока finally (Руководство по программированию на C#)
Инструкция `finally` предназначена для обеспечения немедленного выполнения необходимой очистки объектов, обычно занимающих внешние ресурсы, даже в случае, когда генерируется исключение.  Примером подобной очистки является вызов метода <xref:System.IO.Stream.Close%2A> для объекта класса <xref:System.IO.FileStream> сразу после его использования, не дожидаясь, когда этот объект будет уничтожен сборщиком мусора среды CLR, как показано ниже:  
  
 [!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## Пример  
 Чтобы превратить предыдущий код в инструкцию `try-catch-finally`, код очистки отделяется от рабочего кода, как показано ниже.  
  
 [!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 Так как исключение может произойти в любой момент внутри блока `try` до вызова метода `OpenWrite()` или ошибкой может завершится выполнение самого метода `OpenWrite()`, при выполнении попытки закрыть файл нет гарантии, что он открыт.  Блок `finally` добавляет проверку, чтобы убедиться, что объект класса <xref:System.IO.FileStream> не имеет значения `null`, прежде чем вызывать метод <xref:System.IO.Stream.Close%2A>.  При отсутствии проверки значения `null` блок `finally` может сам генерировать исключение <xref:System.NullReferenceException>, но генерирования исключений в блоках `finally` по возможности следует избегать.  
  
 Подключение к базе данных является еще одним кандидатом на закрывание в блоке `finally`.  Так как допустимое число подключений к серверу базы данных иногда ограничено, их следует закрывать как можно быстрее.  Если исключение генерируется прежде, чем можно закрыть подключение, то это еще один случай, когда лучше применить блок `finally`, чем ждать выполнения сборки мусора.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)