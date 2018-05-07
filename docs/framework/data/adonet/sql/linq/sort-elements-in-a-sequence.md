---
title: Сортировка элементов последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 00c7a7a62890aced4c480e2653084c0b7cfe7f45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sort-elements-in-a-sequence"></a>Сортировка элементов последовательности
Для сортировки последовательности по одному или нескольким ключам используется оператор <xref:System.Linq.Enumerable.OrderBy%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предназначен для поддержки упорядочения по простым примитивным типам, таких как `string`, `int`, и т. д. В этой технологии не поддерживается упорядочение для сложных многозначных классов, таких как анонимные типы. В ней также не поддерживаются типы данных `byte`.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется сортировка сотрудников (`Employees`) по дате приема на работу.  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a>Пример  
 В следующем примере для сортировки заказов (`where`), поставленных в Лондон (`Orders`), по типу перевозки используется предложение `London`.  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется сортировка продуктов (`Products`) по цене единицы товара по убыванию.  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a>Пример  
 В следующем примере для сортировки клиентов (`OrderBy`) по городу, а затем по контактному лицу используется составной оператор `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется сортировка заказов от сотрудника `EmployeeID 1` по стране доставки, а затем по типу перевозки по убыванию.  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a>Пример  
 В следующем примере объединяются операторы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> и <xref:System.Linq.Enumerable.GroupBy%2A>, чтобы найти продукты (`Products`) с максимальной ценой за единицу товара в каждой категории, а затем выполнить сортировку полученной группы по коду категории.  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты должны выглядеть следующим образом:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a>См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
