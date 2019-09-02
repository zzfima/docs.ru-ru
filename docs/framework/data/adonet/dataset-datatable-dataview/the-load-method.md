---
title: Метод Load
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: b704deeffcd06bca09b6c26d60a66218b46fc55c
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203167"
---
# <a name="the-load-method"></a><span data-ttu-id="a1fe4-102">Метод Load</span><span class="sxs-lookup"><span data-stu-id="a1fe4-102">The Load Method</span></span>
<span data-ttu-id="a1fe4-103">Метод <xref:System.Data.DataTable.Load%2A> используется для загрузки в таблицу <xref:System.Data.DataTable> строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="a1fe4-104">Это перегруженный метод, который в простейшей форме принимает один параметр — **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="a1fe4-105">В этой форме он просто загружает **таблицу данных DataTable** со строками.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="a1fe4-106">При необходимости можно указать параметр **loadOption** для управления добавлением данных в **таблицу DataTable**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="a1fe4-107">Параметр **loadOption** особенно полезен в случаях, когда объект **DataTable** уже содержит строки данных, поскольку он описывает, как входящие данные из источника данных будут объединены с данными, уже находящихся в таблице.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="a1fe4-108">Например, **пресервекуррентвалуес** (значение по умолчанию) указывает, что в случаях, когда строка помечена как **добавленная** в **таблицу**данных, **исходное** значение или каждый столбец задается в соответствии с содержимым соответствующей строки из источника.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="a1fe4-109">**Текущее** значение будет хранить значения, назначенные при добавлении строки, а **RowState** строки будет **изменено**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="a1fe4-110">В следующей таблице приведено краткое описание значений перечисления <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="a1fe4-111">Значение LoadOption</span><span class="sxs-lookup"><span data-stu-id="a1fe4-111">LoadOption value</span></span>|<span data-ttu-id="a1fe4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a1fe4-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="a1fe4-113">**овервритеров**</span><span class="sxs-lookup"><span data-stu-id="a1fe4-113">**OverwriteRow**</span></span>|<span data-ttu-id="a1fe4-114">Если входящие строки имеют то же значение **PrimaryKey** , что и строка, уже находящиеся в **DataTable**, то **исходные** и **текущие** значения каждого столбца заменяются значениями во входной строке, а свойство **RowState** устанавливается в значение **Без изменений**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a1fe4-115">Строки из источника данных, которые еще не существуют в **DataTable** , добавляются со значением **RowState** без **изменений**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a1fe4-116">Этот параметр в силе обновляет содержимое **таблицы DataTable** , чтобы оно соответствовало содержимому источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="a1fe4-117">**Пресервекуррентвалуес (по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="a1fe4-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="a1fe4-118">Если входящие строки имеют то же значение **PrimaryKey** , что и строка, уже находящиеся в **DataTable**, то **исходное** значение устанавливается на содержимое входящей строки, а **Текущее** значение не изменяется.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="a1fe4-119">При **добавлении** или **изменении** **RowState** оно **изменяется**на изменено.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="a1fe4-120">Если параметр **RowState** **удален**, он остается **удаленным**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="a1fe4-121">Строки из источника данных, которые еще не существуют в **DataTable** , добавляются, а для **RowState** устанавливается значение **без изменений**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="a1fe4-122">**упдатекуррентвалуес**</span><span class="sxs-lookup"><span data-stu-id="a1fe4-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="a1fe4-123">Если входящие строки имеют то же значение **PrimaryKey** , что и строка, уже находящиеся в **DataTable**, **Текущее** значение копируется в **исходное** значение, а **Текущее** значение затем устанавливается в содержимое входящей строки.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="a1fe4-124">Если свойство **RowState** в **таблице DataTable** было **добавлено**, то свойство **RowState** остается **добавленным**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="a1fe4-125">Для строк, помеченных как **измененные** или **Удаленные**, свойство **RowState** **изменяется**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="a1fe4-126">Строки из источника данных, которые еще не существуют в **DataTable** , добавляются, а для свойства **RowState** устанавливается значение **added**.</span><span class="sxs-lookup"><span data-stu-id="a1fe4-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="a1fe4-127">В следующем примере метод **Load** используется для вывода списка дней рождения сотрудников в базе данных **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="a1fe4-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1fe4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a1fe4-128">See also</span></span>

- [<span data-ttu-id="a1fe4-129">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="a1fe4-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="a1fe4-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1fe4-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
