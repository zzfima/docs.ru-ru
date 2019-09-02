---
title: Добавление данных в таблицу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 91c635e2bc2ed617e8c45171d9ec7d7359b9ca88
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205489"
---
# <a name="adding-data-to-a-datatable"></a>Добавление данных в таблицу данных
После создания объекта <xref:System.Data.DataTable> и определения его структуры с использованием столбцов и ограничений к созданной таблице можно добавлять новые строки данных. Чтобы добавить новую строку, объявите новую переменную типа <xref:System.Data.DataRow>. При вызове <xref:System.Data.DataTable.NewRow%2A> метода возвращается новый объект **DataRow** . Затем **Таблица** данных создает объект **DataRow** на основе структуры таблицы, как определено в <xref:System.Data.DataColumnCollection>.  
  
 В следующем примере показано, как создать новую строку, вызвав метод **невров** .  
  
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
  
 После вставки данных в новую строку метод **Add** используется для добавления строки <xref:System.Data.DataRowCollection>в, показанной в следующем коде.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Можно также вызвать метод **Add** , чтобы добавить новую строку, передав массив значений, типизированный как <xref:System.Object>, как показано в следующем примере.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Передача массива значений, типизированных как **Object**, в метод **Add** создает новую строку внутри таблицы и устанавливает для ее значений столбцов значения в массиве объектов. Обратите внимание, что значения в массиве сопоставляются со столбцами последовательно, с учетом порядка этих столбцов в таблице.  
  
 В следующем примере в созданную таблицу **Customers** добавляется 10 строк.  
  
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

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Управление данными в DataTable](manipulating-data-in-a-datatable.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
