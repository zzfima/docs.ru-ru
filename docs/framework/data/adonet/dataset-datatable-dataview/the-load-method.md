---
title: Метод Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150731"
---
# <a name="the-load-method"></a>Метод Load
Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных. Это перегруженный метод, который в своей простейшой форме принимает один параметр, **DataReader.** В этой форме он просто загружает **DataTable** строками. Дополнительно можно указать параметр **LoadOption** для контроля за тем, как данные добавляются в **DataTable.**  
  
 Параметр **LoadOption** особенно полезен в тех случаях, когда **DataTable** уже содержит строки данных, поскольку он описывает, как поступающие данные из источника данных будут сочетаться с данными, уже находящимися в таблице. Например, **PreserveCurrentValues** (по умолчанию) указывает, что в случаях, когда строка помечена как **Добавленная** в **DataTable,** **исходное** значение или каждый столбец устанавливается на содержимое соответствующей строки из источника данных. **Текущее** значение сохранит значения, присвоенные при добавлении строки, а **строка Строка** будет настроена на **изменение.**  
  
 В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.  
  
|Значение LoadOption|Описание|  
|----------------------|-----------------|  
|**OverwriteRow**|Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **исходные** и **текущие** значения каждого столбца заменяются значениями в входящих строках, а свойство **RowState** настроено на **unchanged.**<br /><br /> Строки из источника данных, которые еще не существуют в **DataTable,** добавляются со значением **RowState** **Unchanged.**<br /><br /> Этот параметр фактически обновляет содержимое **DataTable,** чтобы он соответствовал содержимому источника данных.|  
|**PreserveCurrentValues (значение по умолчанию)**|Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **исходное** значение устанавливается на содержимое входящего ряда, и **текущее** значение не изменяется.<br /><br /> Если **RowState** **добавлен** или **изменен,** он настроен на **изменение**.<br /><br /> Если **RowState** был **удален,** он остается **удаленным**.<br /><br /> Строки из источника данных, которые еще не существуют в **DataTable,** добавляются, и **RowState** настроен **на неизменный.**|  
|**UpdateCurrentValues**|Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **текущее** значение скопировано в **исходное** значение, а **текущее** значение затем устанавливается на содержимое входящего строки.<br /><br /> Если **состояние строки** в **DataTable** было **добавлено,** **rowState** остается **добавленным**. Для строк, помеченных как **измененные** или **удаленные,** **состояние RowState** **модифицируется.**<br /><br /> Строки из источника данных, которые еще не существуют в **DataTable,** добавляются, и **RowState** настроен на **добавление.**|  
  
 В следующем примере используется метод **Нагрузки** для отображения списка дней рождения сотрудников в базе данных **Northwind.**  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a>См. также раздел

- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
