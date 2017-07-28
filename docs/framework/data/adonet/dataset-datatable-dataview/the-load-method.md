---
title: "Метод Load | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Метод Load
Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных.  Это перегруженный метод, который в своей простейшей форме имеет единственный параметр, **DataReader**.  В этой форме он просто загружает строки в таблицу **DataTable**.  Дополнительно можно задать параметр **LoadOption**, который управляет добавлением данных в таблицу **DataTable**.  
  
 Параметр **LoadOption** особенно удобен в тех случаях, когда объект **DataTable** уже содержит строки данных, поскольку позволяет описать, как входящие данные из источника данных должны быть объединены с данными, уже находящимися в таблице.  Например, значение **PreserveCurrentValues** этого параметра \(используемое по умолчанию\) указывает, что в случаях, если в объекте **DataTable** какая\-то строка отмечена как **Added**, значению **Original** каждого столбца присваивается содержимое соответствующей строки из источника данных.  Использование значения **Current** приводит к сохранению значений, присвоенных при добавлении строки, а параметру строки **RowState** присваивается значение **Changed**.  
  
 В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.  
  
|Значение LoadOption|Описание|  
|-------------------------|--------------|  
|**OverwriteRow**|Если входящие строки имеют такое же значение **PrimaryKey**, что и одна из строк, уже находящихся в объекте **DataTable**, то значения **Original** и **Current** каждого столбца заменяются значениями из входящей строки, а свойству **RowState** присваивается значение **Unchanged**.<br /><br /> Строки из источника данных, которые еще не существуют в объекте **DataTable**, добавляются со свойством **RowState**, равным **Unchanged**.<br /><br /> Если используются указанные значения параметров, то содержимое объекта **DataTable** и становится равным содержимому источника данных.|  
|**PreserveCurrentValues \(значение по умолчанию\)**|Если входящие строки имеют такое же значение **PrimaryKey**, что и одна из строк, уже находящихся в объекте **DataTable**, то значение **Original** устанавливается равным содержимому входящей строки, а значение **Current** не изменяется.<br /><br /> Если свойство **RowState** имеет значение **Added** или **Modified**, то ему присваивается значение **Modified**.<br /><br /> Если свойство **RowState** имело значение **Deleted**, то оно остается равным **Deleted**.<br /><br /> Строки из источника данных, которые пока еще отсутствуют в объекте **DataTable**, добавляются, а свойству **RowState** присваивается значение **Unchanged**.|  
|**UpdateCurrentValues**|Если входящие строки имеют такое же значение **PrimaryKey**, что и одна из строк, уже находящихся в объекте **DataTable**, то значение **Current** копируется в значение **Original**, после чего значению **Current** присваивается содержимое входящей строки.<br /><br /> Если свойство **RowState** в объекте **DataTable** имело значение **Added**, то это свойство **RowState** остается равным **Added**.  Для строк, отмеченных как **Modified** или **Deleted**, свойству **RowState** присваивается значение **Modified**.<br /><br /> Строки из источника данных, которые пока еще отсутствуют в объекте **DataTable**, добавляются, а свойству **RowState** присваивается значение **Added**.|  
  
 В следующем образце метод **Load** используется для отображения списка дней рождения сотрудников, представленных в базе данных **Northwind**.  
  
 \[Visual Basic\]  
  
```  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## См. также  
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)