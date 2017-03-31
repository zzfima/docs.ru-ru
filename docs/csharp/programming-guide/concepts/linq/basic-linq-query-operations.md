---
title: "Основные операции запросов LINQ (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48624d608c3eb8d1118a2492454595d46025cb3e
ms.lasthandoff: 03/13/2017

---
# <a name="basic-linq-query-operations-c"></a>Основные операции запросов LINQ (C#)
В этом разделе содержится краткое описание выражений запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] и некоторые типичные операции, выполняемые в запросе. Более подробные сведения приводятся в следующих разделах:  
  
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [Пошаговое руководство. Написание запросов на C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  Если вы уже знакомы с языком запросов, таким как SQL или XQuery, можно пропустить большую часть этого раздела. Чтобы изучить порядок предложений в выражениях запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], прочитайте о предложении `from` в следующем разделе.  
  
## <a name="obtaining-a-data-source"></a>Получение источника данных  
 В первую очередь в запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] нужно указать источник данных. В C#, как и в большинстве языков программирования, переменная должна быть объявлена до ее использования. В запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] первым идет предложение `from` для указания источника данных (`customers`) и *переменная диапазона* (`cust`).  
  
 [!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_1.cs)]  
  
 Переменная диапазона схожа с переменной итерации в цикле `foreach` за исключением того, что в выражении запроса не происходит фактической итерации. При выполнении запроса переменная диапазона будет использоваться как ссылка на каждый последующий элемент в `customers`. Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Дополнительные переменные диапазона могут быть введены предложением `let`. Дополнительные сведения см. в разделе [Предложение let](../../../../csharp/language-reference/keywords/let-clause.md).  
  
> [!NOTE]
>  Для неуниверсальных источников данных, таких как <xref:System.Collections.ArrayList>, переменная диапазона должна быть явно типизирована. Дополнительные сведения см. в разделах [Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) и [Предложение from](../../../../csharp/language-reference/keywords/from-clause.md).  
  
## <a name="filtering"></a>Фильтрация  
 По-видимому, одной из наиболее распространенных операций с запросом является применение фильтра в форме логического выражения. Фильтр приводит к возвращению запросом только тех элементов, для которых выражение является истинным. Результат вырабатывается с использованием предложения `where`. Фильтр фактически указывает элементы для исключения из исходной последовательности. В приведенном ниже примере возвращаются только те элементы `customers`, которые находятся в Лондоне.  
  
 [!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_2.cs)]  
  
 Для применения нужного числа выражений фильтра в предложении `where` можно использовать знакомые логические операторы C# `AND` и `OR`. Например, для получения только заказчиков из Лондона `AND` с именем Devon следует написать следующий код:  
  
 [!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_3.cs)]  
  
 Для получения заказчиков из Лондона или Парижа следует написать следующий код:  
  
 [!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_4.cs)]  
  
 Дополнительные сведения см. в разделе [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## <a name="ordering"></a>Упорядочение  
 Часто целесообразно отсортировать возвращенные данные. Предложение `orderby` сортирует элементы возвращаемой последовательности в зависимости от компаратора по умолчанию для сортируемого типа. Например, приведенный ниже запрос можно расширить для сортировки результатов на основе свойства `Name`. Так как `Name` является строкой, сравнение по умолчанию выполняется в алфавитном порядке от А до Я.  
  
 [!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_5.cs)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `orderby…descending`.  
  
 Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
## <a name="grouping"></a>Группирование  
 Предложение `group` позволяет группировать результаты на основе указанного ключа. Например, можно указать, что результаты должны быть сгруппированы по `City` так, чтобы все заказчики из Лондона или Парижа оказались в отдельных группах. В этом случае ключом является `cust.City`.  
  
 [!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_6.cs)]  
  
 Когда запрос завершается предложением `group`, результаты представляются в виде списка из списков. Каждый элемент в списке является объектом, имеющим член `Key` и список элементов, сгруппированных по этому ключу. При итерации запроса, создающего последовательность групп, необходимо использовать вложенный цикл `foreach`. Внешний цикл выполняет итерацию каждой группы, а внутренний цикл — итерацию членов каждой группы.  
  
 Если необходимо ссылаться на результаты операции группировки, можно использовать ключевое слово `into` для создания идентификатора, который можно будет запрашивать. Приведенный ниже запрос возвращает только те группы, которые содержат более двух заказчиков.  
  
 [!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_7.cs)]  
  
 Дополнительные сведения см. в разделе [Предложение group](../../../../csharp/language-reference/keywords/group-clause.md).  
  
## <a name="joining"></a>Соединение  
 Операции соединения создают связи между последовательностями, неявно смоделированными в источниках данных. Например, можно выполнить соединение для поиска всех клиентов и дистрибьюторов, которые находятся в одном месте. В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] предложение `join` всегда работает с коллекциями объектов, а не непосредственно с таблицами базы данных.  
  
 [!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_8.cs)]  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] нет необходимости использовать `join` так часто, как в SQL, так как внешние ключи в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] представлены в объектной модели свойствами, содержащими коллекцию элементов. Например, объект `Customer` содержит коллекцию объектов `Order`. Вместо выполнения соединения доступ к заказам можно получить с помощью точечной нотации.  
  
```  
from order in Customer.Orders...  
```  
  
 Дополнительные сведения см. в разделе [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md).  
  
## <a name="selecting-projections"></a>Выбор (проецирование)  
 Предложение `select` создает результаты запроса и задает форму или тип каждого возвращаемого элемента. Например, можно указать, будут ли результаты состоять из полных объектов `Customer`, только из одного члена, подмножества членов или некоторых совершенно других типов, на основе вычислений или создания новых объектов. Когда предложение `select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*. Использование проекций для преобразования данных является эффективной возможностью выражений запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Дополнительные сведения см. в разделах [Преобразования данных с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) и [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Пошаговое руководство. Написание запросов на C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Ключевые слова запроса (LINQ)](../../../../csharp/language-reference/keywords/query-keywords.md)   
 [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
