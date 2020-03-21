---
title: Редактирование таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151264"
---
# <a name="datatable-edits"></a>Редактирование таблиц данных
При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки. Затем <xref:System.Data.DataRowState> устанавливается на **изменение,** и изменения принимаются <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> отклоняются с помощью или методов **DataRow.** **DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки во время редактирования. Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 При непосредственном изменении значений столбца в **DataRow** **DataRow DataRow** управляет значениями столбца с помощью версий **тока,** **по умолчанию**и **исходного** ряда. В дополнение к этим версиям строки, методы **BeginEdit,** **EndEdit**и **CancelEdit** используют версию четвертой строки: **Предложено.** Для получения дополнительной информации о строке версии, см [строки государств и строки версии](row-states-and-row-versions.md).  
  
 **Предлагаемая** строка версия существует во время операции по изменению, которая начинается с вызова **BeginEdit** и заканчивается либо с помощью **EndEdit** или **CancelEdit,** либо путем вызова **AcceptChanges** или **RejectChanges.**  
  
 Во время операции по изменению необходимо применить логику проверки к отдельным столбикам, оценив **ажиотальное значение** в случае **OfThe.** **DataTable** Событие **ColumnChanged** содержит **DataColumnChangeEventArgs,** которые сохраняют ссылку на изменяемую колонку и на **предложенную стоимость.** После оценки предложенного значения можно изменить его или отменить изменение. По окончании действия строки строка выходит из **состояния Предложенного.**  
  
 Вы можете подтвердить правки, позвонив **в EndEdit,** или отменить их, позвонив **в CancelEdit.** Обратите внимание, что в то время как **EndEdit** подтверждает ваши изменения, **DataSet** фактически не принимает изменения до тех пор, пока **acceptChanges** не будет вызван. Обратите внимание также, что если вы называете **AcceptChanges** до того, как закончите исправление с **помощью EndEdit** или **CancelEdit,** то изменение завершено, а значения **предлагаемых** строк принимаются как для **текущей,** так и **для исходной** версий строки. Таким же образом вызов **RejectChanges** завершает изменение и отбрасывает **версии текущей** и **предлагаемой** строки. Вызов **EndEdit** или **CancelEdit** после вызова **AcceptChanges** или **RejectChanges** не имеет никакого эффекта, поскольку изменение уже завершено.  
  
 Следующий пример показывает, как использовать **BeginEdit** с **EndEdit** и **CancelEdit**. Пример также проверяет **предлагаемое значение** в событии **ColumnChanged** и решает, следует ли отменить изменение.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Обработка событий таблиц данных](handling-datatable-events.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
