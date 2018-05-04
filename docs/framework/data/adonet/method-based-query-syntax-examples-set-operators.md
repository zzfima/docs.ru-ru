---
title: Примеры синтаксиса запросов на основе методов. Операторы набора (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 2c95125182a352d3cd2b0b4c51ffac3f74fff5a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a>Примеры синтаксиса запросов на основе методов. Операторы набора (LINQ to DataSet)
Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, и <xref:System.Linq.Enumerable.Union%2A> операторов для выполнения операций сравнения на основе значений наборов строк данных.[ Загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) разделе [сравнение объектов DataRow](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) Дополнительные сведения о <xref:System.Data.DataRowComparer>.  
  
 `FillDataSet` Используется в этих примерах метод определен в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах в этом разделе используются следующие `using` / `Imports` инструкции:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Дополнительные сведения см. в разделе [как: создайте LINQ to DataSet проекта в Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="distinct"></a>Distinct  
  
### <a name="example"></a>Пример  
 В этом примере метод <xref:System.Linq.Enumerable.Distinct%2A> используется для удаления повторяющихся элементов в последовательности.  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a>Except  
  
### <a name="example"></a>Пример  
 В этом примере метод <xref:System.Linq.Enumerable.Except%2A> используется, чтобы вернуть контакты, которые есть в первой таблице, но отсутствуют во второй.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a>Пересечение  
  
### <a name="example"></a>Пример  
 В этом примере используется метод <xref:System.Linq.Enumerable.Intersect%2A>, чтобы вернуть контакты, которые есть в обеих таблицах.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a>Объединение  
  
### <a name="example"></a>Пример  
 В этом примере используется метод <xref:System.Linq.Enumerable.Union%2A> для возврата уникальных контактов из двух таблиц.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a>См. также  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
