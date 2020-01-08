---
title: Универсальные методы Field и SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 310eb3ccecc3159234ed362ed044be7ad704dde4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634837"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Универсальные методы Field и SetField (LINQ to DataSet)
LINQ to DataSet предоставляет методы расширения классу <xref:System.Data.DataRow> для доступа к значениям столбцов: метод <xref:System.Data.DataRowExtensions.Field%2A> и метод <xref:System.Data.DataRowExtensions.SetField%2A>. Эти методы обеспечивают разработчикам более простой доступ к значениям столбцов, особенно это касается значений NULL. <xref:System.Data.DataSet> использует <xref:System.DBNull.Value?displayProperty=nameWithType> для представления значений NULL, тогда как LINQ использует типы <xref:System.Nullable> и <xref:System.Nullable%601>. При использовании метода доступа к уже существующему столбцу в <xref:System.Data.DataRow> необходимо привести возвращаемый объект к соответствующему типу. Если конкретное поле в <xref:System.Data.DataRow> может иметь значение null, необходимо явно проверить значение null, так как при возвращении <xref:System.DBNull.Value?displayProperty=nameWithType> и неявном приведении его к другому типу возникает ошибка <xref:System.InvalidCastException>. В следующем примере, если метод <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> не использовался для проверки значения NULL, будет выдано исключение, если индексатор возвращал <xref:System.DBNull.Value?displayProperty=nameWithType> и пытался привести его к <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> предоставляет доступ к значениям столбцов в <xref:System.Data.DataRow>, а метод <xref:System.Data.DataRowExtensions.SetField%2A> устанавливает значения столбцов в <xref:System.Data.DataRow>. Оба метода, <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, обрабатывают типы, допускающие значения NULL, поэтому нет необходимости явно проводить проверку на значения NULL, как в предыдущем примере. Оба метода являются универсальными, поэтому приводить возвращенное значение к определенному типу не нужно.  
  
 В следующем примере используется метод <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` метода <xref:System.Data.DataRowExtensions.Field%2A> и метода <xref:System.Data.DataRowExtensions.SetField%2A>, должен совпадать с типом базового значения. В противном случае возникнет исключение <xref:System.InvalidCastException>. Указанное имя столбца также должно совпадать с именем столбца в <xref:System.Data.DataSet>, в противном случае возникнет исключение <xref:System.ArgumentException>. В обоих случаях исключения возникают во время выполнения при перечислении данных в ходе выполнения запроса.  
  
 Метод <xref:System.Data.DataRowExtensions.SetField%2A> сам по себе не выполняет преобразования типов. Однако это не означает, что преобразование типов не происходит. Метод <xref:System.Data.DataRowExtensions.SetField%2A> предоставляет поведение ADO.NET класса <xref:System.Data.DataRow>. Преобразование типа может быть выполнено объектом <xref:System.Data.DataRow>, а преобразованное значение будет сохранено в объект <xref:System.Data.DataRow>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Data.DataRowExtensions>
