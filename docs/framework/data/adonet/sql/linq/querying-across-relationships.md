---
title: Выполнение запросов в связях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
ms.openlocfilehash: 1675e4c6a610373e1c981b383ae0229739d96dd0
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003331"
---
# <a name="querying-across-relationships"></a>Выполнение запросов в связях
Ссылки на другие объекты или коллекции других объектов в определениях классов указывают непосредственно на связи внешнего ключа в базе данных. Эти связи можно использовать при осуществлении запроса с помощью точечной нотации для доступа к свойствам связей и перехода от одного объекта к другому. Эти операции доступа преобразуются в более сложные соединения или коррелированные подзапросы в эквивалентном SQL.  
  
 Например, следующий запрос переходит от заказов к клиентам в качестве способа ограничения результатов только заказами для клиентов, находящихся в Лондоне.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Если свойства связи не существовали, придется написать их вручную как *объединения*, как в SQL-запросе, как показано в следующем коде:  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Можно использовать свойство *Relationship* , чтобы определить эту конкретную связь один раз. После этого можно применять более удобный точечный синтаксис. Однако существование свойств связи более важно, поскольку объектные модели, характерные для доменов, обычно определяются как иерархии или графики. Программируемые объекты имеют ссылки на другие объекты. Соответствие связей "объект-объект" связям внешнего ключа в базах данных является лишь совпадением. Доступ к свойству предоставляет удобный способ для написания соединений.  
  
 В связи с этим свойства связи являются более важными как результаты запроса, чем как часть самого запроса. После того, как запрос извлечет, данные о конкретном клиенте, определение класса указывает наличие заказов. Другими словами, ожидается, что свойство `Orders` конкретного клиента является коллекцией, заполняемой всеми заказами данного клиента. На самом деле это контракт, объявленный путем подобного определения классов. Вы хотите увидеть в нем заказы, даже если они не требуются для запроса. Вы хотите, чтобы объектная модель поддерживала представление о том, что это находящееся в памяти расширение базы данных со связанными и немедленно доступными объектами.  
  
 Теперь при наличии связей можно писать запросы, обращаясь к свойствам связей, определенным в классах. Эти ссылки на связи соответствуют связям внешнего ключа в базе данных. Операции, использующие эти связи, преобразуются в более сложные соединения в эквивалентном SQL. После определения связи (с помощью атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>) не требуется кодировать явное соединение в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Для поддержки этой иллюзии [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует метод, называемый *отложенной загрузкой*. Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).  
  
 Рассмотрим следующий SQL-запрос для проецирования списка `CustomerID`-`OrderID` пар:  
  
```sql
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Чтобы получить такие же результаты с помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используйте ссылку на свойство `Orders`, уже существующую в классе `Customer`. Ссылка на `Orders` предоставляет необходимые сведения для выполнения запроса и проецирования `CustomerID`-`OrderID` пар, как показано в следующем коде:  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 Также можно выполнить обратное. Это значит, что можно запросить `Orders` и использовать ссылку на связь `Customer` для получения сведений о связанном объекте `Customer`. Следующий код проецирует то же `CustomerID`-`OrderID`, как и раньше, но на этот раз путем запроса `Orders` вместо `Customers`.  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a>См. также:

- [Основные принципы запросов](query-concepts.md)
