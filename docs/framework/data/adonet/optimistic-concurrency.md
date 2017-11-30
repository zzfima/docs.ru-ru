---
title: "Оптимистическая блокировка"
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
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 45939dcec8b8db8e1b06ebfc67d89bfead67575a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optimistic-concurrency"></a>Оптимистическая блокировка
В многопользовательской среде предусмотрены две модели обновления данных в базе данных: оптимистичный параллелизм и пессимистичный параллелизм. Объект <xref:System.Data.DataSet> предназначен для стимулирования использования оптимистичного параллелизма для длительный действий, таких как удаленный доступ к данным и взаимодействие с данными.  
  
 Пессимистичный параллелизм предусматривает блокировку строк в источнике данных, что позволяет запретить другим пользователям модификацию данных, которая может отрицательно повлиять на работу текущего пользователя. В пессимистической модели, когда пользователь выполняет действие, вызывающее применение блокировки, другие пользователи не могут выполнять действия, которые могли бы конфликтовать с этой блокировкой, до тех пор как владелец блокировки ее не снимет. Эта модель в основном используется в таких средах, где наблюдается интенсивная конкуренция по доступу к данным, поэтому расходы на защиту данных с помощью блокировок оказываются меньше по сравнению с расходами на откаты транзакций, обусловленные возникновением конфликтов параллельного доступа.  
  
 Поэтому в модели с пессимистичным параллелизмом пользователь, обновляющий строку, устанавливает блокировку. До тех пор пока пользователь не закончит обновление и не снимет блокировку, больше никто другой не сможет вносить изменения в эту строку. Это означает, что пессимистичный параллелизм является наиболее подходящим в тех ситуациях, когда блокировки устанавливаются на короткое время, например как при программной обработке записей. Применение пессимистичного параллелизма становится препятствием для масштабирования приложения, когда пользователи взаимодействуют с данными и вызывают блокировку записей на относительно большие промежутки времени.  
  
> [!NOTE]
>  Если в приложении требуется обновлять несколько строк в одной операции, то создание транзакций обеспечивает лучшее масштабирование по сравнению с использованием пессимистичных блокировок.  
  
 В отличие от этого, пользователи, применяющие оптимистичный параллелизм, не блокируют строку при ее чтении. Когда пользователю требуется обновить строку, приложение должно определить, не изменялась ли эта строка другим пользователем после того, как она была открыта для чтения. Оптимистичный параллелизм обычно используется в средах, характеризующихся низкой конкуренцией за данные. Применение оптимистичного параллелизма способствует повышению производительности благодаря тому, что не требуется блокировка записей, которая требует дополнительных ресурсов сервера. Кроме того, для блокировки записей требуется постоянное соединение с сервером базы данных. При использовании модели оптимистичного параллелизма такая необходимость отсутствует, поэтому соединения с сервером можно применять для обслуживания большего количества клиентов за меньшее время.  
  
 В модели оптимистичного параллелизма конфликтом параллельного доступа считается ситуация, когда вслед за получением пользователем значения из базы данных другой пользователь изменяет это значение до того, как первый пользователь попытается его изменить. Разрешение конфликта параллельного доступа лучше всего показать, рассмотрев следующий пример.  
  
 В следующих таблицах рассматривается пример оптимистичного параллелизма.  
  
 В 13:00 Пользователь1 считывает из базы данных строку со следующими значениями:  
  
 **CustID LastName FirstName**  
  
 101          Smith             Bob  
  
|Имя столбца|Исходное значение|Текущее значение|Значение в базе данных|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Bob|Bob|  
  
 В 13:01 Пользователь2 считывает ту же строку.  
  
 В 13:03 Пользователь2 изменяет **FirstName** с «Bob» на «Robert» и обновляет базу данных.  
  
|Имя столбца|Исходное значение|Текущее значение|Значение в базе данных|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Robert|Bob|  
  
 Эта операция обновления завершается успешно, поскольку значения в базе данных ко времени обновления соответствуют первоначальным значениям, которые имеются в распоряжении Пользователя2.  
  
 В 13:05 Пользователь1 изменяет значение FirstName с «Bob» на «James» и пытается обновить строку.  
  
|Имя столбца|Исходное значение|Текущее значение|Значение в базе данных|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|James|Robert|  
  
 В этот момент Пользователь1 обнаруживает нарушение оптимистичного параллелизма, поскольку значение в базе данных («Robert») больше не соответствует первоначальному значению, которое ожидал найти Пользователь1 («Bob»). Это нарушение параллелизма просто позволяет узнать о том, что обновление окончилось неудачей. После этого нужно принять решение, следует ли перезаписать изменения, внесенные Пользователем2, изменениями, которые внес Пользователь1, или отменить изменения Пользователя1.  
  
## <a name="testing-for-optimistic-concurrency-violations"></a>Проверка на наличие нарушений оптимистичного параллелизма  
 Существует несколько методов проверки на наличие нарушений оптимистичного параллелизма. Один из этих методов предусматривает включение столбца отметки времени в таблицу. Базы данных обычно предоставляют возможность использования отметок времени, которые могут служить для определения даты и времени последнего обновления записи. При использовании этого метода в определение таблицы включается столбец отметки времени. После каждого обновления записи обновляется также отметка времени, отражая текущую дату и время. При проверке на наличие нарушений оптимистичного параллелизма при любом запросе к содержимому таблицы происходит возврат значений столбца отметки времени. При попытке обновления это значение отметки времени из базы данных сравнивается с первоначальным значением отметки времени, содержащимся в измененной строке. Если эти значения совпадают, операция обновления выполняется и столбец отметки времени обновляется с указанием текущего времени, чтобы отразить факт обновления. Если эти значения не совпадают, то возникает конфликт оптимистичного параллелизма.  
  
 Еще один метод проверки на наличие нарушения оптимистичного параллелизма состоит в проверке того, что все первоначальные значения полей в строке все еще соответствуют находящимся в базе данных. Например, рассмотрим следующий запрос:  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 Для проверки на наличие нарушения оптимистичного параллелизма при обновлении строки в **Table1**, можно выполнить следующую инструкцию UPDATE:  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 При условии, что первоначальные значения равны значениям в базе данных, обновление выполняется. Если же какое-то значение было изменено, то при обновлении изменение строки не происходит, поскольку в предложении WHERE не обнаруживается совпадение.  
  
 Обратите внимание, что всегда рекомендуется возвращать уникальное значение первичного ключа в каждом конкретном запросе. В противном случае в предыдущей инструкции UPDATE может произойти обновление нескольких строк, что может не соответствовать намерениям.  
  
 Если столбец в источнике данных допускает значения NULL, то может потребоваться дополнить предложение WHERE для проверки на наличие согласующихся ссылок NULL в локальной таблице и в источнике данных. Например, в следующей инструкции UPDATE проверяется, что ссылка NULL в локальной строке все еще соответствует ссылке NULL в источнике данных или что значение в локальной строке все еще соответствует значению в источнике данных.  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 При использовании модели оптимистичного параллелизма можно также выбрать менее строгие критерии. Например, если в предложении WHERE используются только столбцы первичного ключа, то перезапись данных происходит независимо от того, произошло ли обновление других столбцов со времени выполнения последнего запроса. Предложение WHERE также можно применять только к конкретным столбцам, в результате чего перезапись данных будет выполняться, только если со времени последнего запроса к определенным полям они не обновлялись.  
  
### <a name="the-dataadapterrowupdated-event"></a>Событие DataAdapter.RowUpdated  
 **RowUpdated** событие <xref:System.Data.Common.DataAdapter> объект может использоваться в сочетании с методами, описанными выше, для предоставления уведомления в приложение оптимистичного параллелизма. **RowUpdated** происходит после каждой попытки обновить **Modified** строка из **набора данных**. Это позволяет включать в приложение специальный код обработки, в том числе обеспечивающий обработку при возникновении исключений, добавление пользовательских сведений об ошибке, введение программных средств повторного выполнения и т. д. <xref:System.Data.Common.RowUpdatedEventArgs> Возвращает **RecordsAffected** свойство, содержащее количество строк, затронутых конкретной командой обновления для измененной строки в таблице. Установив команды update для проверки на оптимистичный параллелизм **RecordsAffected** свойство в результате возвратит значение 0, если произошло нарушение оптимистичного параллелизма, так как нет записи были обновлены. В таком случае вызывается исключение. **RowUpdated** событий позволяет обрабатывать такую ситуацию и избегать исключения путем задания соответствующего **RowUpdatedEventArgs.Status** значений, таких как  **UpdateStatus.SkipCurrentRow**. Дополнительные сведения о **RowUpdated** событий, в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
 При необходимости можно задать **DataAdapter.ContinueUpdateOnError** для **true**, перед вызовом метода **обновление**и реагировать на ошибки сведениями, хранящимися в **RowError** конкретной строки, если **обновление** завершения. Дополнительные сведения см. в разделе [сведения об ошибках строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md).  
  
## <a name="optimistic-concurrency-example"></a>Пример оптимистического управления параллелизмом  
 Ниже приведен простой пример, который задает **UpdateCommand** из **DataAdapter** для проверки на оптимистичный параллелизм, а затем использует **RowUpdated** событий для проверки нарушений оптимистичного параллелизма. При обнаружении нарушение оптимистичного параллелизма, приложение задает **RowError** строки, чтобы отразить нарушение оптимистичного параллелизма обновления была выполнена в отношении.  
  
 Обратите внимание, что значения параметров, передаваемые в предложение WHERE команды UPDATE сопоставляются с **исходного** значения соответствующих столбцов.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = dataSet.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName, connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Обновление источников данных с объектами DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Сведения об ошибках строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 [Транзакции и параллелизм](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
