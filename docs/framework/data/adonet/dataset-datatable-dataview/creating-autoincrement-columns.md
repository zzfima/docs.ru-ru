---
title: "Создание столбцов AutoIncrement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Создание столбцов AutoIncrement
Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице.  Чтобы создать столбец <xref:System.Data.DataColumn> с автоматически увеличивающимися значениями, задайте для свойства <xref:System.Data.DataColumn.AutoIncrement%2A> столбца значение **true**.  После этого в объекте <xref:System.Data.DataColumn> берется за исходное то значение, которое определено в свойстве <xref:System.Data.DataColumn.AutoIncrementSeed%2A>, и в каждой добавляемой строке значение в столбце **AutoIncrement** возрастает на величину, указанную в свойстве <xref:System.Data.DataColumn.AutoIncrementStep%2A> столбца.  
  
 Применительно к столбцам **AutoIncrement** рекомендуется, чтобы свойству <xref:System.Data.DataColumn.ReadOnly%2A> объекта **DataColumn** было присвоено значение **true**.  
  
 В следующем примере показано, как создать столбец, значения в котором начинаются с 200 и каждый раз увеличиваются с шагом 3.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## См. также  
 <xref:System.Data.DataColumn>   
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)