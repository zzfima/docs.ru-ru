---
title: Метод Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 21868f808a6d39c935b612f745d720180df2dd73
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507266"
---
# <a name="the-load-method"></a>Метод Load
Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных. Это перегруженный метод, который, в его простейшей форме принимает один параметр, **DataReader**. В этой форме он просто загружает **DataTable** со строками. При необходимости можно указать **LoadOption** параметра для управления, как данные добавляются к **DataTable**.  
  
 **LoadOption** особенно удобен в случаях, где **DataTable** уже содержатся строки данных, так как он описывает, как входящие данные из источника данных объединяются с данными уже находится в таблице. Например **PreserveCurrentValues** (по умолчанию) указывает, что в случаях, когда строка отмечена как **Added** в **DataTable**, **исходный** значение или каждого столбца присваивается содержимое соответствующей строки из источника данных. **Текущей** значение будет сохранять значений, присвоенных при добавлении строки и **RowState** строки будет присвоено **Changed**.  
  
 В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.  
  
|Значение LoadOption|Описание|  
|----------------------|-----------------|  
|**OverwriteRow**|Если входящие строки имеют одинаковые **PrimaryKey** значение как строка уже **DataTable**, **исходного** и **текущей** значения каждого столбец заменяются значениями из входящей строки и **RowState** свойству **Unchanged**.<br /><br /> Строки из источника данных, еще не существуют в **DataTable** , который добавляется **RowState** значение **Unchanged**.<br /><br /> Этот параметр действует обновляет содержимое **DataTable** , чтобы он соответствовал содержимого источника данных.|  
|**PreserveCurrentValues (значение по умолчанию)**|Если входящие строки имеют одинаковые **PrimaryKey** значение как строка уже **DataTable**, **исходного** присваивается содержимое входящей строки и **Текущей** значение не изменяется.<br /><br /> Если **RowState** — **Added** или **Modified**, ему будет присвоено **Modified**.<br /><br /> Если **RowState** был **Deleted**, он остается **Deleted**.<br /><br /> Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** присваивается **Unchanged**.|  
|**UpdateCurrentValues**|Если входящие строки имеют одинаковые **PrimaryKey** значение в виде строки, уже в **DataTable**, **текущей** копируется в значение **исходный**значение и **текущей** затем присваивается содержимое входящей строки.<br /><br /> Если **RowState** в **DataTable** был **Added**, **RowState** остается **Added**. Для строк, отмеченных как **Modified** или **Deleted**, **RowState** — **Modified**.<br /><br /> Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** присваивается **Added**.|  
  
 В следующем примере используется **нагрузки** метод для отображения списка дней рождения сотрудников **Northwind** базы данных.  
  
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
  
## <a name="see-also"></a>См. также  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
