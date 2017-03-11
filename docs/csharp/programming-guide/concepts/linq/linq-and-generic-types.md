---
title: "LINQ and Generic Types (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], generic types"
  - "generic types [LINQ]"
  - "generics [LINQ]"
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# LINQ and Generic Types (C#)
Запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] основаны на универсальных типах, которые впервые были представлены в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] версии 2.0.  Для написания запросов не требуется глубокое знание универсальных шаблонов.  Но понимание двух основных понятий может пригодиться.  
  
1.  При создании экземпляра класса универсальной коллекции, например <xref:System.Collections.Generic.List%601>, "T" заменяется типом объектов, которые будут храниться в списке.  Например, список строк выражается как `List<string>`, а список объектов `Customer` выражается как `List<Customer>`.  Универсальный список является строго типизированным и предоставляет множество преимуществ над коллекциями, которые хранят свои элементы как <xref:System.Object>.  При попытке добавить `Customer` к `List<string>` возникнет ошибка во время компиляции.  Использование универсальных коллекций не вызывает сложностей, поскольку не нужно выполнять приведение типов во время выполнения.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> является интерфейсом, который позволяет классам универсальных коллекций поддерживать перечисление с помощью оператора `foreach`.  Классы универсальных коллекций поддерживают <xref:System.Collections.Generic.IEnumerable%601> так же, как не универсальные классы коллекций, например <xref:System.Collections.ArrayList>, поддерживают <xref:System.Collections.IEnumerable>.  
  
 Дополнительные сведения об универсальных шаблонах см. в разделе [Универсальные шаблоны](../../../../csharp/programming-guide/generics/index.md).  
  
## Переменные IEnumerable\<T\> в запросах LINQ  
 Переменные запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] определены как <xref:System.Collections.Generic.IEnumerable%601> или как производный тип, например <xref:System.Linq.IQueryable%601>.  Если переменная запроса имеет тип `IEnumerable<Customer>`, это означает, что запрос при выполнении выведет последовательность из нуля или более объектов `Customer`.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#34)]  
  
 Дополнительные сведения см. в разделе [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Использование компилятора для обработки объявлений универсальных типов  
 При желании обычного синтаксиса универсальных шаблонов можно избежать с помощью ключевого слова [var](../../../../csharp/language-reference/keywords/var.md).  Ключевое слово `var` сообщает компилятору о необходимости определения типа переменной запроса с помощью просмотра источника данных, указанного в предложении `from`.  В следующем примере создается тот же самый скомпилированный код, что и в предыдущем примере.  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#35)]  
  
 Ключевое слово `var` удобно, когда тип переменной является очевидным, или когда не требуется явно указывать вложенные универсальные типы, например создаваемые запросами group.  В целом, если используется `var`, важно осознавать, что код может быть более сложным для чтения.  Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## См. также  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Универсальные шаблоны](../../../../csharp/programming-guide/generics/index.md)