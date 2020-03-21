---
title: Добавление данных в таблицу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151537"
---
# <a name="adding-data-to-a-datatable"></a>Добавление данных в таблицу данных
После создания объекта <xref:System.Data.DataTable> и определения его структуры с использованием столбцов и ограничений к созданной таблице можно добавлять новые строки данных. Чтобы добавить новую строку, объявите новую переменную типа <xref:System.Data.DataRow>. При вызове метода возвращается <xref:System.Data.DataTable.NewRow%2A> новый объект **DataRow.** Затем **DataTable** создает объект **DataRow** на основе структуры таблицы, <xref:System.Data.DataColumnCollection>определяемой .  
  
 Следующий пример показывает, как создать новую строку, вызывая метод **NewRow.**  
  
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
  
 После вставки данных в новую строку используется метод <xref:System.Data.DataRowCollection> **Добавления** для добавления строки в строку, показанную в следующем коде.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Вы также можете вызвать метод **добавления,** чтобы добавить новую <xref:System.Object>строку, перейдя в массив значений, набранных как, как показано в следующем примере.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Передавая массив значений, набранный как **объект,** метод **добавления** создает новую строку внутри таблицы и устанавливает значения столбца к значениям в массиве объекта. Обратите внимание, что значения в массиве сопоставляются со столбцами последовательно, с учетом порядка этих столбцов в таблице.  
  
 Следующий пример добавляет 10 строк в недавно созданную таблицу **Клиентов.**  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
