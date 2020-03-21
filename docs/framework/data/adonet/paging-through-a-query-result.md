---
title: Разбивка на страницы результатов запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 2e7fb97e5c0cb42deff43c411f47e8d30e2257ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149392"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="e9ae4-102">Разбивка на страницы результатов запроса</span><span class="sxs-lookup"><span data-stu-id="e9ae4-102">Paging Through a Query Result</span></span>
<span data-ttu-id="e9ae4-103">Постраничный просмотр результатов запроса - это процесс возврата результатов запроса небольшими подмножествами данных (страницами).</span><span class="sxs-lookup"><span data-stu-id="e9ae4-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="e9ae4-104">Этот метод часто используется для вывода результатов пользователю в виде небольших фрагментов, с которыми легко работать.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="e9ae4-105">**DataAdapter** предоставляет возможность для возвращения только страницы данных, через перегрузки метода **заполнения.**</span><span class="sxs-lookup"><span data-stu-id="e9ae4-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="e9ae4-106">Однако это может быть не лучшим выбором для paging через большие результаты <xref:System.Data.DataTable> <xref:System.Data.DataSet> запроса, потому что, хотя **DataAdapter** заполняет цель или только с запрошенными записями, ресурсы для возврата всего запроса по-прежнему используются.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="e9ae4-107">Для возврата страницы данных из источника данных без использования лишних ресурсов задайте для запроса дополнительные критерии, которые ограничат число возвращаемых строки только необходимыми.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="e9ae4-108">Чтобы использовать метод **заполнения** для возврата страницы данных, укажите параметр **startRecord,** для первой записи на странице данных, и параметр **maxRecords,** для количества записей на странице данных.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="e9ae4-109">В следующем примере кода показано, как использовать метод **заполнения** для возврата первой страницы результата запроса, где размер страницы составляет пять записей.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="e9ae4-110">В предыдущем примере **DataSet** заполнен только пятью записями, но вся таблица **заказов** возвращается.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="e9ae4-111">Чтобы заполнить **DataSet** теми же пятью записями, но вернуть только пять записей, используйте положения TOP и WHERE в выписке из S'L, как в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 <span data-ttu-id="e9ae4-112">Обратите внимание, что при таком способе постраничного просмотра результатов запроса необходимо сохранять уникальный идентификатор, с помощью которого выполняется упорядочение строк. Этот уникальный идентификатор нужно будет передать команде, служащей для возврата следующей страницы записей, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="e9ae4-113">Чтобы вернуть следующую страницу записей, используя перегрузку метода **заполнения,** который принимает параметры **startRecord** и **maxRecords,** наращивайте текущий индекс записи по размеру страницы и заполняйте таблицу.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="e9ae4-114">Помните, что сервер базы данных возвращает все результаты запроса, несмотря на то, что в **DataSet**добавлена только одна страница записей.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="e9ae4-115">В следующем примере кода строки таблицы очищаются, а затем заполняются следующей страницей данных.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="e9ae4-116">Может быть необходимым сохранить определенное число возвращенных строк в локальном кэше, чтобы уменьшить число обращений к серверу базы данных.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="e9ae4-117">Чтобы возвратить следующую страницу записей, не заставляя сервер баз данных возвращать сразу все результаты запроса, укажите ограничивающие критерии для инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="e9ae4-118">Так как код предыдущего примера сохранил последнюю возвращенную запись, ее можно использовать в предложении WHERE, чтобы указать для запроса начальную точку, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9ae4-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9ae4-119">See also</span></span>

- [<span data-ttu-id="e9ae4-120">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="e9ae4-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="e9ae4-121">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9ae4-121">ADO.NET Overview</span></span>](ado-net-overview.md)
