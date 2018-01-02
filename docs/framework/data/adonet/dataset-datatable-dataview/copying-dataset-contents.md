---
title: "Копирование содержимого набора данных"
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
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d8f9eac80d7a6679e7b3717446e79caf54a5fed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="copying-dataset-contents"></a>Копирование содержимого набора данных
Можно создать копию <xref:System.Data.DataSet> , чтобы работать с данными, не затрагивая исходные данные, или работать с подмножеством данных из **набора данных**. При копировании **набора данных**, вы можете:  
  
-   Создать точную копию объекта **набора данных**, включая схему, данные, сведения о состоянии строк и версии строк.  
  
-   Создание **набора данных** , содержащий схему существующей **набора данных**, но только те строки, которые были изменены. Возвращает все строки, которые были изменены или указать конкретный **DataRowState**. Дополнительные сведения о состояниях строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Копирование схемы или реляционной структуры **набора данных** , не копируя никаких строк. Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Чтобы создать точную копию объекта **DataSet** , включает в себя схему и данные, используйте <xref:System.Data.DataSet.Copy%2A> метод **набора данных**. В следующем примере кода показано, как создать точную копию объекта **набора данных**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Чтобы создать копию **набора данных** схемы, и только данные, представляющие **Added**, **Modified**, или **Deleted** строк, используйте <xref:System.Data.DataSet.GetChanges%2A> метод **набора данных**. Можно также использовать **GetChanges** для возврата только строк с указанным состоянием строки, передавая **DataRowState** при вызове **GetChanges**. В следующем примере кода показано, как передать **DataRowState** при вызове **GetChanges**.  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 Чтобы создать копию **DataSet** , включающую только схему, используйте <xref:System.Data.DataSet.Clone%2A> метод **набора данных**. Можно также добавить существующие строки к клонированному **DataSet** с помощью **ImportRow** метод **DataTable**. **ImportRow** добавляет к указанной таблице данных, строк состояния и сведения о версии строки. Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.  
  
 В следующем примере кода создается клон **DataSet** и затем добавляются строки первоначального **DataSet** для **клиентов** в таблицу **набора данных**  клон для клиентов, где **CountryRegion** столбец имеет значение «Germany».  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
