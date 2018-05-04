---
title: Определение первичных ключей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 21d63aa33e20019f8392b81fb69881296a52cb26
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="defining-primary-keys"></a>Определение первичных ключей
База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице. Такие столбцы или группы столбцов называются первичными ключами.  
  
 При определении одного <xref:System.Data.DataColumn> как <xref:System.Data.DataTable.PrimaryKey%2A> для <xref:System.Data.DataTable>, в таблице автоматически присваивается <xref:System.Data.DataColumn.AllowDBNull%2A> свойство столбца **false** и <xref:System.Data.DataColumn.Unique%2A> свойства  **значение true,**. Для нескольких столбцов первичных ключей, только **AllowDBNull** автоматически присваивается свойству **false**.  
  
 **PrimaryKey** свойство <xref:System.Data.DataTable> получает в качестве значения массив из одного или нескольких **DataColumn** объекты, как показано в следующих примерах. В первом примере в качестве первичного ключа определяется один столбец.  
  
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
 <xref:System.Data.DataTable>  
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
