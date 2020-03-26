---
title: Универсальные методы Field и SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: d7ddee775e91c6be6166a091997afd58113cfe6b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249107"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Универсальные методы Field и SetField (LINQ to DataSet)
ДЛЯ DataSet для DataSet приводится методы расширения <xref:System.Data.DataRow> для <xref:System.Data.DataRowExtensions.Field%2A> класса для <xref:System.Data.DataRowExtensions.SetField%2A> доступа к значениям столбца: методу и методу. Эти методы обеспечивают разработчикам более простой доступ к значениям столбцов, особенно это касается значений NULL. Использует <xref:System.Data.DataSet> <xref:System.DBNull.Value?displayProperty=nameWithType> для представления нулевых значений, в <xref:System.Nullable> <xref:System.Nullable%601> то время как LIN' использует и типы. Использование уже существующего аксессуара <xref:System.Data.DataRow> столбца требует от вас отлить обратный объект в соответствующий тип. Если определенное поле <xref:System.Data.DataRow> в может быть нулевым, вы должны <xref:System.DBNull.Value?displayProperty=nameWithType> явно проверить на нулевую <xref:System.InvalidCastException>стоимость, потому что возвращение и неявно литья его в другой тип бросает . В следующем примере, <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> если метод не был использован для проверки нулевого значения, <xref:System.DBNull.Value?displayProperty=nameWithType> будет брошено исключение, если индексер вернется и попытается бросить его в <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> предоставляет доступ к значениям столбцов в <xref:System.Data.DataRow>, а метод <xref:System.Data.DataRowExtensions.SetField%2A> устанавливает значения столбцов в <xref:System.Data.DataRow>. <xref:System.Data.DataRowExtensions.Field%2A> Метод и <xref:System.Data.DataRowExtensions.SetField%2A> метод обрабатывают недействительные типы значений, поэтому вам не придется явно проверять значения null, как в предыдущем примере. Оба метода являются универсальными, поэтому приводить возвращенное значение к определенному типу не нужно.  
  
 В следующем примере используется метод <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` метода <xref:System.Data.DataRowExtensions.Field%2A> и метода <xref:System.Data.DataRowExtensions.SetField%2A>, должен совпадать с типом базового значения. В противном случае возникнет исключение <xref:System.InvalidCastException>. Указанное имя столбца также должно совпадать с именем столбца в <xref:System.Data.DataSet>, в противном случае возникнет исключение <xref:System.ArgumentException>. В обоих случаях исключения возникают во время выполнения при перечислении данных в ходе выполнения запроса.  
  
 Метод <xref:System.Data.DataRowExtensions.SetField%2A> сам по себе не выполняет преобразования типов. Однако это не означает, что преобразование типов не происходит. Метод <xref:System.Data.DataRowExtensions.SetField%2A> разоблачает ADO.NET <xref:System.Data.DataRow> поведение класса. Преобразование типа может <xref:System.Data.DataRow> быть выполнено объектом, и <xref:System.Data.DataRow> преобразованное значение будет сохранено объекту.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRowExtensions>
