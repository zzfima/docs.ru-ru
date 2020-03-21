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
# <a name="the-load-method"></a><span data-ttu-id="cf3af-102">Метод Load</span><span class="sxs-lookup"><span data-stu-id="cf3af-102">The Load Method</span></span>
<span data-ttu-id="cf3af-103">Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="cf3af-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="cf3af-104">Это перегруженный метод, который в своей простейшой форме принимает один параметр, **DataReader.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="cf3af-105">В этой форме он просто загружает **DataTable** строками.</span><span class="sxs-lookup"><span data-stu-id="cf3af-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="cf3af-106">Дополнительно можно указать параметр **LoadOption** для контроля за тем, как данные добавляются в **DataTable.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="cf3af-107">Параметр **LoadOption** особенно полезен в тех случаях, когда **DataTable** уже содержит строки данных, поскольку он описывает, как поступающие данные из источника данных будут сочетаться с данными, уже находящимися в таблице.</span><span class="sxs-lookup"><span data-stu-id="cf3af-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="cf3af-108">Например, **PreserveCurrentValues** (по умолчанию) указывает, что в случаях, когда строка помечена как **Добавленная** в **DataTable,** **исходное** значение или каждый столбец устанавливается на содержимое соответствующей строки из источника данных.</span><span class="sxs-lookup"><span data-stu-id="cf3af-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="cf3af-109">**Текущее** значение сохранит значения, присвоенные при добавлении строки, а **строка Строка** будет настроена на **изменение.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="cf3af-110">В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="cf3af-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="cf3af-111">Значение LoadOption</span><span class="sxs-lookup"><span data-stu-id="cf3af-111">LoadOption value</span></span>|<span data-ttu-id="cf3af-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cf3af-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="cf3af-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="cf3af-113">**OverwriteRow**</span></span>|<span data-ttu-id="cf3af-114">Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **исходные** и **текущие** значения каждого столбца заменяются значениями в входящих строках, а свойство **RowState** настроено на **unchanged.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="cf3af-115">Строки из источника данных, которые еще не существуют в **DataTable,** добавляются со значением **RowState** **Unchanged.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="cf3af-116">Этот параметр фактически обновляет содержимое **DataTable,** чтобы он соответствовал содержимому источника данных.</span><span class="sxs-lookup"><span data-stu-id="cf3af-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="cf3af-117">**PreserveCurrentValues (значение по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="cf3af-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="cf3af-118">Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **исходное** значение устанавливается на содержимое входящего ряда, и **текущее** значение не изменяется.</span><span class="sxs-lookup"><span data-stu-id="cf3af-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="cf3af-119">Если **RowState** **добавлен** или **изменен,** он настроен на **изменение**.</span><span class="sxs-lookup"><span data-stu-id="cf3af-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="cf3af-120">Если **RowState** был **удален,** он остается **удаленным**.</span><span class="sxs-lookup"><span data-stu-id="cf3af-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="cf3af-121">Строки из источника данных, которые еще не существуют в **DataTable,** добавляются, и **RowState** настроен **на неизменный.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="cf3af-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="cf3af-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="cf3af-123">Если входящие строки имеют то же значение **PrimaryKey,** что и строка, уже в **DataTable,** **текущее** значение скопировано в **исходное** значение, а **текущее** значение затем устанавливается на содержимое входящего строки.</span><span class="sxs-lookup"><span data-stu-id="cf3af-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="cf3af-124">Если **состояние строки** в **DataTable** было **добавлено,** **rowState** остается **добавленным**.</span><span class="sxs-lookup"><span data-stu-id="cf3af-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="cf3af-125">Для строк, помеченных как **измененные** или **удаленные,** **состояние RowState** **модифицируется.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="cf3af-126">Строки из источника данных, которые еще не существуют в **DataTable,** добавляются, и **RowState** настроен на **добавление.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="cf3af-127">В следующем примере используется метод **Нагрузки** для отображения списка дней рождения сотрудников в базе данных **Northwind.**</span><span class="sxs-lookup"><span data-stu-id="cf3af-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf3af-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf3af-128">See also</span></span>

- [<span data-ttu-id="cf3af-129">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="cf3af-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="cf3af-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf3af-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
