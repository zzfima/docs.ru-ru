---
title: "Управление объектами DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Управление объектами DataView
С помощью класса <xref:System.Data.DataViewManager> можно управлять параметрами представлений во всех таблицах <xref:System.Data.DataView>.  Если есть элемент управления, который нужно связать с несколькими таблицами, например сеткой перехода по связям, то для этого идеально подойдет класс **DataViewManager**.  
  
 Класс **DataViewManager** содержит коллекцию объектов <xref:System.Data.DataViewSetting>, которые используются для установки параметров представления таблиц в <xref:System.Data.DataSet>.  Коллекция <xref:System.Data.DataViewSettingCollection> содержит один объект <xref:System.Data.DataViewSetting> для каждой таблицы в **DataSet**.  С помощью **DataViewSetting** можно задать свойства по умолчанию **ApplyDefaultSort**, **Sort**, **RowFilter** и **RowStateFilter** таблицы.  На **DataViewSetting** конкретной таблицы можно ссылаться по имени или по порядковому номеру, либо путем передачи ссылки на этот конкретный объект таблицы.  Доступ к коллекции объектов **DataViewSetting** можно получить в **DataViewManager** с помощью свойства **DataViewSettings**.  
  
 В следующем примере кода объект **DataSet** заполняется таблицами базы данных **Northwind** SQL Server с именами **Customers**, **Orders** и **Order Details**, создаются связи между таблицами, с помощью диспетчера **DataViewManager** устанавливаются параметры **DataView** по умолчанию, и к **DataViewManager** привязывается **DataGrid**.  В примере устанавливаются параметры **DataView** по умолчанию для всех таблиц **DataSet** для сортировки первичного ключа таблицы \(**ApplyDefaultSort** \= **true**\) и изменяется порядок сортировки таблицы **Customers** для сортировки по **CompanyName**.  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## См. также  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataViewManager>   
 <xref:System.Data.DataViewSetting>   
 <xref:System.Data.DataViewSettingCollection>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)