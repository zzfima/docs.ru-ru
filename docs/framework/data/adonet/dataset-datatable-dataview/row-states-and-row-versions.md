---
title: "Состояния и версии строк | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Состояния и версии строк
ADO.NET управляет строками таблиц с помощью состояний и версий строк.  Состояние строки указывает на статус строки, а версии строк хранят значения изменения строки, включая текущее, исходное и применяемое по умолчанию значения.  Например, после внесения изменения в столбец строки эта строка будет иметь состояние `Modified` и две версии: `Current`, содержащую текущие значения, и `Original`, содержащую значения этой строки до изменения столбца.  
  
 Каждый объект <xref:System.Data.DataRow> имеет свойство <xref:System.Data.DataRow.RowState%2A>, которое отображает текущее состояние строки.  В следующей таблице кратко описано каждое из значений перечисления `RowState`.  
  
|Значение перечисления RowState|Описание|  
|------------------------------------|--------------|  
|<xref:System.Data.DataRowState>|Не было выполнено никаких изменений с момента последнего вызова метода `AcceptChanges` или с момента создания строки методом `DataAdapter.Fill`.|  
|<xref:System.Data.DataRowState>|Строка добавлена к таблице, но метод `AcceptChanges` не вызывался.|  
|<xref:System.Data.DataRowState>|Изменены некоторые элементы строки.|  
|<xref:System.Data.DataRowState>|Строка удалена из таблицы, но метод `AcceptChanges` не вызывался.|  
|<xref:System.Data.DataRowState>|Строка не принадлежит ни к одной коллекции `DataRowCollection`.  Свойство `RowState` только что созданной строки имеет значение `Detached`.  После добавления новой строки `DataRow` к коллекции `DataRowCollection` с помощью вызова метода `Add` свойству `RowState` присваивается значение `Added`.<br /><br /> Значение `Detached` также присваивается строке, удаленной из `DataRowCollection` с помощью метода `Remove` или путем последовательного вызова методов `Delete` и `AcceptChanges`.|  
  
 Если метод `AcceptChanges` вызывается для <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или <xref:System.Data.DataRow>, удаляются все строки со значением состояния `Deleted`.  Оставшимся строкам присваивается состояние `Unchanged`, а значения в версии строки `Original` перезаписываются значениями версии строки `Current`.  Если вызывается метод `RejectChanges`, удаляются все строки со значением состояния `Added`.  Оставшимся строкам присваивается состояние `Unchanged`, а значения в версии строки `Current` перезаписываются значениями версии строки `Original`.  
  
 Можно просматривать разные версии строки, передавая параметр <xref:System.Data.DataRowVersion> со ссылкой на столбец, как показано в следующем примере.  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 В следующей таблице кратко описано каждое из значений перечисления `DataRowVersion`.  
  
|Значение DataRowVersion|Описание|  
|-----------------------------|--------------|  
|<xref:System.Data.DataRowVersion>|Текущие значения строки.  Эта версия не существует для строк, у которых `RowState` равно `Deleted`.|  
|<xref:System.Data.DataRowVersion>|Версия по умолчанию для конкретной строки.  Версия по умолчанию для строки `Added`, `Modified` и `Unchanged` представляет собой `Current`.  Версия по умолчанию для строки `Deleted` \- `Original`.  Версия по умолчанию для строки `Detached` \- `Proposed`.|  
|<xref:System.Data.DataRowVersion>|Исходные значения строки.  Эта версия не существует для строк, у которых `RowState` равно `Added`.|  
|<xref:System.Data.DataRowVersion>|Предложенные значения строки.  Эта версия строки существует в течение операции изменения строки или для строки, не содержащейся в коллекции `DataRowCollection`.|  
  
 Можно проверить, имеет ли `DataRow` конкретную версию строки, вызвав метод <xref:System.Data.DataRow.HasVersion%2A> и передав ему `DataRowVersion` в качестве аргумента.  Например, `DataRow.HasVersion(DataRowVersion.Original)` возвратит значение `false` для только что добавленных строк перед тем, как был вызван метод `AcceptChanges`.  
  
 В следующем примере кода показаны значения во всех удаленных строках таблицы.  Строки `Deleted` не имеют версии строки `Current`, поэтому для доступа к значениям столбцов необходимо передать аргумент `DataRowVersion.Original`.  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## См. также  
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Объекты DataAdapter и DataReader](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)