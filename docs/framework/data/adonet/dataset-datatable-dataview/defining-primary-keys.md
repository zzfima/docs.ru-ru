---
title: "Определение первичных ключей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Определение первичных ключей
База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице.  Такие столбцы или группы столбцов называются первичными ключами.  
  
 При определении одного столбца <xref:System.Data.DataColumn> как <xref:System.Data.DataTable.PrimaryKey%2A> для <xref:System.Data.DataTable> в таблице автоматически присваивается свойству <xref:System.Data.DataColumn.AllowDBNull%2A> значение **false**, а свойству <xref:System.Data.DataColumn.Unique%2A> \- значение **true**.  Для первичных ключей, содержащих несколько столбцов, значение **false** автоматически присваивается только свойству **AllowDBNull**.  
  
 Свойство **PrimaryKey** таблицы <xref:System.Data.DataTable> получает в качестве значения массив из одного или нескольких объектов **DataColumn**, как показано в следующих примерах.  В первом примере в качестве первичного ключа определяется один столбец.  
  
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
  
## См. также  
 <xref:System.Data.DataTable>   
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)