---
title: Создание столбцов AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034376"
---
# <a name="creating-autoincrement-columns"></a>Создание столбцов AutoIncrement
Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице. Для создания заданы с автоматическим приращением <xref:System.Data.DataColumn>, задайте <xref:System.Data.DataColumn.AutoIncrement%2A> свойство столбца **true**. <xref:System.Data.DataColumn> Берется за значения, определенного в <xref:System.Data.DataColumn.AutoIncrementSeed%2A> свойство и в каждой добавляемой строке значение **AutoIncrement** столбца увеличивается на значение, определенное в <xref:System.Data.DataColumn.AutoIncrementStep%2A> свойства столбца.  
  
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

- <xref:System.Data.DataColumn>
- [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
