---
title: "Практическое руководство. Выполнение левых внешних соединений (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "левые внешние соединения [LINQ в C#]"
  - "соединения [C#], левые внешние"
  - "выражения запросов [LINQ в C#], соединения"
  - "запросы [LINQ в C#], соединения"
ms.assetid: 18e32be8-93db-4d30-8dea-ec6596e18f43
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Выполнение левых внешних соединений (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Левое внешнее соединение является соединением, при котором каждый элемент первой коллекции возвращается независимо от наличия взаимосвязанных элементов во второй коллекции.  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] можно использовать для левого внешнего соединения, вызвав метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> на основании результатов соединения группы.  
  
## Пример  
 В следующем примере показано, как использовать метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> применительно к результатам группового соединения для выполнения левого внешнего соединения.  
  
 Первым шагом выполнения левого внешнего соединения двух коллекций является выполнение внутреннего соединения с помощью группового соединения.  \(Описание этой процедуры см. в разделе [Практическое руководство. Выполнение внутренних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).\) В этом примере список объектов `Person` внутренн\- соединение в список объектов `Pet`, основанных на объекте `Person`, соответствующее `Pet.Owner`.  
  
 Вторым этапом является включение каждого элемента первой \(левой\) коллекции в результирующий сбор, даже если какой\-то из элементов не имеет совпадений в правой коллекции.  Эта процедура выполняется путем вызова метода <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> для каждой последовательности совпадающих элементов из группового соединения.  В этом примере <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> вызван на каждой последовательности соответствующие объекты `Pet`.  Метод возвращает коллекцию, содержащую одну, значение по умолчанию, если последовательность пуста сопоставления объектов `Pet` для любого объекта, `Person`, таким образом, при условии, что в каждом объекте `Person` представлен в коллекции результата.  
  
> [!NOTE]
>  Значение по умолчанию для типа `null`; поэтому пример проверяет пустой ссылки перед доступ к каждому элементу каждой коллекции `Pet`.  
  
 [!code-cs[CsLINQProgJoining#7](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-left-outer-joins_1.cs)]  
  
## Компиляция кода  
  
-   Создайте в [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] новый проект консольного приложения.  
  
-   Добавьте ссылку на System.Core.dll, если она отсутствует.  
  
-   Включите пространство имен <xref:System.Linq>.  
  
-   Скопируйте и вставьте код из примера в файл program.cs, после метода `Main` в классе `Program`.  Добавьте в метод `Main` строку кода для вызова метода `LeftOuterJoinExample`.  
  
-   Запустите программу.  
  
## См. также  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Практическое руководство. Выполнение внутренних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Практическое руководство. Выполнение групповых соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)