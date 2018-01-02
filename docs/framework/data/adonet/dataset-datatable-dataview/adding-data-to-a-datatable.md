---
title: "Добавление данных в таблицу данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 91aa84b0a3d381512faf74f350dc4b43e9a3c598
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adding-data-to-a-datatable"></a>Добавление данных в таблицу данных
После создания объекта <xref:System.Data.DataTable> и определения его структуры с использованием столбцов и ограничений к созданной таблице можно добавлять новые строки данных. Чтобы добавить новую строку, объявите новую переменную типа <xref:System.Data.DataRow>. Новый **DataRow** объект возвращается при вызове <xref:System.Data.DataTable.NewRow%2A> метода. **DataTable** создает **DataRow** объекта на основе структуры таблицы, в соответствии с определением <xref:System.Data.DataColumnCollection>.  
  
 Следующий пример демонстрирует создание новой строки путем вызова **NewRow** метод.  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 После этого можно манипулировать вновь добавленной строкой с помощью индекса или имени столбца, как показано в следующем примере.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 После вставки данных в новую строку, **добавить** метод используется для добавления строки в <xref:System.Data.DataRowCollection>, показанный в следующем коде.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Можно также вызвать **добавить** метод, чтобы добавить новую строку, передавая массив значений, типизированного как <xref:System.Object>, как показано в следующем примере.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Передача массива значений с типом **объекта**в **добавить** метод создает новую строку в таблице и заданию значений столбцов со значениями в массиве объектов. Обратите внимание, что значения в массиве сопоставляются со столбцами последовательно, с учетом порядка этих столбцов в таблице.  
  
 В следующем примере добавляется 10 строк к вновь созданной **клиентов** таблицы.  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
