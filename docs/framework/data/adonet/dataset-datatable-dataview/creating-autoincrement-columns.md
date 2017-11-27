---
title: "Создание столбцов AutoIncrement"
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
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7bc71e3ae817bbdaf5dc14f22041e297cab949b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-autoincrement-columns"></a>Создание столбцов AutoIncrement
Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице. Для создания Автоувеличение <xref:System.Data.DataColumn>, задайте <xref:System.Data.DataColumn.AutoIncrement%2A> свойство столбца **true**. <xref:System.Data.DataColumn> Затем начинается со значения, определенного в <xref:System.Data.DataColumn.AutoIncrementSeed%2A> свойство и в каждой добавляемой строке значение **AutoIncrement** столбца увеличивается на значение, определенное в <xref:System.Data.DataColumn.AutoIncrementStep%2A> свойство столбца.  
  
 Для **AutoIncrement** столбцы, мы рекомендуем <xref:System.Data.DataColumn.ReadOnly%2A> свойство **DataColumn** присвоить **true**.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataColumn>  
 [Определение схемы таблицы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
