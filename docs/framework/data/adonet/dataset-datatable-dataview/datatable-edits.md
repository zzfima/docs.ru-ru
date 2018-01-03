---
title: "Редактирование таблиц данных"
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3d06fc3a82457972db94f82964942f446bb761be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datatable-edits"></a>Редактирование таблиц данных
При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки. <xref:System.Data.DataRowState> Присваивается значение **Modified**, и изменения принимаются или отклонить при помощи <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> методы **DataRow**. **DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки, пока вы работаете. Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 При изменении значений столбцов **DataRow** напрямую, **DataRow** управляет значениями столбцов с помощью **текущей**, **по умолчанию**, и **Исходного** версий строк. Помимо этих версий строки **BeginEdit**, **EndEdit**, и **CancelEdit** методы используют четвертая версия: **предложено**. Дополнительные сведения о версиях строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 **Предложено** версия строки существует во время операции изменения, которая начинается вызовом **BeginEdit** и заканчивающийся либо с помощью **EndEdit** или **CancelEdit**  или вызвав **AcceptChanges** или **RejectChanges**.  
  
 Во время операции изменения можно применить логику проверки в отдельные столбцы, оценивая **ProposedValue** в **ColumnChanged** событие **DataTable**. **ColumnChanged** содержит событие **DataColumnChangeEventArgs** , сохранить ссылку для изменяемого столбца и **ProposedValue**. После оценки предложенного значения можно изменить его или отменить изменение. Когда изменение заканчивается, строка переходит из **предложено** состояния.  
  
 Изменения можно подтвердить, вызвав **EndEdit**, или отменить, вызвав **CancelEdit**. Обратите внимание, что, хотя **EndEdit** подтвердить изменения, **DataSet** фактически не принимает изменения до **AcceptChanges** вызывается. Обратите внимание, что при вызове метода **AcceptChanges** до окончания изменений при помощи **EndEdit** или **CancelEdit**, то изменение заканчивается и **предложено** значения строк принимаются для обоих **текущей** и **исходного** версий строк. Таким же образом вызвав **RejectChanges** заканчивает изменения и отменяет **текущей** и **предложено** версий строк. Вызов **EndEdit** или **CancelEdit** после вызова **AcceptChanges** или **RejectChanges** имеет смысл, поскольку редактирование уже завершено.  
  
 В следующем примере демонстрируется использование **BeginEdit** с **EndEdit** и **CancelEdit**. В примере также проверяется **ProposedValue** в **ColumnChanged** событий и решает, следует ли отменить изменение.  
  
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
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
