---
title: "Практическое руководство. Объявление, создание экземпляра и использование делегата (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "делегаты [C#], объявление и создание экземпляров"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Объявление, создание экземпляра и использование делегата (Руководство по программированию в C#)
В C\# версии 1.0 и более поздней версии делегаты можно объявлять, как показано в следующем примере.  
  
 [!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#13)]  
  
 [!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#14)]  
  
 C\# версии 2.0 предоставляет упрощенный способ записи предыдущего объявления, как показано в следующем примере.  
  
 [!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#32)]  
  
 В C\# версии 2.0 и более поздней версии также можно использовать анонимный метод для объявления и инициализации [делегата](../../../csharp/language-reference/keywords/delegate.md), как показано в следующем примере.  
  
 [!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#15)]  
  
 В C\# версии 3.0 и более поздней версии делегаты можно также объявлять и создавать их экземпляры при помощи лямбда\-выражения, как показано в следующем примере.  
  
 [!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#31)]  
  
 Дополнительные сведения см. в разделе [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Следующий пример демонстрирует объявление, создание экземпляра и использование делегата.  Класс `BookDB` инкапсулирует базу данных книжного магазина, в котором ведется база данных книг.  Он предоставляет метод `ProcessPaperbackBooks`, который находит все книги в мягкой обложке по базе данных и вызывает делегат для каждой книги.  Используемый тип `delegate` имеет имя `ProcessBookDelegate`.  Класс `Test` использует этот класс для печати заголовков и средней цены книг в мягкой обложке.  
  
 Использование делегата способствует правильному разделению функций между базой данных книжного магазина и клиентским кодом.  Клиентскому коду неизвестен порядок хранения книг и то, как код книжного магазина выполняет поиск книг в мягкой обложке.  Коду книжного магазина неизвестно о выполняемой обработке книг с мягкой обложкой после их нахождения.  
  
## Пример  
 [!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#12)]  
  
## Отказоустойчивость  
  
-   Объявление делегата.  
  
     Следующий оператор объявляет новый типа делегата.  
  
     [!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#16)]  
  
     Каждый тип делегата описывает число и типы аргументов, а также тип возвращаемого значения методов, которые могут быть им инкапсулированы.  Каждый раз, когда требуется новый набор типов аргументов или тип возвращаемого значения, необходимо объявить новый тип делегата.  
  
-   Создание экземпляра делегата  
  
     После объявления типа делегата необходимо создать объект делегата и связать его с определенным методом.  В предыдущем примере это выполняется путем передачи метода `PrintTitle` в метод `ProcessPaperbackBooks`, как показано в следующем примере:  
  
     [!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#17)]  
  
     Это создает новый объект делегата, связанный со [статическим](../../../csharp/language-reference/keywords/static.md) методом `Test.PrintTitle`.  Подобным образом передается не статический метод `AddBookToTotal` объекта `totaller`, как показано в следующем примере:  
  
     [!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#18)]  
  
     В обоих случаях новый объект делегата передается в метод `ProcessPaperbackBooks`.  
  
     После создания делегата метод, с которым он связан, никогда не изменится; объекты делегатов являются неизменяемыми.  
  
-   Вызов делегата.  
  
     После создания объекта делегата, он как правило передается в другой код, который вызовет делегат.  Объект делегата вызывается при помощи имени объекта делегата, после которого следуют параметризованные аргументы, передаваемые в делегат.  Ниже приведен пример вызова делегата.  
  
     [!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#19)]  
  
     Делегат может быть вызван синхронно \(как в этом примере\), или асинхронно при помощи методов `BeginInvoke` и `EndInvoke`.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)