---
title: "Изменения объекта DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Изменения объекта DataTable
При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки.  Затем для <xref:System.Data.DataRowState> устанавливается значение **Изменено**, и изменения принимаются или отвергаются с использованием методов <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> объекта **DataRow**.  Объект **DataRow** предоставляет также три метода, которые можно использовать для приостановки состояния строки, пока пользователь выполняет ее изменение.  Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 При изменении значений столбцов непосредственно в **DataRow** объект **DataRow** управляет значениями столбцов с использованием версий строки **Current**, **Default** и **Original**.  Помимо этих версий строки, в методах **BeginEdit**, **EndEdit** и **CancelEdit** используется четвертая версия: **Proposed**.  Дополнительные сведения о версиях строк см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Версия **Proposed** строки существует во время операции изменения, которая начинается вызовом **BeginEdit**, а заканчивается использованием методов **EndEdit** или **CancelEdit**, либо вызовом методов **AcceptChanges** или **RejectChanges**.  
  
 Во время операции изменения к отдельным столбцам можно применить логику проверки, оценив **ProposedValue** в событии **ColumnChanged** таблицы **DataTable**.  Событие **ColumnChanged** содержит **DataColumnChangeEventArgs**, где хранится ссылка на изменяемый столбец и на **ProposedValue**.  После оценки предложенного значения можно изменить его или отменить изменение.  Когда изменение заканчивается, строка выводится из состояния **Proposed**.  
  
 Изменения можно подтвердить, вызвав метод **EndEdit**, либо можно их отменить, вызвав метод **CancelEdit**.  Следует отметить, что в то время как метод **EndEdit** подтверждает изменения, метод **DataSet** фактически не принимает изменения до тех пор, пока не будет вызван метод **AcceptChanges**.  Отметим также, что если метод **AcceptChanges** вызывается до окончания изменений при помощи **EndEdit** или **CancelEdit**, то изменение заканчивается и значения строк **Proposed** принимаются и для версии **Current**, и для версии **Original** строки.  Таким же образом вызов метода **RejectChanges** заканчивает изменения и отменяет версии **Current** и **Proposed** строк.  Вызов метода **EndEdit** или **CancelEdit** после вызова **AcceptChanges** или **RejectChanges** не оказывает никакого влияния, т. к. изменение уже закончено.  
  
 Следующий пример демонстрирует, как использовать метод **BeginEdit** с методами **EndEdit** и **CancelEdit**.  В примере также проверяется **ProposedValue** в событии **ColumnChanged**, выполняется решение, отменить ли изменение.  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## См. также  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataRowVersion>   
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)