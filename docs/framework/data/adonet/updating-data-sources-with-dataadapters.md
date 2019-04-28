---
title: Обновление источников данных с объектами DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: 548e374fbabee57e756d06e5cb56a59f8e97a47c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756277"
---
# <a name="updating-data-sources-with-dataadapters"></a><span data-ttu-id="bafed-102">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="bafed-102">Updating Data Sources with DataAdapters</span></span>
<span data-ttu-id="bafed-103">Метод `Update` объекта <xref:System.Data.Common.DataAdapter> вызывается для решения задачи по передаче изменений из <xref:System.Data.DataSet> обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-103">The `Update` method of the <xref:System.Data.Common.DataAdapter> is called to resolve changes from a <xref:System.Data.DataSet> back to the data source.</span></span> <span data-ttu-id="bafed-104">Метод `Update`, как и метод `Fill`, принимает в качестве аргументов экземпляр `DataSet`, а также (необязательно) объект <xref:System.Data.DataTable> или имя `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="bafed-104">The `Update` method, like the `Fill` method, takes as arguments an instance of a `DataSet`, and an optional <xref:System.Data.DataTable> object or `DataTable` name.</span></span> <span data-ttu-id="bafed-105">Экземпляр `DataSet` представляет собой объект `DataSet`, который содержит выполненные изменения, а `DataTable` указывает на таблицу, из которой должны быть получены эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bafed-105">The `DataSet` instance is the `DataSet` that contains the changes that have been made, and the `DataTable` identifies the table from which to retrieve the changes.</span></span> <span data-ttu-id="bafed-106">Если ни один объект `DataTable` не задан, используется первый объект `DataTable` в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-106">If no `DataTable` is specified, the first `DataTable` in the `DataSet` is used.</span></span>  
  
 <span data-ttu-id="bafed-107">При вызове метода `Update` в `DataAdapter` анализируются внесенные изменения и выполняется соответствующая команда (INSERT, UPDATE или DELETE).</span><span class="sxs-lookup"><span data-stu-id="bafed-107">When you call the `Update` method, the `DataAdapter` analyzes the changes that have been made and executes the appropriate command (INSERT, UPDATE, or DELETE).</span></span> <span data-ttu-id="bafed-108">Если в `DataAdapter` обнаруживается изменение в <xref:System.Data.DataRow>, то в этом объекте используется команда <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> или <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> для обработки этого изменения.</span><span class="sxs-lookup"><span data-stu-id="bafed-108">When the `DataAdapter` encounters a change to a <xref:System.Data.DataRow>, it uses the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, or <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> to process the change.</span></span> <span data-ttu-id="bafed-109">Это позволяет максимально повысить производительность приложения ADO.NET путем задания синтаксиса команды во время разработки, а также, по возможности, за счет применения хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="bafed-109">This allows you to maximize the performance of your ADO.NET application by specifying command syntax at design time and, where possible, through the use of stored procedures.</span></span> <span data-ttu-id="bafed-110">Необходимо явно задавать команды перед вызовом `Update`.</span><span class="sxs-lookup"><span data-stu-id="bafed-110">You must explicitly set the commands before calling `Update`.</span></span> <span data-ttu-id="bafed-111">Если вызывается `Update`, и не существует подходящая команда для конкретного обновления (например, отсутствует `DeleteCommand` для удаленных строк), то активизируется исключение.</span><span class="sxs-lookup"><span data-stu-id="bafed-111">If `Update` is called and the appropriate command does not exist for a particular update (for example, no `DeleteCommand` for deleted rows), an exception is thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bafed-112">При использовании хранимых процедур SQL Server для изменения или удаления данных с помощью `DataAdapter` убедитесь, что в определении хранимой процедуры не указана инструкция SET NOCOUNT ON.</span><span class="sxs-lookup"><span data-stu-id="bafed-112">If you are using SQL Server stored procedures to edit or delete data using a `DataAdapter`, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="bafed-113">В таком случае возвращается число затронутых строк, равное нулю, что `DataAdapter` интерпретирует как конфликт параллелизма.</span><span class="sxs-lookup"><span data-stu-id="bafed-113">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="bafed-114">Это событие вызовет исключение <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="bafed-114">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
 <span data-ttu-id="bafed-115">Параметры команды могут использоваться в целях указания входных и выходных значений для инструкции SQL или хранимой процедуры применительно к каждой модифицированной строке в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-115">Command parameters can be used to specify input and output values for an SQL statement or stored procedure for each modified row in a `DataSet`.</span></span> <span data-ttu-id="bafed-116">Дополнительные сведения см. в разделе [параметры DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bafed-116">For more information, see [DataAdapter Parameters](../../../../docs/framework/data/adonet/dataadapter-parameters.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bafed-117">Важно учитывать различие между обозначением строки как удаленной в <xref:System.Data.DataTable> и удалением этой строки.</span><span class="sxs-lookup"><span data-stu-id="bafed-117">It is important to understand the difference between deleting a row in a <xref:System.Data.DataTable> and removing the row.</span></span> <span data-ttu-id="bafed-118">Если вызывается метод `Remove` или `RemoveAt`, строка немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="bafed-118">When you call the `Remove` or `RemoveAt` method, the row is removed immediately.</span></span> <span data-ttu-id="bafed-119">Любые соответствующие строки в серверном источнике данных остаются не затронутыми, если после этого будет передано значение `DataTable` или `DataSet` в `DataAdapter` и вызван метод `Update`.</span><span class="sxs-lookup"><span data-stu-id="bafed-119">Any corresponding rows in the back end data source will not be affected if you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`.</span></span> <span data-ttu-id="bafed-120">Если же используется метод `Delete`, то строка остается в `DataTable` и отмечается как предназначенная для удаления.</span><span class="sxs-lookup"><span data-stu-id="bafed-120">When you use the `Delete` method, the row remains in the `DataTable` and is marked for deletion.</span></span> <span data-ttu-id="bafed-121">Если после этого будет передано значение `DataTable` или `DataSet` в `DataAdapter` и вызван метод `Update`, то соответствующая строка в серверном источнике данных становится удаленной.</span><span class="sxs-lookup"><span data-stu-id="bafed-121">If you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`, the corresponding row in the back end data source is deleted.</span></span>  
  
 <span data-ttu-id="bafed-122">Если значение `DataTable` сопоставляется или создается на основе одной таблицы базы данных, то можно воспользоваться тем, что объект <xref:System.Data.Common.DbCommandBuilder> автоматически создает объекты `DeleteCommand`, `InsertCommand` и `UpdateCommand` для `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="bafed-122">If your `DataTable` maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` objects for the `DataAdapter`.</span></span> <span data-ttu-id="bafed-123">Дополнительные сведения см. в разделе [создание команд с помощью построителей CommandBuilder](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).</span><span class="sxs-lookup"><span data-stu-id="bafed-123">For more information, see [Generating Commands with CommandBuilders](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).</span></span>  
  
## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a><span data-ttu-id="bafed-124">Использование объекта UpdatedRowSource для сопоставления значений с набором данных</span><span class="sxs-lookup"><span data-stu-id="bafed-124">Using UpdatedRowSource to Map Values to a DataSet</span></span>  
 <span data-ttu-id="bafed-125">Можно управлять тем, как значения, возвращенные из источника данных, сопоставляются в обратном направлении с `DataTable` вслед за вызовом метода Update объекта `DataAdapter` с использованием свойства <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> объекта <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="bafed-125">You can control how the values returned from the data source are mapped back to the `DataTable` following a call to the Update method of a `DataAdapter`, by using the <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> property of a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="bafed-126">Задавая значение свойства `UpdatedRowSource` равным одному из значений перечисления <xref:System.Data.UpdateRowSource>, можно управлять тем, должны ли пропускаться выходные параметры, возвращаемые командами `DataAdapter`, или применяться к изменившейся строке в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-126">By setting the `UpdatedRowSource` property to one of the <xref:System.Data.UpdateRowSource> enumeration values, you can control whether output parameters returned by the `DataAdapter` commands are ignored or applied to the changed row in the `DataSet`.</span></span> <span data-ttu-id="bafed-127">Можно также указать, применяется ли первая возвращенная строка (если она существует) к изменившейся строке в `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="bafed-127">You can also specify whether the first returned row (if it exists) is applied to the changed row in the `DataTable`.</span></span>  
  
 <span data-ttu-id="bafed-128">В следующей таблице приведено описание различных значений перечисления `UpdateRowSource` и показано, как они влияют на поведение команды, используемой в сочетании с `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="bafed-128">The following table describes the different values of the `UpdateRowSource` enumeration and how they affect the behavior of a command used with a `DataAdapter`.</span></span>  
  
|<span data-ttu-id="bafed-129">Перечисление UpdatedRowSource</span><span class="sxs-lookup"><span data-stu-id="bafed-129">UpdatedRowSource Enumeration</span></span>|<span data-ttu-id="bafed-130">Описание</span><span class="sxs-lookup"><span data-stu-id="bafed-130">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:System.Data.UpdateRowSource.Both>|<span data-ttu-id="bafed-131">И выходные параметры, и первая строка возвращенного результирующего набора могут быть сопоставлены с модифицированной строкой в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-131">Both the output parameters and the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|  
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|<span data-ttu-id="bafed-132">Только данные из первой строки возвращенного результирующего набора могут быть сопоставлены с модифицированной строкой в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-132">Only the data in the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|  
|<xref:System.Data.UpdateRowSource.None>|<span data-ttu-id="bafed-133">Любые выходные параметры или строки возвращенного результирующего набора пропускаются.</span><span class="sxs-lookup"><span data-stu-id="bafed-133">Any output parameters or rows of a returned result set are ignored.</span></span>|  
|<xref:System.Data.UpdateRowSource.OutputParameters>|<span data-ttu-id="bafed-134">Только выходные параметры могут быть сопоставлены с модифицированной строкой в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-134">Only output parameters may be mapped to the changed row in the `DataSet`.</span></span>|  
  
 <span data-ttu-id="bafed-135">Метод `Update` позволяет решить задачу по передаче внесенных изменений обратно в источник данных; но может оказаться так, что другие клиенты уже внесли изменения в данные источника данных с того момента, как последний раз было осуществлено заполнение `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="bafed-135">The `Update` method resolves your changes back to the data source; however other clients may have modified data at the data source since the last time you filled the `DataSet`.</span></span> <span data-ttu-id="bafed-136">Чтобы обновить применяемый объект `DataSet` с использованием текущих данных, воспользуйтесь `DataAdapter` и методом `Fill`.</span><span class="sxs-lookup"><span data-stu-id="bafed-136">To refresh your `DataSet` with current data, use the `DataAdapter` and `Fill` method.</span></span> <span data-ttu-id="bafed-137">Произойдет добавление новых строк к таблице, а обновленная информация будет включена в существующие строки.</span><span class="sxs-lookup"><span data-stu-id="bafed-137">New rows will be added to the table, and updated information will be incorporated into existing rows.</span></span> <span data-ttu-id="bafed-138">Метод `Fill` определяет, должна ли быть добавлена новая строка или обновлена существующая строка, путем проверки значений первичного ключа в строках объекта `DataSet` и в строках, возвращенных `SelectCommand`.</span><span class="sxs-lookup"><span data-stu-id="bafed-138">The `Fill` method determines whether a new row will be added or an existing row will be updated by examining the primary key values of the rows in the `DataSet` and the rows returned by the `SelectCommand`.</span></span> <span data-ttu-id="bafed-139">Если в методе `Fill` обнаруживается значение первичного ключа какой-то строки в `DataSet`, которое совпадает со значением первичного ключа строки в результатах, возвращенных `SelectCommand`, то метод обновляет существующую строку на основании данных из строки, возвращенной `SelectCommand`, и задает значение <xref:System.Data.DataRow.RowState%2A> существующей строки, равное `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="bafed-139">If the `Fill` method encounters a primary key value for a row in the `DataSet` that matches a primary key value from a row in the results returned by the `SelectCommand`, it updates the existing row with the information from the row returned by the `SelectCommand` and sets the <xref:System.Data.DataRow.RowState%2A> of the existing row to `Unchanged`.</span></span> <span data-ttu-id="bafed-140">Если строка, возвращенная `SelectCommand`, имеет значение первичного ключа, не совпадающее ни с одним из значений первичного ключа в строках в `DataSet`, то метод `Fill` добавляет новую строку со значением `RowState`, равным `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="bafed-140">If a row returned by the `SelectCommand` has a primary key value that does not match any of the primary key values of the rows in the `DataSet`, the `Fill` method adds a new row with a `RowState` of `Unchanged`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bafed-141">Если метод `SelectCommand` возвращает результаты инструкции OUTER JOIN, то `DataAdapter` не задает значение `PrimaryKey` для результирующего набора `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="bafed-141">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` will not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="bafed-142">Необходимо непосредственно определить значение `PrimaryKey` для обеспечения того, чтобы решение по обработке повторяющихся строк было принято правильно.</span><span class="sxs-lookup"><span data-stu-id="bafed-142">You must define the `PrimaryKey` yourself to ensure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="bafed-143">Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="bafed-143">For more information, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="bafed-144">Для обработки исключений, которые могут возникнуть при вызове `Update` метод, можно использовать `RowUpdated` события, происходящие реагировать на ошибки обновления строки (см. в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)), или можно задать `DataAdapter.ContinueUpdateOnError` для `true` перед вызовом `Update`и реагировать на них сведения об ошибке, хранящихся в `RowError` свойства конкретной строки после завершения обновления (см. в разделе [сведения об ошибках строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)).</span><span class="sxs-lookup"><span data-stu-id="bafed-144">To handle exceptions that may occur when calling the `Update` method, you can use the `RowUpdated` event to respond to row update errors as they occur (see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)), or you can set `DataAdapter.ContinueUpdateOnError` to `true` before calling `Update`, and respond to the error information stored in the `RowError` property of a particular row when the update is complete (see [Row Error Information](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)).</span></span>  
  
 <span data-ttu-id="bafed-145">**Примечание** вызова `AcceptChanges` на `DataSet`, `DataTable`, или `DataRow` все `Original` значений в параметре `DataRow` перезапись `Current` значений в параметре `DataRow`.</span><span class="sxs-lookup"><span data-stu-id="bafed-145">**Note** Calling `AcceptChanges` on the `DataSet`, `DataTable`, or `DataRow` will cause all `Original` values for a `DataRow` to be overwritten with the `Current` values for the `DataRow`.</span></span> <span data-ttu-id="bafed-146">Если были изменены значения полей, уникальным образом идентифицирующих строку, то после вызова метода `AcceptChanges` значения `Original` больше не будут соответствовать этим значениям в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-146">If the field values that identify the row as unique have been modified, after calling `AcceptChanges` the `Original` values will no longer match the values in the data source.</span></span> <span data-ttu-id="bafed-147">Метод `AcceptChanges` вызывается автоматически для каждой строки во время вызова метода Update объекта `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="bafed-147">`AcceptChanges` is called automatically for each row during a call to the Update method of a `DataAdapter`.</span></span> <span data-ttu-id="bafed-148">Можно сохранить первоначальные значения во время вызова метода Update, для чего вначале следует задать значение свойства `AcceptChangesDuringUpdate` объекта `DataAdapter` равным false, или создать обработчик событий для события `RowUpdated` и задать значение <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A>, равное <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span><span class="sxs-lookup"><span data-stu-id="bafed-148">You can preserve the original values during a call to the Update method by first setting the `AcceptChangesDuringUpdate` property of the `DataAdapter` to false, or by creating an event handler for the `RowUpdated` event and setting the <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> to <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span></span> <span data-ttu-id="bafed-149">Дополнительные сведения см. в разделе [слияние содержимого набора данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md) и [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="bafed-149">For more information, see [Merging DataSet Contents](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md) and [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bafed-150">Пример</span><span class="sxs-lookup"><span data-stu-id="bafed-150">Example</span></span>  
 <span data-ttu-id="bafed-151">Следующие примеры демонстрируют, как для выполнения обновлений к модифицированным строкам путем явного задания `UpdateCommand` из `DataAdapter` и вызов его `Update` метод.</span><span class="sxs-lookup"><span data-stu-id="bafed-151">The following examples demonstrate how to perform updates to modified rows by explicitly setting the `UpdateCommand` of a `DataAdapter` and calling its `Update` method.</span></span> <span data-ttu-id="bafed-152">Обратите внимание на то, что задан параметр, указанный в предложении WHERE инструкции UPDATE, чтобы использовалось значение `Original` объекта `SourceColumn`.</span><span class="sxs-lookup"><span data-stu-id="bafed-152">Notice that the parameter specified in the WHERE clause of the UPDATE statement is set to use the `Original` value of the `SourceColumn`.</span></span> <span data-ttu-id="bafed-153">Это важно, поскольку значение `Current` могло быть изменено, поэтому может не соответствовать этому значению в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-153">This is important, because the `Current` value may have been modified and may not match the value in the data source.</span></span> <span data-ttu-id="bafed-154">Значение `Original` представляет собой значение, которое использовалось для заполнения `DataTable` из источника данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-154">The `Original` value is the value that was used to populate the `DataTable` from the data source.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]  
  
## <a name="autoincrement-columns"></a><span data-ttu-id="bafed-155">Столбцы AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="bafed-155">AutoIncrement Columns</span></span>  
 <span data-ttu-id="bafed-156">Если в таблицах из применяемого источника данных имеются столбцы с автоматическим увеличением значений, то можно обеспечить заполнение столбцов в применяемом `DataSet` путем возврата автоматически увеличивающегося значения как выходного параметра хранимой процедуры и сопоставления его со столбцом таблицы; возврата автоматически увеличивающегося значения в первой строке результирующего набора, возвращенного хранимой процедурой или инструкцией SQL; а также использование события `RowUpdated` объекта `DataAdapter` для выполнения дополнительной инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="bafed-156">If the tables from your data source have auto-incrementing columns, you can fill the columns in your `DataSet` either by returning the auto-increment value as an output parameter of a stored procedure and mapping that to a column in a table, by returning the auto-increment value in the first row of a result set returned by a stored procedure or SQL statement, or by using the `RowUpdated` event of the `DataAdapter` to execute an additional SELECT statement.</span></span> <span data-ttu-id="bafed-157">Дополнительные сведения и пример см. в разделе [извлечение идентификации или значений автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).</span><span class="sxs-lookup"><span data-stu-id="bafed-157">For more information and an example, see [Retrieving Identity or Autonumber Values](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).</span></span>  
  
## <a name="ordering-of-inserts-updates-and-deletes"></a><span data-ttu-id="bafed-158">Упорядочение вставок, обновлений и удалений</span><span class="sxs-lookup"><span data-stu-id="bafed-158">Ordering of Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="bafed-159">Во многих обстоятельствах имеет значение последовательность передачи изменений, внесенных с помощью `DataSet`, в источник данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-159">In many circumstances, the order in which changes made through the `DataSet` are sent to the data source is important.</span></span> <span data-ttu-id="bafed-160">Например, если происходит обновление значения первичного ключа для существующей строки и добавляется новая строка с новым значением первичного ключа в качестве внешнего ключа, то важно вначале осуществить обновление, а затем вставку.</span><span class="sxs-lookup"><span data-stu-id="bafed-160">For example, if a primary key value for an existing row is updated, and a new row has been added with the new primary key value as a foreign key, it is important to process the update before the insert.</span></span>  
  
 <span data-ttu-id="bafed-161">Можно использовать метод `Select` объекта `DataTable` для возврата массива `DataRow`, который ссылается только на строки с конкретным значением `RowState`.</span><span class="sxs-lookup"><span data-stu-id="bafed-161">You can use the `Select` method of the `DataTable` to return a `DataRow` array that only references rows with a particular `RowState`.</span></span> <span data-ttu-id="bafed-162">После этого можно передать возвращенный массив `DataRow` в метод `Update` объекта `DataAdapter` для обработки измененных строк.</span><span class="sxs-lookup"><span data-stu-id="bafed-162">You can then pass the returned `DataRow` array to the `Update` method of the `DataAdapter` to process the modified rows.</span></span> <span data-ttu-id="bafed-163">Задавая подмножество строк, подлежащих обновлению, можно управлять тем, в какой последовательности обрабатываются вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="bafed-163">By specifying a subset of rows to be updated, you can control the order in which inserts, updates, and deletes are processed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bafed-164">Пример</span><span class="sxs-lookup"><span data-stu-id="bafed-164">Example</span></span>  
 <span data-ttu-id="bafed-165">Например, в следующем коде обеспечивается то, что удаленные строки таблицы обрабатываются в первую очередь, затем происходит обработка обновленных строк, после чего обрабатываются вставленные строки.</span><span class="sxs-lookup"><span data-stu-id="bafed-165">For example, the following code ensures that the deleted rows of the table are processed first, then the updated rows, and then the inserted rows.</span></span>  
  
```vb  
Dim table As DataTable = dataSet.Tables("Customers")  
  
' First process deletes.  
dataSet.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Deleted))  
  
' Next process updates.  
adapter.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.ModifiedCurrent))  
  
' Finally, process inserts.  
dataAdapater.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Added))  
```  
  
```csharp  
DataTable table = dataSet.Tables["Customers"];  
  
// First process deletes.  
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));  
  
// Next process updates.  
adapter.Update(table.Select(null, null,   
  DataViewRowState.ModifiedCurrent));  
  
// Finally, process inserts.  
adapter.Update(table.Select(null, null, DataViewRowState.Added));  
```  
  
## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a><span data-ttu-id="bafed-166">Используйте DataAdapter для извлечения и обновления данных</span><span class="sxs-lookup"><span data-stu-id="bafed-166">Use a DataAdapter to Retrieve and Update Data</span></span>  
 <span data-ttu-id="bafed-167">DataAdapter можно использовать для извлечения и обновления данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-167">You can use a DataAdapter to retrieve and update the data.</span></span>  
  
- <span data-ttu-id="bafed-168">В этом примере DataAdapter.AcceptChangesDuringFill используется для клонирования данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-168">The sample uses DataAdapter.AcceptChangesDuringFill to clone the data in the database.</span></span> <span data-ttu-id="bafed-169">Если свойство имеет значение false, AcceptChanges при заполнении таблицы не вызывается и позднее добавленные строки рассматриваются как вставленные строки.</span><span class="sxs-lookup"><span data-stu-id="bafed-169">If the property is set as false, AcceptChanges is not called when filling the table, and the newly added rows are treated as inserted rows.</span></span> <span data-ttu-id="bafed-170">Таким образом, в примере эти строки используются для вставки новых строк в базу данных.</span><span class="sxs-lookup"><span data-stu-id="bafed-170">So, the sample uses these rows to insert the new rows into the database.</span></span>  
  
- <span data-ttu-id="bafed-171">В этом примере DataAdapter.TableMappings используется для определения сопоставления между исходной таблицей и DataTable.</span><span class="sxs-lookup"><span data-stu-id="bafed-171">The samples uses DataAdapter.TableMappings to define the mapping between the source table and DataTable.</span></span>  
  
- <span data-ttu-id="bafed-172">В этом примере DataAdapter.FillLoadOption используется для определения того, как адаптер заполняет DataTable из DbDataReader.</span><span class="sxs-lookup"><span data-stu-id="bafed-172">The sample uses DataAdapter.FillLoadOption to determine how the adapter fills the DataTable from the DbDataReader.</span></span> <span data-ttu-id="bafed-173">При создании объекта DataTable можно выполнять запись данных из базы данных только в текущую или исходную версию путем установки свойства в LoadOption.Upsert или LoadOption.PreserveChanges.</span><span class="sxs-lookup"><span data-stu-id="bafed-173">When you create a DataTable, you can only write the data from database to the current version or the original version by setting the property as the LoadOption.Upsert or the LoadOption.PreserveChanges.</span></span>  
  
- <span data-ttu-id="bafed-174">В примере также обновляется таблица путем использования DbDataAdapter.UpdateBatchSize для выполнения пакетных операций.</span><span class="sxs-lookup"><span data-stu-id="bafed-174">The sample will also update the table by using DbDataAdapter.UpdateBatchSize to perform batch operations.</span></span>  
  
 <span data-ttu-id="bafed-175">Перед компиляцией и выполнением примера необходимо создать образец базы данных:</span><span class="sxs-lookup"><span data-stu-id="bafed-175">Before you compile and run the sample, you need to create the sample database:</span></span>  
  
```sql
USE [master]  
GO  
  
CREATE DATABASE [MySchool]   
  
GO  
  
USE [MySchool]  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,  
[Year] [smallint] NOT NULL,  
[Title] [nvarchar](100) NOT NULL,  
[Credits] [int] NOT NULL,  
[DepartmentID] [int] NOT NULL,  
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED  
(  
[CourseID] ASC,  
[Year] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,  
[Name] [nvarchar](50) NOT NULL,  
[Budget] [money] NOT NULL,  
[StartDate] [datetime] NOT NULL,  
[Administrator] [int] NULL,  
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED  
(  
[DepartmentID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)  
  
SET IDENTITY_INSERT [dbo].[Department] ON   
  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)  
SET IDENTITY_INSERT [dbo].[Department] OFF  
  
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])  
REFERENCES [dbo].[Department] ([DepartmentID])  
GO  
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]  
GO  
```  
  
 <span data-ttu-id="bafed-176">Проекты C# и Visual Basic с этим образцом кода можно найти на [примеры кода от разработчиков](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span><span class="sxs-lookup"><span data-stu-id="bafed-176">C# and Visual Basic projects with this code sample can be found on [Developer Code Samples](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span></span>  
  
```csharp
using System;  
using System.Data;  
using System.Data.Common;  
using System.Data.SqlClient;  
using System.Linq;  
using CSDataAdapterOperations.Properties;  
  
namespace CSDataAdapterOperations.Properties {  
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {  
  
      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));  
  
      public static Settings Default {  
         get {  
            return defaultInstance;  
         }  
      }  
  
      [global::System.Configuration.ApplicationScopedSettingAttribute()]  
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]  
      public string MySchoolConnectionString {  
         get {  
            return ((string)(this["MySchoolConnectionString"]));  
         }  
      }  
   }  
}  
  
class Program {  
   static void Main(string[] args) {  
      Settings settings = new Settings();  
  
      // Copy the data from the database.  Get the table Department and Course from the database.  
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]  
                                     FROM [MySchool].[dbo].[Department];  
  
                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],  
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]  
                                   FROM [MySchool].[dbo].[Course]  
                                   Group by [CourseID]";  
  
      DataSet mySchool = new DataSet();  
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);  
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);  
  
      // Use DataTableMapping to map the source tables and the destination tables.  
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};  
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);  
  
      Console.WriteLine("The following tables are from the database.");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      // Roll back the changes  
      DataTable department = mySchool.Tables["Department"];  
      DataTable course = mySchool.Tables["Course"];  
  
      department.Rows[0]["Name"] = "New" + department.Rows[0][1];  
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];  
      course.Rows[0]["Credits"] = 10;  
  
      Console.WriteLine("After we changed the tables:");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      department.RejectChanges();  
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");  
      ShowDataTable(department);  
  
      DataColumn[] primaryColumns = { course.Columns["CourseID"] };  
      DataColumn[] resetColumns = { course.Columns["Title"] };  
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);  
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");  
      ShowDataTable(course);  
  
      // Batch update the table.  
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],   
                                   [Credits],[DepartmentID])   
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";  
      SqlCommand insertCommand = new SqlCommand(insertString);  
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");  
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");  
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");  
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");  
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");  
  
      const Int32 batchSize = 10;  
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);  
   }  
  
   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);  
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a   
            // DataRow after it is added to the DataTable during any of the Fill operations.  
            adapter.AcceptChangesDuringFill = false;  
  
            adapter.Fill(dataSet);  
         }  
      }  
   }  
  
   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.  
   private static void ResetCourse(DataTable table, String connectionString,  
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {  
      table.PrimaryKey = primaryColumns;  
  
      // Build the query string  
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));  
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));
  
      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
  
      ResetDataTable(table, connectionString, selectCommand);  
   }  
  
   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges   
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges  
   // The ResetDataTable method rolls back one or more columns of data.  
   private static void ResetDataTable(DataTable table, String connectionString,  
       SqlCommand selectCommand) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {  
            // The incoming values for this row will be written to the current version of each   
            // column. The original version of each column's data will not be changed.  
            adapter.FillLoadOption = LoadOption.Upsert;  
  
            adapter.Fill(table);  
         }  
      }  
   }  
  
   private static void BatchInsertUpdate(DataTable table, String connectionString,  
       SqlCommand insertCommand, Int32 batchSize) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         insertCommand.Connection = connection;  
         // When setting UpdateBatchSize to a value other than 1, all the commands   
         // associated with the SqlDataAdapter have to have their UpdatedRowSource   
         // property set to None or OutputParameters. An exception is thrown otherwise.  
         insertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter()) {  
            adapter.InsertCommand = insertCommand;  
            // Gets or sets the number of rows that are processed in each round-trip to the server.  
            // Setting it to 1 disables batch updates, as rows are sent one at a time.  
            adapter.UpdateBatchSize = batchSize;  
  
            adapter.Update(table);  
  
            Console.WriteLine("Successfully to update the table.");  
         }  
      }  
   }  
  
   private static void ShowDataTable(DataTable table) {  
      foreach (DataColumn col in table.Columns) {  
         Console.Write("{0,-14}", col.ColumnName);  
      }  
      Console.WriteLine("{0,-14}", "RowState");  
  
      foreach (DataRow row in table.Rows) {  
         foreach (DataColumn col in table.Columns) {  
            if (col.DataType.Equals(typeof(DateTime)))  
               Console.Write("{0,-14:d}", row[col]);  
            else if (col.DataType.Equals(typeof(Decimal)))  
               Console.Write("{0,-14:C}", row[col]);  
            else  
               Console.Write("{0,-14}", row[col]);  
         }  
         Console.WriteLine("{0,-14}", row.RowState);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bafed-177">См. также</span><span class="sxs-lookup"><span data-stu-id="bafed-177">See also</span></span>

- [<span data-ttu-id="bafed-178">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="bafed-178">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="bafed-179">Состояния и версии строк</span><span class="sxs-lookup"><span data-stu-id="bafed-179">Row States and Row Versions</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="bafed-180">AcceptChanges и RejectChanges</span><span class="sxs-lookup"><span data-stu-id="bafed-180">AcceptChanges and RejectChanges</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [<span data-ttu-id="bafed-181">Слияние содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="bafed-181">Merging DataSet Contents</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)
- [<span data-ttu-id="bafed-182">Извлечение идентификации или значений автонумерации</span><span class="sxs-lookup"><span data-stu-id="bafed-182">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)
- [<span data-ttu-id="bafed-183">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bafed-183">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
