---
title: Метод Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 04defffc724875e691fd7b87331c28e6b6c0cd28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="the-load-method"></a><span data-ttu-id="a1f21-102">Метод Load</span><span class="sxs-lookup"><span data-stu-id="a1f21-102">The Load Method</span></span>
<span data-ttu-id="a1f21-103">Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1f21-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="a1f21-104">Это перегруженный метод, который в самом простом принимает один параметр **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="a1f21-105">В этой форме он просто загружает **DataTable** со строками.</span><span class="sxs-lookup"><span data-stu-id="a1f21-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="a1f21-106">Кроме того, можно указать **LoadOption** параметра для управления как данные добавляются **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="a1f21-107">**LoadOption** особенно удобен в случаях, где **DataTable** уже содержит строки данных, так как он описывает, как входящие данные из источника данных будут объединяться с данными уже находится в таблице.</span><span class="sxs-lookup"><span data-stu-id="a1f21-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="a1f21-108">Например **PreserveCurrentValues** (по умолчанию) указывает, что в случаях, когда строка помечается как **Added** в **DataTable**, **исходный** значение или каждый столбец имеет значение содержимое соответствующей строки из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1f21-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="a1f21-109">**Текущей** значение будет сохранять значений, присвоенных при добавлении строки и **RowState** строки будет присвоено **Changed**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="a1f21-110">В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="a1f21-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="a1f21-111">Значение LoadOption</span><span class="sxs-lookup"><span data-stu-id="a1f21-111">LoadOption value</span></span>|<span data-ttu-id="a1f21-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a1f21-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="a1f21-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="a1f21-113">**OverwriteRow**</span></span>|<span data-ttu-id="a1f21-114">Если входящие строки имеют такое же **PrimaryKey** значение в виде строк, уже находящихся в **DataTable**, **исходного** и **текущей** значения каждого столбец заменяются значениями из входящей строки и **RowState** свойству **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a1f21-115">Строки из источника данных, еще не существуют в **DataTable** добавлены с классом **RowState** значение **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a1f21-116">Этот параметр действует обновление содержимого **DataTable** , чтобы он соответствовал содержимое источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1f21-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="a1f21-117">**PreserveCurrentValues (по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="a1f21-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="a1f21-118">Если входящие строки имеют такое же **PrimaryKey** значение в виде строк, уже находящихся в **DataTable**, **исходного** присваивается содержимое входящей строки и **Текущей** значение не изменяется.</span><span class="sxs-lookup"><span data-stu-id="a1f21-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="a1f21-119">Если **RowState** — **Added** или **Modified**, ему присваивается **Modified**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="a1f21-120">Если **RowState** было **Deleted**, он остается **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="a1f21-121">Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** равно **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="a1f21-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="a1f21-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="a1f21-123">Если входящие строки имеют такое же **PrimaryKey** значение в виде строк, уже находящихся в **DataTable**, **текущей** копировать значение **исходный**значение и **текущей** затем присваивается содержимое входящей строки.</span><span class="sxs-lookup"><span data-stu-id="a1f21-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="a1f21-124">Если **RowState** в **DataTable** было **Added**, **RowState** остается **Added**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="a1f21-125">Для строк, отмеченных как **Modified** или **Deleted**, **RowState** — **Modified**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="a1f21-126">Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** равно **Added**.</span><span class="sxs-lookup"><span data-stu-id="a1f21-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="a1f21-127">В следующем примере используется **нагрузки** метод для отображения списка дней рождения сотрудников **Northwind** базы данных.</span><span class="sxs-lookup"><span data-stu-id="a1f21-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1f21-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a1f21-128">See Also</span></span>  
 [<span data-ttu-id="a1f21-129">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="a1f21-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="a1f21-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1f21-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
