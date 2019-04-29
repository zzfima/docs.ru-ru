---
title: Метод Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 82f840ab7dd26a4888ebf024d696f2c70701eb18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607236"
---
# <a name="the-load-method"></a><span data-ttu-id="9b4cc-102">Метод Load</span><span class="sxs-lookup"><span data-stu-id="9b4cc-102">The Load Method</span></span>
<span data-ttu-id="9b4cc-103">Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="9b4cc-104">Это перегруженный метод, который, в его простейшей форме принимает один параметр, **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="9b4cc-105">В этой форме он просто загружает **DataTable** со строками.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="9b4cc-106">При необходимости можно указать **LoadOption** параметра для управления, как данные добавляются к **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="9b4cc-107">**LoadOption** особенно удобен в случаях, где **DataTable** уже содержатся строки данных, так как он описывает, как входящие данные из источника данных объединяются с данными уже находится в таблице.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="9b4cc-108">Например **PreserveCurrentValues** (по умолчанию) указывает, что в случаях, когда строка отмечена как **Added** в **DataTable**, **исходный** значение или каждого столбца присваивается содержимое соответствующей строки из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="9b4cc-109">**Текущей** значение будет сохранять значений, присвоенных при добавлении строки и **RowState** строки будет присвоено **Changed**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="9b4cc-110">В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="9b4cc-111">Значение LoadOption</span><span class="sxs-lookup"><span data-stu-id="9b4cc-111">LoadOption value</span></span>|<span data-ttu-id="9b4cc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9b4cc-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="9b4cc-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="9b4cc-113">**OverwriteRow**</span></span>|<span data-ttu-id="9b4cc-114">Если входящие строки имеют одинаковые **PrimaryKey** значение как строка уже **DataTable**, **исходного** и **текущей** значения каждого столбец заменяются значениями из входящей строки и **RowState** свойству **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9b4cc-115">Строки из источника данных, еще не существуют в **DataTable** , который добавляется **RowState** значение **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9b4cc-116">Этот параметр действует обновляет содержимое **DataTable** , чтобы он соответствовал содержимого источника данных.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="9b4cc-117">**PreserveCurrentValues (значение по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="9b4cc-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="9b4cc-118">Если входящие строки имеют одинаковые **PrimaryKey** значение как строка уже **DataTable**, **исходного** присваивается содержимое входящей строки и **Текущей** значение не изменяется.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="9b4cc-119">Если **RowState** — **Added** или **Modified**, ему будет присвоено **Modified**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="9b4cc-120">Если **RowState** был **Deleted**, он остается **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="9b4cc-121">Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** присваивается **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="9b4cc-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="9b4cc-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="9b4cc-123">Если входящие строки имеют одинаковые **PrimaryKey** значение в виде строки, уже в **DataTable**, **текущей** копируется в значение **исходный**значение и **текущей** затем присваивается содержимое входящей строки.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="9b4cc-124">Если **RowState** в **DataTable** был **Added**, **RowState** остается **Added**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="9b4cc-125">Для строк, отмеченных как **Modified** или **Deleted**, **RowState** — **Modified**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="9b4cc-126">Строки из источника данных, еще не существуют в **DataTable** добавляются и **RowState** присваивается **Added**.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="9b4cc-127">В следующем примере используется **нагрузки** метод для отображения списка дней рождения сотрудников **Northwind** базы данных.</span><span class="sxs-lookup"><span data-stu-id="9b4cc-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b4cc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9b4cc-128">See also</span></span>

- [<span data-ttu-id="9b4cc-129">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="9b4cc-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9b4cc-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9b4cc-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
