---
title: Запросы между таблицами (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 8f9a538482580134fa876866dfe394c3dfc7de2a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634889"
---
# <a name="cross-table-queries-linq-to-dataset"></a>Запросы между таблицами (LINQ to DataSet)
В дополнение к запросам к одной таблице можно также выполнять запросы между таблицами в LINQ to DataSet. Это делается с помощью *объединения*. Соединение — это ассоциация объектов в одном источнике данных с объектами, которые совместно используют общий атрибут в другом источнике данных, например продукт или контактный код. В объектно-ориентированном программировании связи между объектами относительно просты для навигации, поскольку каждый объект имеет член, ссылающийся на другой объект. Однако в таблицах внешних баз данных перемещение по связям не столь однозначно. Таблицы баз данных не содержат встроенных связей. В таких случаях для соединения элементов из разных источников может использоваться операция объединения. Например, если две таблицы содержат данные о продуктах и о продажах, нужно использовать операцию соединения для сопоставления данных о продажах и о продуктах, относящихся к одному и тому же заказу на продажу.  
  
 Платформа, интегрированная с языком LINQ, предоставляет два оператора Join: <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>. Эти операторы выполняют *эквивалентные объединения*: то есть объединения, которые соответствуют двум источникам данных, только если их ключи равны. (Напротив, Transact-SQL поддерживает операторы Join, кроме `equals`, например оператор `less than`.)  
  
 В терминах реляционной базы данных оператор <xref:System.Linq.Enumerable.Join%2A> выполняет внутреннее соединение. Внутреннее соединение представляет собой соединение, при котором возвращаются только объекты, имеющие соответствия в другом наборе данных.  
  
 Операторы <xref:System.Linq.Enumerable.GroupJoin%2A> не имеют прямого эквивалента в терминах реляционной базы данных; они реализуют надмножество внутренних соединений и левых внешних соединений. Левое внешнее соединение — это соединение, возвращающее каждый элемент первой (левой) коллекции, даже если в второй коллекции нет коррелированных элементов.  
  
 Дополнительные сведения о объединениях см. в разделе [операции JOIN](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется традиционное соединение таблиц `SalesOrderHeader` и `SalesOrderDetail` из образца базы данных AdventureWorks для получения заказов, сделанных через Интернет начиная с августа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>См. также:

- [Запросы к DataSet](querying-datasets-linq-to-dataset.md)
- [Запросы к одной таблице](single-table-queries-linq-to-dataset.md)
- [Запрос к типизированным объектам DataSet](querying-typed-datasets.md)
- [Операции соединения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
