---
title: "Basic LINQ Query Operations (C#) | Microsoft Docs"
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
  - "orderby clause [LINQ in C#]"
  - "ordering data [LINQ in C#]"
  - "selecting data [LINQ in C#]"
  - "queries [LINQ in C#], basic operations"
  - "grouping data [LINQ in C#]"
  - "data sources [LINQ in C#]"
  - "sorting data [LINQ in C#]"
  - "projections [LINQ in C#]"
  - "filtering data [LINQ in C#]"
  - "joining data [LINQ in C#]"
  - "select clause [LINQ in C#]"
  - "LINQ [C#], basic query operations"
  - "join clause [LINQ in C#]"
  - "group clause [LINQ in C#]"
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 37
---
# Basic LINQ Query Operations (C#)
В этом разделе содержится краткое описание выражений запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] и некоторые типичные операции, выполняемые в запросе.  Более подробные сведения находятся в следующих разделах:  
  
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  Если вы уже знакомы с языком запросов, таким как SQL или XQuery, можно пропустить большую часть этого раздела.  Чтобы изучить порядок предложений в выражениях запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], прочитайте о предложении `from` в следующем разделе.  
  
## Получение источника данных  
 В первую очередь в запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] нужно указать источник данных.  В C\#, как и в большинстве языков программирования, переменная должна быть объявлена до ее использования.  В запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] первым идет предложение `from` для указания источника данных \(`customers`\) и *переменная диапазона* \(`cust`\).  
  
 [!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#23)]  
  
 Переменная диапазона схожа с переменной итерации в цикле `foreach` за исключением того, что в выражении запроса не происходит фактической итерации.  При выполнении запроса переменная диапазона будет использоваться как ссылка на каждый последующий элемент в `customers`.  Поскольку компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.  Дополнительные переменные диапазона могут быть введены предложением `let`.  Дополнительные сведения см. в разделе [Предложение let](../../../../csharp/language-reference/keywords/let-clause.md).  
  
> [!NOTE]
>  Для неуниверсальных источников данных, таких как <xref:System.Collections.ArrayList>,переменная диапазона должна быть явно типизирована.  Дополнительные сведения см. в разделах [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md) и [Предложение from](../../../../csharp/language-reference/keywords/from-clause.md).  
  
## Фильтрация  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в виде логического выражения.  Фильтр приводит к возвращению запросом только тех элементов, для которых выражение является истинным.  Результат создается с помощью предложения `where`.  Фильтр фактически указывает элементы для исключения из исходной последовательности.  В следующем примере возвращаются только `customers`, находящиеся в Лондоне.  
  
 [!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#24)]  
  
 Для применения нужного числа выражений фильтра в предложении `where` можно использовать знакомые логические операторы C\# `AND` и `OR`.  Например, для получения только заказчиков из Лондона `AND` с именем Devon следует написать следующий код.  
  
 [!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#25)]  
  
 Для получения заказчиков из Лондона или Парижа следует написать следующий код.  
  
 [!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#26)]  
  
 Дополнительные сведения см. в разделе [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## Порядок  
 Часто целесообразно отсортировать возвращенные данные.  Предложение `orderby` сортирует элементы возвращаемой последовательности в зависимости от компаратора по умолчанию для сортируемого типа.  Например, следующий запрос может быть расширен для сортировки результатов на основе свойства `Name`.  Поскольку `Name` является строкой, сравнение по умолчанию выполняется в алфавитном порядке от А до Я.  
  
 [!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#27)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `orderby…descending`.  
  
 Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
## Группировка  
 Предложение `group` позволяет группировать результаты на основе указанного ключа.  Например, можно указать, что результаты должны быть сгруппированы по `City` так, чтобы все заказчики из Лондона или Парижа оказались в отдельных группах.  В этом случае ключом является `cust.City`.  
  
 [!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#28)]  
  
 Когда запрос завершается предложением `group`, результаты представляются в виде списка из списков.  Каждый элемент в списке является объектом, имеющим член `Key` и список элементов, сгруппированных по этому ключу.  При итерации запроса, создающего последовательность групп, необходимо использовать вложенный цикл `foreach`.  Внешний цикл выполняет итерацию каждой группы, а внутренний цикл — итерацию членов каждой группы.  
  
 Если необходимо ссылаться на результаты операции группировки, можно использовать ключевое слово `into` для создания идентификатора, который можно будет запрашивать.  Следующий запрос возвращает только те группы, которые содержат более двух заказчиков.  
  
 [!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#29)]  
  
 Дополнительные сведения см. в разделе [Предложение group](../../../../csharp/language-reference/keywords/group-clause.md).  
  
## Соединение  
 Операции соединения создают связи между последовательностями, неявно смоделированными в источниках данных.  Например, можно выполнить соединение для поиска всех клиентов и распространителей, которые находятся в одном месте.  В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] предложение `join` всегда работает с коллекциями объектов, а не непосредственно с таблицами базы данных.  
  
 [!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#36)]  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] нет необходимости использовать `join` так часто, как в SQL, поскольку внешние ключи в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] представлены в объектной модели свойствами, содержащими коллекцию элементов.  Например, объект `Customer` содержит коллекцию объектов `Order`.  Вместо выполнения соединения, доступ к заказам можно получить с помощью точечной нотации.  
  
```  
from order in Customer.Orders...  
```  
  
 Дополнительные сведения см. в разделе [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md).  
  
## Выбор \(Проецирование\)  
 Предложение `select` создает результаты запроса и задает форму или тип каждого возвращаемого элемента.  Например, можно указать, будут ли результаты состоять из полных объектов `Customer`, только из одного члена, подмножества членов или некоторых совершенно других типов, на основе вычислений или создания новых объектов.  Когда предложение `select` создает что\-либо отличное от копии исходного элемента, операция называется *проекцией*.  Использование проекций для преобразования данных является мощной возможностью выражений запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Дополнительные сведения см. в разделах [Преобразования данных с помощью LINQ \(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) и [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## См. также  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Ключевые слова запроса \(LINQ\)](../../../../csharp/language-reference/keywords/query-keywords.md)   
 [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Основные операции запроса \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)