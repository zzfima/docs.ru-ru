---
title: Создание столбцов выражений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: db38d42e9c7dc1657e06030599ae2b8ba66ef6b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549880"
---
# <a name="creating-expression-columns"></a>Создание столбцов выражений
Можно определить выражение для столбца, позволяя тем самым хранить в нем значение, вычисляемое из значений других столбцов той же строки или из значений столбцов нескольких строк таблицы. Для определения вычисляемого выражения используется свойство <xref:System.Data.DataColumn.Expression%2A> целевого столбца, свойство <xref:System.Data.DataColumn.ColumnName%2A> - для ссылки на другие столбцы в выражении. Тип данных <xref:System.Data.DataColumn.DataType%2A> столбца выражения должен соответствовать типу данных значения, возвращаемого выражением.  
  
 В следующей таблице приведен список возможного использования столбцов выражений в таблице.  
  
|Тип выражения|Пример|  
|---------------------|-------------|  
|Сравнение|"Total >= 500"|  
|Вычисление|"UnitPrice * Quantity"|  
|Статистическая обработка|Sum(Price)|  
  
 Можно задать **выражение** свойство на существующем **DataColumn** объекта, или можно включить свойство как третий аргумент, передаваемый в <xref:System.Data.DataColumn> конструктора, как показано в следующем примере.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Выражение может содержать ссылки на другие столбцы выражений, но циклическая ссылка, при которой два выражения ссылаются друг на друга, вызовет исключение. Правила написания выражений, см. в разделе <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.  
  
## <a name="see-also"></a>См. также
- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
