---
title: "Запросы в LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Запросы в LINQ to DataSet
Запрос представляет собой выражение, извлекающее данные из источника данных.  Запросы обычно выражаются на специализированном языке запросов, например SQL для реляционных баз данных и XQuery для XML.  Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных и формата данных, для которых выполняется запрос.  [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] реализует более простую и согласованную модель работы с данными для различных типов источников данных и различных форматов данных.  В запросе [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] работа всегда происходит с программными объектами.  
  
 Операция запроса [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] состоит из трех действий: получение одного или нескольких источников данных, создание запроса и выполнение запроса.  
  
 К источникам данных, которые реализуют универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, могут быть выполнены запросы с помощью [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  Вызов метода <xref:System.Data.DataTableExtensions.AsEnumerable%2A> для <xref:System.Data.DataTable> возвращает объект, который реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, который в свою очередь служит источником данных для запросов [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
 В запросе указываются данные, которые необходимо получить из источника данных.  В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию.  В [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] запрос хранится в переменной.  Если запрос должен возвращать последовательность значений, переменная запроса должна иметь перечислимый тип данных.  Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе.  После создания запроса его необходимо выполнить, чтобы получить данные.  
  
 В запросе, возвращающем последовательность значений, переменная запроса никогда не содержит результаты запроса, а только хранит его команды.  Выполнение запроса откладывается, пока переменная запроса используется в циклах `foreach` или `For Each`.  Это называется *отложенным выполнением*, то есть выполнение запроса происходит спустя некоторое время после его создания.  Это означает, что запрос можно выполнять настолько часто, насколько это необходимо.  Такое свойство полезно, например, если имеется база данных, которая обновляется другими приложениями.  В собственном приложении можно создать запрос, который регулярно выполняется, каждый раз получая последние обновленные данные.  
  
 В отличие от отложенных запросов, возвращающих последовательности значений, запросы, получающие одноэлементное значение, выполняются немедленно.  Примерами одноэлементных запросов являются <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> и <xref:System.Linq.Enumerable.First%2A>.  Они выполняются немедленно, так как результаты запросов необходимы для вычисления одноэлементного результата.  Например, чтобы вычислить среднее из результатов запросов, запросы должны быть выполнены, только тогда усредняющая функция получит данные для обработки.  Для принудительного немедленного выполнения запроса, не создающего одноэлементное значение, можно также использовать метод <xref:System.Linq.Enumerable.ToList%2A> или <xref:System.Linq.Enumerable.ToArray%2A>.  Такая методика принудительного немедленного выполнения может оказаться полезной при кэшировании результатов запроса.  Дополнительные сведения об отложенном и немедленном выполнении запросов см. в разделе [Getting Started with LINQ](http://msdn.microsoft.com/ru-ru/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).  
  
## Запросы  
 При подготовке запросов [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] можно использовать два разных синтаксиса: синтаксис выражений запросов и синтаксис запросов на основе методов.  
  
### Синтаксис выражений запросов  
 Выражения запроса используют декларативный синтаксис запроса.  Этот синтаксис позволяет разработчику писать запросы на C\# или Visual Basic в формате, похожем на SQL.  С помощью синтаксиса выражения запроса можно выполнять даже сложную фильтрацию, упорядочение и группирование операций в источнике данных с помощью минимального программного кода.  Дополнительные сведения см. в разделах [Выражения запросов LINQ](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md) и [Основные операции запроса \(Visual Basic\)](../Topic/Basic%20Query%20Operations%20\(Visual%20Basic\).md).  
  
 Синтаксис выражения запроса появился в языках C\# 3.0 и [!INCLUDE[vb_orcas_long](../../../../includes/vb-orcas-long-md.md)].  Тем не менее среда CLR платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] не может прочитать выражение запроса сама.  Таким образом, во время компиляции выражения запроса преобразуются в то, что понятно CLR \- вызовы методов.  Эти методы называются *стандартными операторами запроса*.  Разработчик может вызывать их напрямую, используя синтаксис методов вместо синтаксиса запроса.  Для получения дополнительной информации см. [Query Syntax and Method Syntax in LINQ](../Topic/Query%20Syntax%20and%20Method%20Syntax%20in%20LINQ%20\(C%23\).md).  Дополнительные сведения об использовании стандартных операторов запроса см. в разделе [NOT IN BUILD: LINQ General Programming Guide](http://msdn.microsoft.com/ru-ru/609c7a6b-cbdd-429d-99f3-78d13d3bc049).  
  
 В следующем примере показано использование метода <xref:System.Linq.Enumerable.Select%2A> для выборки всех строк из таблицы `Product` и отображения названий продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### Синтаксис запросов, основанных на методе  
 Другой способ создания запросов [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] \- использование запросов на основе методов.  Синтаксис запросов на основе методов \- это последовательность прямых вызовов методов [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] с передачей им лямбда\-выражений в качестве параметров.  Для получения дополнительной информации см. [Лямбда\-выражения](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md).  
  
 В следующем примере выражение <xref:System.Linq.Enumerable.Select%2A> используется для возврата всех строк из таблицы `Product` и вывода названий продуктов.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## Создание запросов  
 Как указывалось выше в этом разделе, переменная запроса хранит команды запроса, если он предназначен для возврата последовательности значений.  Если запрос не содержит метод, приводящий к немедленному выполнению запроса, фактическое выполнение запроса откладывается до завершения обработки переменной запроса в цикле `foreach` или `For Each`.  Отложенное выполнение позволяет объединять несколько запросов или расширять один запрос.  При расширении запроса он изменяется, включая в себя новые операции, а последующее выполнение отразит эти изменения.  В следующем примере первый запрос возвращает все продукты.  Второй запрос расширяет первый, используя предложение `Where`, чтобы возвратить все продукты с размером «L»:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 После выполнения запроса присоединять к нему дополнительные запросы нельзя, и все последующие запросы будут использовать операторы [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] из памяти.  Запрос выполнится в случае, когда закончится итерация переменной запроса в инструкциях `foreach` или `For Each`, либо при вызове одного из операторов преобразования [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], запускающих немедленное выполнение.  В число этих операторов входят следующие: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> и <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 В следующем примере первый запрос возвращает все продукты, отсортированные по списочной цене.  Метод <xref:System.Linq.Enumerable.ToArray%2A> используется для принудительного немедленного выполнения запроса:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## См. также  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)   
 [Запросы к объектам DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Getting Started with LINQ in C\#](../Topic/Getting%20Started%20with%20LINQ%20in%20C%23.md)   
 [Getting Started with LINQ in Visual Basic](../Topic/Getting%20Started%20with%20LINQ%20in%20Visual%20Basic.md)