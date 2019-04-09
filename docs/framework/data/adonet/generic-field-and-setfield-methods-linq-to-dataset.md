---
title: Универсальные методы Field и SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 7c7f1fef5d1fa575cd6d3bfdb7e6cbbea79ade28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086017"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Универсальные методы Field и SetField (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Предоставляет методы расширения для <xref:System.Data.DataRow> класс для доступа к значениям столбцов: <xref:System.Data.DataRowExtensions.Field%2A> метод и <xref:System.Data.DataRowExtensions.SetField%2A> метод. Эти методы обеспечивают разработчикам более простой доступ к значениям столбцов, особенно это касается значений NULL. Объект <xref:System.Data.DataSet> использует для представления значений NULL класс <xref:System.DBNull.Value>, тогда как [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] использует поддержку платформой [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] типов, допускающих значения NULL. С помощью существующего метода доступа столбцов в <xref:System.Data.DataRow> требует приведения возвращаемого объекта к соответствующему типу. Если определенное поле в <xref:System.Data.DataRow> может иметь значение null, необходимо явно проверить значение null, так как возврат <xref:System.DBNull.Value> и неявном приведении его к другому типу возникает исключение <xref:System.InvalidCastException>. В следующем примере если <xref:System.Data.DataRow.IsNull%2A> метод не использовался, чтобы проверить значение null, будет создано исключение, если индексатор возвращает <xref:System.DBNull.Value> и пытается привести его к <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> предоставляет доступ к значениям столбцов в <xref:System.Data.DataRow>, а метод <xref:System.Data.DataRowExtensions.SetField%2A> устанавливает значения столбцов в <xref:System.Data.DataRow>. Оба метода, <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, обрабатывают типы, допускающие значения NULL, поэтому нет необходимости явно проводить проверку на значения NULL, как в предыдущем примере. Оба метода являются универсальными, поэтому приводить возвращенное значение к определенному типу не нужно.  
  
 В следующем примере используется метод <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` метода <xref:System.Data.DataRowExtensions.Field%2A> и метода <xref:System.Data.DataRowExtensions.SetField%2A>, должен совпадать с типом базового значения. В противном случае возникнет исключение <xref:System.InvalidCastException>. Указанное имя столбца также должно совпадать с именем столбца в <xref:System.Data.DataSet>, в противном случае возникнет исключение <xref:System.ArgumentException>. В обоих случаях исключения возникают во время выполнения при перечислении данных в ходе выполнения запроса.  
  
 Метод <xref:System.Data.DataRowExtensions.SetField%2A> сам по себе не выполняет преобразования типов. Однако это не означает, что преобразование типов не происходит. <xref:System.Data.DataRowExtensions.SetField%2A> Предоставляет метод [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] поведение <xref:System.Data.DataRow> класса. Преобразование типа может быть выполнено <xref:System.Data.DataRow> объекта и преобразованное значение затем будут сохраняться в <xref:System.Data.DataRow> объекта.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRowExtensions>
