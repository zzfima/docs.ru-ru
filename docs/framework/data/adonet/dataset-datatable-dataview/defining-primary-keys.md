---
title: Определение первичных ключей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 0f87b1b730eecf0edad75bd87ca8b491b96e1d2b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784704"
---
# <a name="defining-primary-keys"></a>Определение первичных ключей
База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице. Такие столбцы или группы столбцов называются первичными ключами.  
  
 При определении <xref:System.Data.DataColumn> одного объекта в <xref:System.Data.DataTable.PrimaryKey%2A> качестве для <xref:System.Data.DataTable>таблицы автоматически присваивает <xref:System.Data.DataColumn.AllowDBNull%2A> свойству столбца **значение false** , а <xref:System.Data.DataColumn.Unique%2A> свойству — **значение true**. Для первичных ключей с несколькими столбцами автоматически присваивается **значение false**только для свойства **AllowDbNull** .  
  
 Свойство <xref:System.Data.DataTable> PrimaryKey принимает в качестве значения массив из одного или нескольких объектов **DataColumn** , как показано в следующих примерах. В первом примере в качестве первичного ключа определяется один столбец.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 Следующий пример определяет два столбца в качестве первичного ключа.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataTable>
- [Определение схемы DataTable](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
