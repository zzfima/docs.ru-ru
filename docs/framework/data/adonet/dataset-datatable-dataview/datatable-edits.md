---
title: Редактирование таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 473ea9963ce192f42e418bebc8e38971019350e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548564"
---
# <a name="datatable-edits"></a>Редактирование таблиц данных
При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки. <xref:System.Data.DataRowState> Затем устанавливается **Modified**, и изменения принимаются или отвергаются с использованием <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> методы **DataRow**. **DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки, при редактировании его. Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 При изменении значений столбцов **DataRow** напрямую, **DataRow** управляет значениями столбцов с помощью **текущей**, **по умолчанию**, и **Исходного** версий строк. Помимо этих версий строки **BeginEdit**, **EndEdit**, и **CancelEdit** методы используют четвертую версию строки: **Предложенные**. Дополнительные сведения о версиях строк см. в разделе [строки состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 **Предложено** версия строки существует во время операции редактирования, которая начинается вызовом **BeginEdit** и заканчивается с помощью **EndEdit** или **CancelEdit,**  или вызвав **AcceptChanges** или **RejectChanges**.  
  
 Во время операции изменения можно применить логику проверки к отдельным столбцам, оценивая **ProposedValue** в **ColumnChanged** событие **DataTable**. **ColumnChanged** событий содержит **DataColumnChangeEventArgs** , сохранить ссылку для изменяемого столбца и **ProposedValue**. После оценки предложенного значения можно изменить его или отменить изменение. Когда изменение заканчивается, строка выводится из **предложено** состояния.  
  
 Изменения можно подтвердить, вызвав **EndEdit**, или их можно отменить, вызвав **CancelEdit**. Обратите внимание, что, хотя **EndEdit** подтвердить изменения, **набора данных** фактически не принимает изменения до **AcceptChanges** вызывается. Обратите внимание, что при вызове метода **AcceptChanges** до окончания изменений при помощи **EndEdit** или **CancelEdit**, то изменение заканчивается и **предложено** значения строк принимаются для обоих **текущей** и **исходного** версий строк. Таким же образом вызвав **RejectChanges** заканчивает изменения и отменяет **текущей** и **предложено** версий строк. Вызов **EndEdit** или **CancelEdit** после вызова метода **AcceptChanges** или **RejectChanges** не влияет, так как изменение оказало уже завершено.  
  
 Следующий пример демонстрирует, как использовать **BeginEdit** с **EndEdit** и **CancelEdit**. В примере также проверяется **ProposedValue** в **ColumnChanged** событий и решает, следует ли отменить изменения.  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
