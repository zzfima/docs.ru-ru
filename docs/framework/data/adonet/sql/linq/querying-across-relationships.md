---
title: "Выполнение запросов в связях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Выполнение запросов в связях
Ссылки на другие объекты или коллекции других объектов в определениях классов указывают непосредственно на связи внешнего ключа в базе данных.  Эти связи можно использовать при осуществлении запроса с помощью точечной нотации для доступа к свойствам связей и перехода от одного объекта к другому.  Эти операции доступа преобразуются в более сложные соединения или коррелированные подзапросы в эквивалентном SQL.  
  
 Например, следующий запрос переходит от заказов к клиентам в качестве способа ограничения результатов только заказами для клиентов, находящихся в Лондоне.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Если свойства связи не существуют, придется написать их вручную как *соединения*. Это выполняется так же, как и в запросе SQL \- см. следующий код.  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Свойство *связи* можно использовать для однократного определения данной конкретной связи.  После этого можно применять более удобный точечный синтаксис.  Однако существование свойств связи более важно, поскольку объектные модели, характерные для доменов, обычно определяются как иерархии или графики.  Программируемые объекты имеют ссылки на другие объекты.  Соответствие связей "объект\-объект" связям внешнего ключа в базах данных является лишь совпадением.  Доступ к свойству предоставляет удобный способ для написания соединений.  
  
 В связи с этим свойства связи являются более важными как результаты запроса, чем как часть самого запроса.  После того, как запрос извлечет, данные о конкретном клиенте, определение класса указывает наличие заказов.  Другими словами, ожидается, что свойство `Orders` конкретного клиента является коллекцией, заполняемой всеми заказами данного клиента.  На самом деле это контракт, объявленный путем подобного определения классов.  Вы хотите увидеть в нем заказы, даже если они не требуются для запроса.  Вы хотите, чтобы объектная модель поддерживала представление о том, что это находящееся в памяти расширение базы данных со связанными и немедленно доступными объектами.  
  
 Теперь при наличии связей можно писать запросы, обращаясь к свойствам связей, определенным в классах.  Эти ссылки на связи соответствуют связям внешнего ключа в базе данных.  Операции, использующие эти связи, преобразуются в более сложные соединения в эквивалентном SQL.  После определения связи \(с помощью атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>\) не требуется кодировать явное соединение в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Для поддержки этого представления в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] существует метод, называемый *отложенной загрузкой*.  Дополнительные сведения  см. в разделе [Сравнение отложенной и немедленной загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 Рассмотрим следующий запрос SQL для создания списка пар `CustomerID`\-`OrderID`.  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Чтобы получить такие же результаты с помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используйте ссылку на свойство `Orders`, уже существующую в классе `Customer`.  Ссылка `Orders` предоставляет данные, необходимые для выполнения запроса и создания пар `CustomerID`\-`OrderID`, как показано в следующем коде.  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 Также можно выполнить обратное.  Это значит, что можно запросить `Orders` и использовать ссылку на связь `Customer` для получения сведений о связанном объекте `Customer`.  В следующем коде создаются те же пары `CustomerID`\-`OrderID`, что и ранее, однако на этот раз выполняется запрос `Orders`, а не `Customers`.  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)