---
title: "Сравнение объектов DataRow (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Сравнение объектов DataRow (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] определяет различные операторы для работы с наборами, позволяющие сравнивать элементы и определять их равенство.  [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] предоставляет следующие операторы для работы с наборами:  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 Эти операторы сравнивают элементы путем вызова методов <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> и <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> для каждого набора элементов.  Для объектов <xref:System.Data.DataRow> эти операторы выполняют ссылочное сравнение, которое в общем случае не является идеальным для операторов наборов, выполняющихся над табличными данными.  Для операторов наборов обычно требуется определить, являются ли равными значения элементов, а не ссылки на элементы.  Поэтому в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] был добавлен класс <xref:System.Data.DataRowComparer>.  Этот класс можно использовать для сравнения значений в строках.  
  
 Класс <xref:System.Data.DataRowComparer> содержит реализацию сравнения значений для объектов <xref:System.Data.DataRow>, поэтому его можно использовать в операциях над наборами, таких как <xref:System.Linq.Enumerable.Distinct%2A>.  Этот класс нельзя создать напрямую, вместо этого необходимо использовать свойство <xref:System.Data.DataRowComparer.Default%2A> для возврата экземпляра <xref:System.Data.DataRowComparer>.  Затем вызывается метод <xref:System.Data.DataRowComparer.Equals%2A>, которому в качестве входных параметров передаются два сравниваемых объекта <xref:System.Data.DataRow>.  Метод <xref:System.Data.DataRowComparer.Equals%2A> возвращает значение `true`, если упорядоченные наборы значений столбцов в обоих объектах <xref:System.Data.DataRow> равны, в противном случае значение `false`.  
  
## Пример  
 В этом примере инструкция `Intersect` используется для возврата контактов, находящихся в обеих таблицах.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### Пример  
 В следующем примере сравниваются две строки и возвращаются их хэш\-коды.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## См. также  
 <xref:System.Data.DataRowComparer>   
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)