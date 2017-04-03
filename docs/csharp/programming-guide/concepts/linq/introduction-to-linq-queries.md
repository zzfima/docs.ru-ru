---
title: "Введение в запросы LINQ (C#) | Документы Майкрософт"
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
- deferred execution [LINQ]
- LINQ, queries
- LINQ, deferred execution
- queries [LINQ], about LINQ queries
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
caps.latest.revision: 47
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
ms.openlocfilehash: 957ab9907c16e494f87873934fe4caccc146c975
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-linq-queries-c"></a>Введение в запросы LINQ (C#)
*Запрос* представляет собой выражение, извлекающее данные из источника данных. Запросы обычно выражаются на специализированном языке запросов. Со временем для различных типов источников данных, например SQL для реляционных баз данных и XQuery для XML, были разработаны разные языки. Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных или формата данных, для которых они должны обеспечить поддержку. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] упрощает ситуацию, реализуя согласованную модель работы с данными для различных типов источников данных и форматов данных. В запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] вы всегда работаете с объектами. Одинаковые базовые шаблоны кода используются для запроса и преобразования данных в XML-документах, базах данных SQL, наборах данных [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], коллекциях .NET и любых других форматах, для которых доступен поставщик [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  
  
## <a name="three-parts-of-a-query-operation"></a>Три составляющие операции запроса  
 Все операции запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] состоят из трех отдельных действий:  
  
1.  получение источника данных;  
  
2.  создание запроса;  
  
3.  выполнение запроса.  
  
 В следующем примере показано, как эти три части операции запроса выражаются в исходном коде. В этом примере для удобства используется массив целых чисел в качестве источника данных. Тем не менее те же принципы применимы к другим источникам данных. Остальные процедуры этого раздела содержат ссылки на этот пример.  
  
 [!code-cs[CsLINQGettingStarted#1](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_1.cs)]  
  
 На следующем рисунке показана полная операция запроса. В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] выполнение запроса отличается от самого запроса; другими словами, вы не получаете данные, просто создав переменную запроса.  
  
 ![Полная операция запроса LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_query.png "INQ_Query")  
  
## <a name="the-data-source"></a>Источник данных  
 В предыдущем примере, поскольку источник данных является массивом, он неявно поддерживает универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Это значит, что его можно запросить с помощью [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Запрос выполняется в операторе `foreach`, а `foreach` требует интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>. Типы, которые поддерживают <xref:System.Collections.Generic.IEnumerable%601> или производный интерфейс (например, универсальный интерфейс <xref:System.Linq.IQueryable%601>), называются *запрашиваемыми типами*.  
  
 Запрашиваемый тип не требует внесения изменений или специальной обработки, чтобы служить источником данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Если источник данных не находится в памяти в качестве запрашиваемого типа, поставщик [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] должен представить его как таковой. Например, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] загружает XML-документ в запрашиваемый тип <xref:System.Xml.Linq.XElement>.  
  
 [!code-cs[CsLINQGettingStarted#2](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_2.cs)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] сначала необходимо создать объектно-реляционное сопоставление во время разработки вручную либо с помощью [средства LINQ to SQL в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2). Вы создаете запросы к объектам, а [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] во время выполнения обрабатывает взаимодействие с базой данных. В следующем примере `Customers` представляет определенную таблицу в базе данных, а тип результата запроса, <xref:System.Linq.IQueryable%601>, является производным от <xref:System.Collections.Generic.IEnumerable%601>.  
  
```csharp  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
  
```  
  
 Дополнительные сведения о способах создания определенных типов источников данных см. в документации для различных поставщиков [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Однако общее правило очень просто: источником данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] является любой объект, который поддерживает универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601> или интерфейс, наследуемый от него.  
  
> [!NOTE]
>  Такие типы, как <xref:System.Collections.ArrayList>, поддерживающие неуниверсальный интерфейс <xref:System.Collections.IEnumerable>, также могут использоваться как источники данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Дополнительные сведения см. в разделе [Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).  
  
##  <a name="query"></a> Запрос  
 Запрос указывает, какую информацию нужно извлечь из источника или источников данных. Дополнительно в запросе можно указать, как следует сортировать, группировать и формировать возвращаемую информацию. Запрос хранится в переменной запроса и инициализируется выражением запроса. Чтобы упростить написание запросов, в C# был представлен новый синтаксис запроса.  
  
 В предыдущем примере запрос возвращает все четные числа из массива целых чисел. Выражение запроса содержит три предложения: `from`, `where` и `select`. (Если вы знакомы с SQL, то должны были заметить, что порядок предложений противоположен порядку в SQL.) Предложение `from` указывает источник данных, предложение `where` применяет фильтр, а предложение `select` задает тип возвращаемых элементов. Эти и другие предложения запросов подробно описываются в разделе [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md). А сейчас важно то, что в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] сама переменная запроса не выполняет никаких действий и не возвращает никаких данных. Она просто хранит сведения, необходимые для предоставления результатов при выполнении запроса на более позднем этапе. Дополнительные сведения о принципах конструирования запросов см. в разделе [Общие сведения о стандартных операторах запросов (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)[Общие сведения о стандартных операторах запросов](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
> [!NOTE]
>  Запросы могут также выражаться с помощью синтаксиса методов. Дополнительные сведения см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="query-execution"></a>Выполнение запроса  
  
### <a name="deferred-execution"></a>Отложенное выполнение  
 Как уже говорилось ранее, сама переменная запроса хранит команды запроса. Фактическое выполнение запроса откладывается до тех пор, пока переменная запроса не будет обработана в операторе `foreach`. Эта концепция называется *отложенным выполнением* и демонстрируется в следующем примере:  
  
 [!code-cs[csLinqGettingStarted#4](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_3.cs)]  
  
 Оператор `foreach` также является частью кода, в которой извлекаются результаты запроса. Например, в предыдущем запросе переменная итерации `num` содержит каждое значение (по одному за раз) в возвращенной последовательности.  
  
 Поскольку сама переменная запроса никогда не содержит результаты запроса, вы можете выполнять ее так часто, как это необходимо. Например, может иметься база данных, постоянно обновляемая отдельным приложением. В приложении можно создать один запрос, получающий самые последние данные, и регулярно выполнять его с некоторым интервалом, каждый раз получая разные результаты.  
  
### <a name="forcing-immediate-execution"></a>Принудительное немедленное выполнение  
 Запросы, выполняющие статистические функции для диапазона исходных элементов, сначала должны выполнить итерацию по этим элементам. Примерами таких запросов являются `Count`, `Max`, `Average` и `First`. Они выполняются без явного оператора `foreach`, поскольку сам запрос должен использовать `foreach` для возвращения результата. Обратите внимание, что такие типы запросов возвращают одно значение, а не коллекцию `IEnumerable`. Следующий запрос возвращает количество четных чисел в исходном массиве:  
  
 [!code-cs[csLinqGettingStarted#5](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_4.cs)]  
  
 Чтобы принудительно вызвать немедленное выполнение любого запроса и кэшировать его результаты, можно вызвать метод <xref:System.Linq.Enumerable.ToList%2A> или <xref:System.Linq.Enumerable.ToArray%2A>.  
  
 [!code-cs[csLinqGettingStarted#6](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_5.cs)]  
  
 Принудительно вызвать выполнение также можно, поместив цикл `foreach` сразу после выражения запроса. При этом путем вызова `ToList` или `ToArray` можно также кэшировать все данные в одном объекте коллекции.  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Пошаговое руководство. Написание запросов на C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Пошаговое руководство. Написание запросов на C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [foreach, in](../../../../csharp/language-reference/keywords/foreach-in.md)   
 [Ключевые слова запроса (LINQ)](../../../../csharp/language-reference/keywords/query-keywords.md)
