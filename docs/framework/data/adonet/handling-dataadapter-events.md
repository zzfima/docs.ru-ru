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
# <a name="handling-dataadapter-events"></a><span data-ttu-id="eda1b-102">Обработка событий DataAdapter</span><span class="sxs-lookup"><span data-stu-id="eda1b-102">Handling DataAdapter Events</span></span>
<span data-ttu-id="eda1b-103">В ADO.NET <xref:System.Data.Common.DataAdapter> доступно три события, с помощью которых можно реагировать на изменения, внесенные в источник данных.</span><span class="sxs-lookup"><span data-stu-id="eda1b-103">The ADO.NET <xref:System.Data.Common.DataAdapter> exposes three events that you can use to respond to changes made to data at the data source.</span></span> <span data-ttu-id="eda1b-104">В следующей таблице показаны события `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-104">The following table shows the `DataAdapter` events.</span></span>  
  
|<span data-ttu-id="eda1b-105">Событие</span><span class="sxs-lookup"><span data-stu-id="eda1b-105">Event</span></span>|<span data-ttu-id="eda1b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="eda1b-106">Description</span></span>|  
|-----------|-----------------|  
|`RowUpdating`|<span data-ttu-id="eda1b-107">Операция UPDATE, INSERT или DELETE над строкой (путем вызова одного из методов `Update`) готова к работе.</span><span class="sxs-lookup"><span data-stu-id="eda1b-107">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is about to begin.</span></span>|  
|`RowUpdated`|<span data-ttu-id="eda1b-108">Операция UPDATE, INSERT или DELETE над строкой (путем вызова одного из методов `Update`) завершена.</span><span class="sxs-lookup"><span data-stu-id="eda1b-108">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is complete.</span></span>|  
|`FillError`|<span data-ttu-id="eda1b-109">Во время операции `Fill` произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="eda1b-109">An error has occurred during a `Fill` operation.</span></span>|  
  
## <a name="rowupdating-and-rowupdated"></a><span data-ttu-id="eda1b-110">RowUpdating и RowUpdated</span><span class="sxs-lookup"><span data-stu-id="eda1b-110">RowUpdating and RowUpdated</span></span>  
 <span data-ttu-id="eda1b-111">Событие `RowUpdating` вызывается перед тем, как любое обновление строки в <xref:System.Data.DataSet> будет обработано в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="eda1b-111">`RowUpdating` is raised before any update to a row from the <xref:System.Data.DataSet> has been processed at the data source.</span></span> <span data-ttu-id="eda1b-112">Событие `RowUpdated` вызывается после того, как любое обновление строки из `DataSet` было обработано в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="eda1b-112">`RowUpdated` is raised after any update to a row from the `DataSet` has been processed at the data source.</span></span> <span data-ttu-id="eda1b-113">Поэтому событие `RowUpdating` позволяет изменить операцию обновления до ее выполнения - выполнить дополнительную обработку при обновлении, сохранить ссылку на обновленную строку, отменить текущее обновление, запланировать его для пакетной обработки впоследствии и т. д.</span><span class="sxs-lookup"><span data-stu-id="eda1b-113">As a result, you can use `RowUpdating` to modify update behavior before it happens, to provide additional handling when an update will occur, to retain a reference to an updated row, to cancel the current update and schedule it for a batch process to be processed later, and so on.</span></span> <span data-ttu-id="eda1b-114">Событие `RowUpdated` может оказаться полезным для обработки ошибок и исключений, возникших в ходе обновления.</span><span class="sxs-lookup"><span data-stu-id="eda1b-114">`RowUpdated` is useful for responding to errors and exceptions that occur during the update.</span></span> <span data-ttu-id="eda1b-115">Сведения об ошибке можно добавить в объект `DataSet`, а также в логику повторов и т. д.</span><span class="sxs-lookup"><span data-stu-id="eda1b-115">You can add error information to the `DataSet`, as well as retry logic, and so on.</span></span>  
  
 <span data-ttu-id="eda1b-116">К аргументам <xref:System.Data.Common.RowUpdatingEventArgs> и <xref:System.Data.Common.RowUpdatedEventArgs>, передаваемым событиям `RowUpdating` и `RowUpdated`, относятся свойство `Command` со ссылкой на объект `Command`, применяемый для выполнения обновлений, свойство `Row` со ссылкой на объект `DataRow`, содержащий обновленные сведения, свойство `StatementType`, указывающее тип выполняемого обновления, свойство `TableMapping` (если применимо) и свойство `Status` операции.</span><span class="sxs-lookup"><span data-stu-id="eda1b-116">The <xref:System.Data.Common.RowUpdatingEventArgs> and <xref:System.Data.Common.RowUpdatedEventArgs> arguments passed to the `RowUpdating` and `RowUpdated` events include the following: a `Command` property that references the `Command` object being used to perform the update; a `Row` property that references the `DataRow` object containing the updated information; a `StatementType` property for what type of update is being performed; the `TableMapping`, if applicable; and the `Status` of the operation.</span></span>  
  
 <span data-ttu-id="eda1b-117">С помощью свойства `Status` можно определить, возникла ли в ходе операции ошибка, и при необходимости управлять действиями с текущими и результирующими строками.</span><span class="sxs-lookup"><span data-stu-id="eda1b-117">You can use the `Status` property to determine if an error has occurred during the operation and, if desired, to control the actions against the current and resulting rows.</span></span> <span data-ttu-id="eda1b-118">При выполнении события свойство `Status` совпадает с `Continue` или `ErrorsOccurred`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-118">When the event occurs, the `Status` property equals either `Continue` or `ErrorsOccurred`.</span></span> <span data-ttu-id="eda1b-119">В следующей таблице показаны значения, которые можно назначить свойству `Status` для управления последующими действиями в ходе обновления.</span><span class="sxs-lookup"><span data-stu-id="eda1b-119">The following table shows the values to which you can set the `Status` property in order to control later actions during the update.</span></span>  
  
|<span data-ttu-id="eda1b-120">Состояние</span><span class="sxs-lookup"><span data-stu-id="eda1b-120">Status</span></span>|<span data-ttu-id="eda1b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="eda1b-121">Description</span></span>|  
|------------|-----------------|  
|`Continue`|<span data-ttu-id="eda1b-122">Продолжить операцию обновления.</span><span class="sxs-lookup"><span data-stu-id="eda1b-122">Continue the update operation.</span></span>|  
|`ErrorsOccurred`|<span data-ttu-id="eda1b-123">Прервать операцию обновления и вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="eda1b-123">Abort the update operation and throw an exception.</span></span>|  
|`SkipCurrentRow`|<span data-ttu-id="eda1b-124">Пропустить текущую строку и продолжить операцию обновления.</span><span class="sxs-lookup"><span data-stu-id="eda1b-124">Ignore the current row and continue the update operation.</span></span>|  
|`SkipAllRemainingRows`|<span data-ttu-id="eda1b-125">Прервать операцию обновления без вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="eda1b-125">Abort the update operation but do not throw an exception.</span></span>|  
  
 <span data-ttu-id="eda1b-126">Назначение свойству `Status` значения `ErrorsOccurred` вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="eda1b-126">Setting the `Status` property to `ErrorsOccurred` causes an exception to be thrown.</span></span> <span data-ttu-id="eda1b-127">Вызов того или иного исключения можно задать с помощью свойства `Errors`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-127">You can control which exception is thrown by setting the `Errors` property to the desired exception.</span></span> <span data-ttu-id="eda1b-128">При использовании одного из других значений `Status` исключение не вызывается.</span><span class="sxs-lookup"><span data-stu-id="eda1b-128">Using one of the other values for `Status` prevents an exception from being thrown.</span></span>  
  
 <span data-ttu-id="eda1b-129">Кроме того, для обработки ошибок для обновленных строк можно использовать свойство `ContinueUpdateOnError`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-129">You can also use the `ContinueUpdateOnError` property to handle errors for updated rows.</span></span> <span data-ttu-id="eda1b-130">Если `DataAdapter.ContinueUpdateOnError` имеет значение `true`, когда обновление строки приводит к возникновению исключения, то текст исключения помещается в сведения `RowError` для конкретной строки, и обработка продолжается без вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="eda1b-130">If `DataAdapter.ContinueUpdateOnError` is `true`, when an update to a row results in an exception being thrown, the text of the exception is placed into the `RowError` information of the particular row, and processing continues without throwing an exception.</span></span> <span data-ttu-id="eda1b-131">Это позволяет реагировать на ошибки, когда `Update` завершено, в отличие от события `RowUpdated`, которое позволяет реагировать на ошибки при их возникновении.</span><span class="sxs-lookup"><span data-stu-id="eda1b-131">This enables you to respond to errors when the `Update` is complete, in contrast to the `RowUpdated` event, which enables you to respond to errors when the error is encountered.</span></span>  
  
 <span data-ttu-id="eda1b-132">В следующем образце кода показано, как добавлять и удалять обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="eda1b-132">The following code sample shows how to both add and remove event handlers.</span></span> <span data-ttu-id="eda1b-133">Обработчик события `RowUpdating` ведет журнал всех удаленных записей с временной меткой.</span><span class="sxs-lookup"><span data-stu-id="eda1b-133">The `RowUpdating` event handler writes a log of all deleted records with a time stamp.</span></span> <span data-ttu-id="eda1b-134">Обработчик `RowUpdated` события добавляет `RowError` информацию об ошибке в свойство `DataSet`строки в, подавляет `ContinueUpdateOnError`  =  `true`исключение и продолжает обработку (отражая поведение).</span><span class="sxs-lookup"><span data-stu-id="eda1b-134">The `RowUpdated` event handler adds error information to the `RowError` property of the row in the `DataSet`, suppresses the exception, and continues processing (mirroring the behavior of `ContinueUpdateOnError` = `true`).</span></span>  
  
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
  
## <a name="fillerror"></a><span data-ttu-id="eda1b-135">FillError</span><span class="sxs-lookup"><span data-stu-id="eda1b-135">FillError</span></span>  
 <span data-ttu-id="eda1b-136">`DataAdapter` выдает событие `FillError` при возникновении ошибки во время операции `Fill`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-136">The `DataAdapter` issues the `FillError` event when an error occurs during a `Fill` operation.</span></span> <span data-ttu-id="eda1b-137">Ошибка такого типа обычно возникает, когда данные в добавляемой строке невозможно преобразовать в тип .NET Framework без потери точности.</span><span class="sxs-lookup"><span data-stu-id="eda1b-137">This type of error commonly occurs when the data in the row being added could not be converted to a .NET Framework type without some loss of precision.</span></span>  
  
 <span data-ttu-id="eda1b-138">Если ошибка возникает во время операции `Fill`, то текущая строка не добавляется в `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-138">If an error occurs during a `Fill` operation, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="eda1b-139">Событие `FillError` позволяет устранить ошибку и добавить строку, либо пропустить исключенную строку и продолжить операцию `Fill`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-139">The `FillError` event enables you to resolve the error and add the row, or to ignore the excluded row and continue the `Fill` operation.</span></span>  
  
 <span data-ttu-id="eda1b-140">Аргументы `FillErrorEventArgs`, переданные в событие `FillError` могут содержать несколько свойств, которые позволяют предпринять ответные действия и устранить ошибки.</span><span class="sxs-lookup"><span data-stu-id="eda1b-140">The `FillErrorEventArgs` passed to the `FillError` event can contain several properties that enable you to respond to and resolve errors.</span></span> <span data-ttu-id="eda1b-141">В приведенной ниже таблице показаны свойства объекта `FillErrorEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-141">The following table shows the properties of the `FillErrorEventArgs` object.</span></span>  
  
|<span data-ttu-id="eda1b-142">Свойство</span><span class="sxs-lookup"><span data-stu-id="eda1b-142">Property</span></span>|<span data-ttu-id="eda1b-143">Описание</span><span class="sxs-lookup"><span data-stu-id="eda1b-143">Description</span></span>|  
|--------------|-----------------|  
|`Errors`|<span data-ttu-id="eda1b-144">Возникшее исключение (`Exception`).</span><span class="sxs-lookup"><span data-stu-id="eda1b-144">The `Exception` that occurred.</span></span>|  
|`DataTable`|<span data-ttu-id="eda1b-145">Объект `DataTable` заполнялся, когда возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="eda1b-145">The `DataTable` object being filled when the error occurred.</span></span>|  
|`Values`|<span data-ttu-id="eda1b-146">Массив объектов со значениями строки, которая добавляется при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="eda1b-146">An array of objects that contains the values of the row being added when the error occurred.</span></span> <span data-ttu-id="eda1b-147">Нумерация элементов массива `Values` соответствует нумерации столбцов добавляемой строки.</span><span class="sxs-lookup"><span data-stu-id="eda1b-147">The ordinal references of the `Values` array correspond to the ordinal references of the columns of the row being added.</span></span> <span data-ttu-id="eda1b-148">Например, `Values[0]` - значение, добавляемое как первый столбец строки.</span><span class="sxs-lookup"><span data-stu-id="eda1b-148">For example, `Values[0]` is the value that was being added as the first column of the row.</span></span>|  
|`Continue`|<span data-ttu-id="eda1b-149">Позволяет указать, нужно ли вызывать исключение.</span><span class="sxs-lookup"><span data-stu-id="eda1b-149">Allows you to choose whether or not to throw an exception.</span></span> <span data-ttu-id="eda1b-150">Если свойство `Continue` имеет значение `false`, текущая операция `Fill` будет остановлена с вызовом исключения.</span><span class="sxs-lookup"><span data-stu-id="eda1b-150">Setting the `Continue` property to `false` will halt the current `Fill` operation, and an exception will be thrown.</span></span> <span data-ttu-id="eda1b-151">Если свойство `Continue` имеет значение `true`, то операция `Fill` будет продолжена, несмотря на ошибку.</span><span class="sxs-lookup"><span data-stu-id="eda1b-151">Setting `Continue` to `true` continues the `Fill` operation despite the error.</span></span>|  
  
 <span data-ttu-id="eda1b-152">В следующем примере кода добавляется обработчик события для события `FillError` класса `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="eda1b-152">The following code example adds an event handler for the `FillError` event of the `DataAdapter`.</span></span> <span data-ttu-id="eda1b-153">В коде события `FillError` данный пример определяет потенциальную потерю точности, предоставляя возможность выполнить определенные действия в ответ на исключение.</span><span class="sxs-lookup"><span data-stu-id="eda1b-153">In the `FillError` event code, the example determines if there is the potential for precision loss, providing the opportunity to respond to the exception.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eda1b-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eda1b-154">See also</span></span>

- [<span data-ttu-id="eda1b-155">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="eda1b-155">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="eda1b-156">Обработка событий наборов данных</span><span class="sxs-lookup"><span data-stu-id="eda1b-156">Handling DataSet Events</span></span>](./dataset-datatable-dataview/handling-dataset-events.md)
- [<span data-ttu-id="eda1b-157">Обработка событий таблиц данных</span><span class="sxs-lookup"><span data-stu-id="eda1b-157">Handling DataTable Events</span></span>](./dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="eda1b-158">События</span><span class="sxs-lookup"><span data-stu-id="eda1b-158">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="eda1b-159">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eda1b-159">ADO.NET Overview</span></span>](ado-net-overview.md)
