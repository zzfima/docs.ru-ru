---
title: Запросы между таблицами (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 17f9e683161fba0fe57279952acecd9e4399d0aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757194"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Запросы между таблицами (LINQ to DataSet)
Кроме запросов к отдельной таблице, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет выполнять межтабличные запросы. Это делается с помощью *соединения*. Соединение представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных, такие как продукт или идентификатору контактного лица. В объектно ориентированное программирование связей между объектами являются относительно легко переход, поскольку каждый объект имеет элемент, который ссылается на другой объект. Однако в таблицах внешних баз данных перемещение по связям не столь однозначно. Таблицы баз данных не содержат встроенных связей. В таких случаях для соединения элементов из разных источников может использоваться операция объединения. Например, если две таблицы содержат данные о продуктах и о продажах, нужно использовать операцию соединения для сопоставления данных о продажах и о продуктах, относящихся к одному и тому же заказу на продажу.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Framework предоставляет два операторы соединения <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>. Эти операторы выполняют *эквивалентные соединения*: т. е соединения, сопоставляющие два данных источников, только если равны их ключей. (В отличие от этого, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] поддерживает операторы соединения, отличные от `equals`, например оператор `less than`.)  
  
 В терминах реляционной базы данных оператор <xref:System.Linq.Enumerable.Join%2A> выполняет внутреннее соединение. Внутреннее соединение представляет собой соединение, при котором возвращаются только объекты, имеющие соответствия в другом наборе данных.  
  
 <xref:System.Linq.Enumerable.GroupJoin%2A> Операторы не имеющих прямого эквивалента в терминах реляционных баз данных; они реализуют надмножество внутренних соединений и левых внешних соединений. Левое внешнее соединение является соединением, которое возвращает каждый элемент первого (левого) коллекции, даже если он не имеет соответствующих элементов второй коллекции.  
  
 Дополнительные сведения о соединениях см. в разделе [операции присоединения](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется традиционное соединение таблиц `SalesOrderHeader` и `SalesOrderDetail` из образца базы данных AdventureWorks для получения заказов, сделанных через Интернет начиная с августа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>См. также  
 [Запросы к DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Запросы к одной таблице](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [Запрос к типизированным объектам DataSet](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [Операции соединения](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
