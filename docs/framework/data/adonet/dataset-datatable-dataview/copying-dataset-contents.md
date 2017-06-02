---
title: "Копирование содержимого объекта DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Копирование содержимого объекта DataSet
Можно создать копию объекта <xref:System.Data.DataSet>, чтобы работать с данными, не затрагивая первоначальные данные, или обрабатывать подмножество данных из **DataSet**.  При копировании объекта **DataSet** можно:  
  
-   Создать точную копию **DataSet**, включая схему, данные, информацию о состоянии строк и версиях строк.  
  
-   Создать **DataSet**, который имеет схему существующего **DataSet**, но содержит только строки, которые были изменены.  Можно возвратить все строки, которые были изменены, или задать конкретное значение **DataRowState**.  Дополнительные сведения о состояниях строк см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Скопировать только схему \(реляционную структуру\) **DataSet**, не копируя никаких строк.  Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Чтобы создать точную копию **DataSet**, которая включает и схему, и данные, используйте метод <xref:System.Data.DataSet.Copy%2A> набора данных **DataSet**.  В следующем примере кода показано, как создать точную копию **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Чтобы создать копию объекта **DataSet**, которая будет включать в себя схему и только данные, представляющие строки **Added**, **Modified** или **Deleted**, используйте метод <xref:System.Data.DataSet.GetChanges%2A> объекта **DataSet**.  Можно также использовать метод **GetChanges** для возврата только строк с указанным состоянием строки, передавая значение **DataRowState** при вызове **GetChanges**.  В следующем примере кода показано, как передать значение **DataRowState** при вызове метода **GetChanges**.  
  
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
  
 Чтобы создать копию объекта **DataSet**, которая будет включать в себя только схему, используйте метод <xref:System.Data.DataSet.Clone%2A> объекта **DataSet**.  Можно также добавить существующие строки к клонированному **DataSet**, используя метод **ImportRow** объекта **DataTable**.  Метод **ImportRow** добавляет к указанной таблице данные, сведения о состоянии строк и о версиях строк.  Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.  
  
 В следующем примере кода создается клон **DataSet**, а затем в таблицу **Customers** добавляются строки первоначального **DataSet** из клона **DataSet**, относящиеся к заказчикам, для которых в столбце **CountryRegion** имеется значение «Germany».  
  
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
  
## См. также  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)