---
title: Обработка событий DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: d01198d158c4e1c64f12e8a0756c3d4e599fce74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149548"
---
# <a name="handling-dataadapter-events"></a>Обработка событий DataAdapter
В ADO.NET <xref:System.Data.Common.DataAdapter> доступно три события, с помощью которых можно реагировать на изменения, внесенные в источник данных. В следующей таблице показаны события `DataAdapter`.  
  
|Событие|Описание|  
|-----------|-----------------|  
|`RowUpdating`|Операция UPDATE, INSERT или DELETE над строкой (путем вызова одного из методов `Update`) готова к работе.|  
|`RowUpdated`|Операция UPDATE, INSERT или DELETE над строкой (путем вызова одного из методов `Update`) завершена.|  
|`FillError`|Во время операции `Fill` произошла ошибка.|  
  
## <a name="rowupdating-and-rowupdated"></a>RowUpdating и RowUpdated  
 Событие `RowUpdating` вызывается перед тем, как любое обновление строки в <xref:System.Data.DataSet> будет обработано в источнике данных. Событие `RowUpdated` вызывается после того, как любое обновление строки из `DataSet` было обработано в источнике данных. Поэтому событие `RowUpdating` позволяет изменить операцию обновления до ее выполнения - выполнить дополнительную обработку при обновлении, сохранить ссылку на обновленную строку, отменить текущее обновление, запланировать его для пакетной обработки впоследствии и т. д. Событие `RowUpdated` может оказаться полезным для обработки ошибок и исключений, возникших в ходе обновления. Сведения об ошибке можно добавить в объект `DataSet`, а также в логику повторов и т. д.  
  
 К аргументам <xref:System.Data.Common.RowUpdatingEventArgs> и <xref:System.Data.Common.RowUpdatedEventArgs>, передаваемым событиям `RowUpdating` и `RowUpdated`, относятся свойство `Command` со ссылкой на объект `Command`, применяемый для выполнения обновлений, свойство `Row` со ссылкой на объект `DataRow`, содержащий обновленные сведения, свойство `StatementType`, указывающее тип выполняемого обновления, свойство `TableMapping` (если применимо) и свойство `Status` операции.  
  
 С помощью свойства `Status` можно определить, возникла ли в ходе операции ошибка, и при необходимости управлять действиями с текущими и результирующими строками. При выполнении события свойство `Status` совпадает с `Continue` или `ErrorsOccurred`. В следующей таблице показаны значения, которые можно назначить свойству `Status` для управления последующими действиями в ходе обновления.  
  
|Состояние|Описание|  
|------------|-----------------|  
|`Continue`|Продолжить операцию обновления.|  
|`ErrorsOccurred`|Прервать операцию обновления и вызвать исключение.|  
|`SkipCurrentRow`|Пропустить текущую строку и продолжить операцию обновления.|  
|`SkipAllRemainingRows`|Прервать операцию обновления без вызова исключения.|  
  
 Назначение свойству `Status` значения `ErrorsOccurred` вызовет исключение. Вызов того или иного исключения можно задать с помощью свойства `Errors`. При использовании одного из других значений `Status` исключение не вызывается.  
  
 Кроме того, для обработки ошибок для обновленных строк можно использовать свойство `ContinueUpdateOnError`. Если `DataAdapter.ContinueUpdateOnError` имеет значение `true`, когда обновление строки приводит к возникновению исключения, то текст исключения помещается в сведения `RowError` для конкретной строки, и обработка продолжается без вызова исключения. Это позволяет реагировать на ошибки, когда `Update` завершено, в отличие от события `RowUpdated`, которое позволяет реагировать на ошибки при их возникновении.  
  
 В следующем образце кода показано, как добавлять и удалять обработчики событий. Обработчик события `RowUpdating` ведет журнал всех удаленных записей с временной меткой. Обработчик `RowUpdated` события добавляет `RowError` информацию об ошибке в свойство `DataSet`строки в, подавляет `ContinueUpdateOnError`  =  `true`исключение и продолжает обработку (отражая поведение).  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
' Add handlers.  
AddHandler custAdapter.RowUpdating, New SqlRowUpdatingEventHandler( _  
  AddressOf OnRowUpdating)  
AddHandler custAdapter.RowUpdated, New SqlRowUpdatedEventHandler(  
  AddressOf OnRowUpdated)  
  
' Set DataAdapter command properties, fill DataSet, and modify DataSet.  
  
custAdapter.Update(custDS, "Customers")  
  
' Remove handlers.  
RemoveHandler custAdapter.RowUpdating, _  
  New SqlRowUpdatingEventHandler(AddressOf OnRowUpdating)  
RemoveHandler custAdapter.RowUpdated, _  
  New SqlRowUpdatedEventHandler(AddressOf OnRowUpdated)  
  
Private Shared Sub OnRowUpdating(sender As Object, _  
  args As SqlRowUpdatingEventArgs)  
  If args.StatementType = StatementType.Delete Then  
    Dim tw As System.IO.TextWriter = _  
  System.IO.File.AppendText("Deletes.log")  
    tw.WriteLine( _  
      "{0}: Customer {1} Deleted.", DateTime.Now, args.Row(_  
      "CustomerID", DataRowVersion.Original))  
    tw.Close()  
  End If  
End Sub  
  
Private Shared Sub OnRowUpdated( _  
  sender As Object, args As SqlRowUpdatedEventArgs)  
  If args.Status = UpdateStatus.ErrorsOccurred  
    args.Status = UpdateStatus.SkipCurrentRow  
    args.Row.RowError = args.Errors.Message  
  End If  
End Sub  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
// Add handlers.  
custAdapter.RowUpdating += new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
// Set DataAdapter command properties, fill DataSet, modify DataSet.  
  
custAdapter.Update(custDS, "Customers");  
  
// Remove handlers.  
custAdapter.RowUpdating -= new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated -= new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
protected static void OnRowUpdating(  
  object sender, SqlRowUpdatingEventArgs args)  
{  
  if (args.StatementType == StatementType.Delete)  
  {  
    System.IO.TextWriter tw = System.IO.File.AppendText("Deletes.log");  
    tw.WriteLine(  
      "{0}: Customer {1} Deleted.", DateTime.Now,
       args.Row["CustomerID", DataRowVersion.Original]);  
    tw.Close();  
  }  
}  
  
protected static void OnRowUpdated(  
  object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.Status == UpdateStatus.ErrorsOccurred)  
  {  
    args.Row.RowError = args.Errors.Message;  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="fillerror"></a>FillError  
 `DataAdapter` выдает событие `FillError` при возникновении ошибки во время операции `Fill`. Ошибка такого типа обычно возникает, когда данные в добавляемой строке невозможно преобразовать в тип .NET Framework без потери точности.  
  
 Если ошибка возникает во время операции `Fill`, то текущая строка не добавляется в `DataTable`. Событие `FillError` позволяет устранить ошибку и добавить строку, либо пропустить исключенную строку и продолжить операцию `Fill`.  
  
 Аргументы `FillErrorEventArgs`, переданные в событие `FillError` могут содержать несколько свойств, которые позволяют предпринять ответные действия и устранить ошибки. В приведенной ниже таблице показаны свойства объекта `FillErrorEventArgs`.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|`Errors`|Возникшее исключение (`Exception`).|  
|`DataTable`|Объект `DataTable` заполнялся, когда возникла ошибка.|  
|`Values`|Массив объектов со значениями строки, которая добавляется при возникновении ошибки. Нумерация элементов массива `Values` соответствует нумерации столбцов добавляемой строки. Например, `Values[0]` - значение, добавляемое как первый столбец строки.|  
|`Continue`|Позволяет указать, нужно ли вызывать исключение. Если свойство `Continue` имеет значение `false`, текущая операция `Fill` будет остановлена с вызовом исключения. Если свойство `Continue` имеет значение `true`, то операция `Fill` будет продолжена, несмотря на ошибку.|  
  
 В следующем примере кода добавляется обработчик события для события `FillError` класса `DataAdapter`. В коде события `FillError` данный пример определяет потенциальную потерю точности, предоставляя возможность выполнить определенные действия в ответ на исключение.  
  
```vb  
AddHandler adapter.FillError, New FillErrorEventHandler( _  
  AddressOf FillError)  
  
Dim dataSet As DataSet = New DataSet  
adapter.Fill(dataSet, "ThisTable")  
  
Private Shared Sub FillError(sender As Object, _  
  args As FillErrorEventArgs)  
  If args.Errors.GetType() Is Type.GetType("System.OverflowException") Then  
    ' Code to handle precision loss.  
    ' Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(New Object() _  
      {args.Values(0), args.Values(1), DBNull.Value})  
    ' Set the RowError containing the value for the third column.  
    myRow.RowError = _  
      "OverflowException encountered. Value from data source: " & _  
      args.Values(2)  
    args.Continue = True  
  End If  
End Sub  
```  
  
```csharp  
adapter.FillError += new FillErrorEventHandler(FillError);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "ThisTable");  
  
protected static void FillError(object sender, FillErrorEventArgs args)  
{  
  if (args.Errors.GetType() == typeof(System.OverflowException))  
  {  
    // Code to handle precision loss.  
    //Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(new object[]  
       {args.Values[0], args.Values[1], DBNull.Value});  
    //Set the RowError containing the value for the third column.  
    myRow.RowError =
       "OverflowException Encountered. Value from data source: " +  
       args.Values[2];  
    args.Continue = true;  
  }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Обработка событий наборов данных](./dataset-datatable-dataview/handling-dataset-events.md)
- [Обработка событий таблиц данных](./dataset-datatable-dataview/handling-datatable-events.md)
- [События](../../../standard/events/index.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
