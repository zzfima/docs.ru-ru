---
title: "Добавление данных в DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Добавление данных в DataTable
После создания объекта <xref:System.Data.DataTable> и определения его структуры с использованием столбцов и ограничений к созданной таблице можно добавлять новые строки данных.  Чтобы добавить новую строку, объявите новую переменную типа <xref:System.Data.DataRow>.  При вызове метода <xref:System.Data.DataTable.NewRow%2A> будет возвращен новый объект **DataRow**.  Затем объект **DataTable** создает объект **DataRow** на основе структуры таблицы, определенной в <xref:System.Data.DataColumnCollection>.  
  
 В следующем примере показано, как создать новую строку путем вызова метода **NewRow**.  
  
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
  
 После вставки данных в новую строку для добавления строки в объект <xref:System.Data.DataRowCollection> применяется метод **Add**, показанный в следующем коде.  
  
```vb  
workTable.Rows.Add(workRow)  
  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Также можно вызвать метод **Add** для добавления новой строки путем передачи массива значений с типом <xref:System.Object>, как показано в следующем примере.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Передача массива значений с типом **Object** в метод **Add** приводит к созданию новой строки в таблице и заданию значений столбцов этой строки, соответствующих значениям в массиве объектов.  Обратите внимание, что значения в массиве сопоставляются со столбцами последовательно, с учетом порядка этих столбцов в таблице.  
  
 В следующем примере происходит добавление 10 строк к вновь созданной таблице **Customers**.  
  
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
  
## См. также  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)