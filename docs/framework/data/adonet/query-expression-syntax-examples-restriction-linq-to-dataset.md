---
title: Примеры синтаксиса выражений запросов. Ограничение (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 04a7b2027ac956d14086f94527b10d253749949d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794665"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a>Примеры синтаксиса выражений запросов. Ограничение (LINQ to DataSet)
В примерах данного раздела показано, как использовать метод <xref:System.Linq.Enumerable.Where%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.  
  
 Метод, используемый в этих примерах, задается при [загрузке данных в набор данных.](loading-data-into-a-dataset.md) `FillDataSet`  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах этого раздела используются следующие `using` / `Imports` инструкции:  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="where"></a>Where  
  
### <a name="example"></a>Пример  
 В этом примере происходит возврат всех заказов в оперативном режиме.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a>Пример  
 В следующем примере возвращаются заказы, количество единиц товара в которых больше 2 и меньше 6.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a>Пример  
 В этом примере возвращаются все продукты красного цвета.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a>Пример  
 В этом примере метод <xref:System.Linq.Enumerable.Where%2A> используется для поиска заказов, сделанных после 1 декабря 2002 г. Затем с помощью метода <xref:System.Data.DataRow.GetChildRows%2A> определяются подробности каждого заказа.  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a>См. также

- [Загрузка данных в DataSet](loading-data-into-a-dataset.md)
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
- [Общие сведения о стандартных операторах запроса (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
