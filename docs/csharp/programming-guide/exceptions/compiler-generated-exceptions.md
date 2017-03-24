---
title: "Исключения, создаваемые компилятором (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "исключения [C#], создаваемые компилятором"
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Исключения, создаваемые компилятором (Руководство по программированию в C#)
Некоторые исключения автоматически создаются средой CLR приложения платформы .NET Framework, когда происходит сбой основной операции.  Эти исключения и условия их возникновения перечислены в следующей таблице.  
  
|Исключение|Описание|  
|----------------|--------------|  
|<xref:System.ArithmeticException>|Основной класс исключений, происходящих при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Создается, когда массив не может хранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.|  
|<xref:System.DivideByZeroException>|Создается при попытке разделить целое число на ноль.|  
|<xref:System.IndexOutOfRangeException>|Создается при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.|  
|<xref:System.InvalidCastException>|Создается, когда происходит сбой явного преобразования из основного типа в интерфейс либо в производный тип во время выполнения.|  
|<xref:System.NullReferenceException>|Создается при попытке ссылки на объект, значение которого равно [null](../../../csharp/language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Создается при неудаче попытки выделения памяти с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md).  Это означает, что память, доступная для среды выполнения, уже исчерпана.|  
|<xref:System.OverflowException>|Создается при переполнении арифметической операции в контексте `checked`.|  
|<xref:System.StackOverflowException>|Создается, когда стек выполнения переполнен за счет слишком большого количества вызовов отложенных методов; обычно является признаком очень глубокой или бесконечной рекурсии.|  
|<xref:System.TypeInitializationException>|Создается, когда статический конструктор создает исключение, и не существует ни одного совместимого предложения `catch` для его захвата.|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)