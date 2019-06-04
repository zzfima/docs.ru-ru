---
title: Запросы между таблицами (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: e974f643fd1515b701d2e81048725b88055b57dc
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489569"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Запросы между таблицами (LINQ to DataSet)
Кроме запросов к отдельной таблице, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет выполнять межтабличные запросы. Это делается с помощью *соединения*. Соединение представляет собой взаимосвязь объектов одного источника данных с объектами, которые имеют общий атрибут в другом источнике данных, таких как продукт или идентификатору контактного лица. В объектно ориентированном программировании связи между объектами относительно просты для перемещения, так как каждый объект имеет элемент, который ссылается на другой объект. Однако в таблицах внешних баз данных перемещение по связям не столь однозначно. Таблицы баз данных не содержат встроенных связей. В таких случаях для соединения элементов из разных источников может использоваться операция объединения. Например, если две таблицы содержат данные о продуктах и о продажах, нужно использовать операцию соединения для сопоставления данных о продажах и о продуктах, относящихся к одному и тому же заказу на продажу.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Framework предоставляет два оператора соединения: <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>. Эти операторы выполняют *эквивалентные соединения*: то есть соединения, которые сопоставляют два данных источников, только если их ключи равны. (Напротив, Transact-SQL поддерживает операторы соединения, отличные от `equals`, такие как `less than` оператор.)  
  
 В терминах реляционной базы данных оператор <xref:System.Linq.Enumerable.Join%2A> выполняет внутреннее соединение. Внутреннее соединение представляет собой соединение, при котором возвращаются только объекты, имеющие соответствия в другом наборе данных.  
  
 <xref:System.Linq.Enumerable.GroupJoin%2A> Операторы не имеющих прямого эквивалента в терминах реляционных баз данных; они реализует надмножество внутренних соединений и левых внешних соединений. Левое внешнее соединение представляет собой соединение, возвращает каждый элемент первой (левой) коллекции, даже если он не имеет соответствующих элементов во второй коллекции.  
  
 Дополнительные сведения о соединениях см. в разделе [операции соединения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется традиционное соединение таблиц `SalesOrderHeader` и `SalesOrderDetail` из образца базы данных AdventureWorks для получения заказов, сделанных через Интернет начиная с августа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>См. также

- [Запросы к DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Запросы к одной таблице](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
- [Запрос к типизированным объектам DataSet](../../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [Операции соединения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))
- [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
