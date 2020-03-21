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
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="3e253-102">Добавление данных в таблицу данных</span><span class="sxs-lookup"><span data-stu-id="3e253-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="3e253-103">После создания объекта <xref:System.Data.DataTable> и определения его структуры с использованием столбцов и ограничений к созданной таблице можно добавлять новые строки данных.</span><span class="sxs-lookup"><span data-stu-id="3e253-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="3e253-104">Чтобы добавить новую строку, объявите новую переменную типа <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="3e253-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="3e253-105">При вызове метода возвращается <xref:System.Data.DataTable.NewRow%2A> новый объект **DataRow.**</span><span class="sxs-lookup"><span data-stu-id="3e253-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="3e253-106">Затем **DataTable** создает объект **DataRow** на основе структуры таблицы, <xref:System.Data.DataColumnCollection>определяемой .</span><span class="sxs-lookup"><span data-stu-id="3e253-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="3e253-107">Следующий пример показывает, как создать новую строку, вызывая метод **NewRow.**</span><span class="sxs-lookup"><span data-stu-id="3e253-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="3e253-108">После этого можно манипулировать вновь добавленной строкой с помощью индекса или имени столбца, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3e253-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="3e253-109">После вставки данных в новую строку используется метод <xref:System.Data.DataRowCollection> **Добавления** для добавления строки в строку, показанную в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="3e253-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="3e253-110">Вы также можете вызвать метод **добавления,** чтобы добавить новую <xref:System.Object>строку, перейдя в массив значений, набранных как, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3e253-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="3e253-111">Передавая массив значений, набранный как **объект,** метод **добавления** создает новую строку внутри таблицы и устанавливает значения столбца к значениям в массиве объекта.</span><span class="sxs-lookup"><span data-stu-id="3e253-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="3e253-112">Обратите внимание, что значения в массиве сопоставляются со столбцами последовательно, с учетом порядка этих столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="3e253-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="3e253-113">Следующий пример добавляет 10 строк в недавно созданную таблицу **Клиентов.**</span><span class="sxs-lookup"><span data-stu-id="3e253-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e253-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e253-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="3e253-115">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="3e253-115">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="3e253-116">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3e253-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
