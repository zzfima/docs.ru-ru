---
title: "Универсальные методы Field и SetField (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Универсальные методы Field и SetField (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] реализует методы расширений класса <xref:System.Data.DataRow> для доступа к значениям столбцов: <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>. Эти методы предоставляют разработчикам более простой доступ к значениям столбцов, особенно в отношении значений NULL. Объект <xref:System.Data.DataSet> использует для представления значений NULL класс <xref:System.DBNull.Value>, тогда как [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] использует поддержку платформой [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] типов, допускающих значения NULL.  Использование существующего метода доступа столбцов в объекте <xref:System.Data.DataRow> требует приведения возвращаемого объекта к нужному типу.  Если определенное поле в объекте <xref:System.Data.DataRow> может иметь значение NULL, необходимо явно проверить наличие значения NULL, поскольку при возвращении объекта <xref:System.DBNull.Value> и неявном приведении его к другому типу возникает исключение <xref:System.InvalidCastException>.  В следующем примере, если метод <xref:System.Data.DataRow.IsNull%2A> не использовался для проверки на значение NULL, возникнет исключение, если индексатор возвращает объект <xref:System.DBNull.Value> и пытается привести его к типу <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> предоставляет доступ к значениям столбцов в <xref:System.Data.DataRow>, а метод <xref:System.Data.DataRowExtensions.SetField%2A> устанавливает значения столбцов в <xref:System.Data.DataRow>.  Оба метода, <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, обрабатывают типы, допускающие значения NULL, поэтому нет необходимости явно проводить проверку на значения NULL, как в предыдущем примере.  Оба метода являются универсальными, поэтому приводить возвращенные данные к определенному типу не нужно.  
  
 В следующем примере используется метод <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` метода <xref:System.Data.DataRowExtensions.Field%2A> и метода <xref:System.Data.DataRowExtensions.SetField%2A>, должен совпадать с типом базового значения.  В противном случае возникнет исключение <xref:System.InvalidCastException>.  Указанное имя столбца также должно совпадать с именем столбца в <xref:System.Data.DataSet>, в противном случае возникнет исключение <xref:System.ArgumentException>.  В обоих случаях исключения возникают во время выполнения при перечислении данных в ходе выполнения запроса.  
  
 Метод <xref:System.Data.DataRowExtensions.SetField%2A> сам по себе не выполняет преобразования типов.  Однако это не означает, что преобразование типов не происходит.  Метод <xref:System.Data.DataRowExtensions.SetField%2A> реализует поведение [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] класса <xref:System.Data.DataRow>.  Преобразование типов может быть выполнено объектом <xref:System.Data.DataRow>, а преобразованное значение затем будет сохранено в объекте <xref:System.Data.DataRow>.  
  
## См. также  
 <xref:System.Data.DataRowExtensions>