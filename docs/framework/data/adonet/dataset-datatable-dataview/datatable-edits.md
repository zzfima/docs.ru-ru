---
title: Редактирование таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: a970ebda76f5bb6bdea704dabef2ee305436c613
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205013"
---
# <a name="datatable-edits"></a>Редактирование таблиц данных
При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки. <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A>Затем задается значение Modified, и изменения принимаются или отклоняются с помощью методов или объекта DataRow. <xref:System.Data.DataRowState> **DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки при ее редактировании. Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 При непосредственном изменении значений столбцов в **DataRow** объект **DataRow** управляет значениями столбцов, используя **текущие**версии строк, **используемые по умолчанию**и **исходные** . В дополнение к этим версиям строк методы **BeginEdit**, **EndEdit**и **CancelEdit** используют четвертую версию строки: **Предложено**. Дополнительные сведения о версиях строк см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).  
  
 Предлагаемая версия строки существует во время операции изменения, которая начинается с вызова **BeginEdit** и заканчивается либо с помощью **EndEdit** **, либо CancelEdit,** либо путем вызова **метода AcceptChanges** или **RejectChanges**.  
  
 Во время операции редактирования можно применить логику проверки к отдельным столбцам, оценивая **пропоседвалуе** в событии **колумнчанжед** объекта **DataTable**. Событие **колумнчанжед** содержит **датаколумнчанжеевентаргс** , которые сохраняют ссылку на изменяемый столбец и на **пропоседвалуе**. После оценки предложенного значения можно изменить его или отменить изменение. После завершения редактирования строка перемещается из предложенного состояния.  
  
 Вы можете подтвердить изменения, вызвав **EndEdit**, или отменить их, вызвав **CancelEdit**. Обратите внимание, что хотя **EndEdit** подтверждает изменения, **набор данных** фактически не принимает изменения, пока не будет вызван метод **AcceptChanges** . Обратите внимание, что если метод **AcceptChanges** вызывается до завершения операции Edit с **EndEdit** или **CancelEdit**, то редактирование завершается и **предлагаемые** значения строки принимаются как для **текущей** , так и для **исходной** версий строк. Аналогичным образом, вызов **RejectChanges** завершает изменение и отменяет **текущую** и предлагаемую версию строки. Вызов метода **EndEdit** или **CancelEdit** после вызова **метода AcceptChanges** или **RejectChanges** не действует, так как редактирование уже завершено.  
  
 В следующем примере показано, как использовать **BeginEdit** с **EndEdit** и **CancelEdit**. В примере также проверяется **пропоседвалуе** в событии **колумнчанжед** и принимается решение, следует ли отменить изменение.  
  
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
- [Управление данными в DataTable](manipulating-data-in-a-datatable.md)
- [Обработка событий DataTable](handling-datatable-events.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
