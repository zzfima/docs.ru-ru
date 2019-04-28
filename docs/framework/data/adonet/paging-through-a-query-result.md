---
title: Разбивка на страницы результатов запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 023efcc15d7080afc1583f4ad8984e152b86cf23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878388"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="ab440-102">Разбивка на страницы результатов запроса</span><span class="sxs-lookup"><span data-stu-id="ab440-102">Paging Through a Query Result</span></span>
<span data-ttu-id="ab440-103">Постраничный просмотр результатов запроса - это процесс возврата результатов запроса небольшими подмножествами данных (страницами).</span><span class="sxs-lookup"><span data-stu-id="ab440-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="ab440-104">Этот метод часто используется для вывода результатов пользователю в виде небольших фрагментов, с которыми легко работать.</span><span class="sxs-lookup"><span data-stu-id="ab440-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="ab440-105">**DataAdapter** предоставляет возможность возврата одной страницы данных при помощи перегрузок **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="ab440-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="ab440-106">Тем не менее, это может оказаться лучшим выбором для разбиение по страницам результатов большого запроса, поскольку, несмотря на то что **DataAdapter** заполняет целевые объекты <xref:System.Data.DataTable> или <xref:System.Data.DataSet> с только запрошенными записями, а ресурсы, возвращая весь запрос по-прежнему используются.</span><span class="sxs-lookup"><span data-stu-id="ab440-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="ab440-107">Для возврата страницы данных из источника данных без использования лишних ресурсов задайте для запроса дополнительные критерии, которые ограничат число возвращаемых строки только необходимыми.</span><span class="sxs-lookup"><span data-stu-id="ab440-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="ab440-108">Для использования **заполнения** указать метод для возврата страницы данных, **startRecord** параметр, для первой записи на странице данных и **maxRecords** параметра, число записей на странице данных.</span><span class="sxs-lookup"><span data-stu-id="ab440-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="ab440-109">В следующем примере кода показано, как использовать **заполнения** метод для возврата первой страницы результатов запроса, где размер страницы-пять записей.</span><span class="sxs-lookup"><span data-stu-id="ab440-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="ab440-110">В предыдущем примере **набора данных** заполняется только пятью записями, но весь **заказы** возвращается таблица.</span><span class="sxs-lookup"><span data-stu-id="ab440-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="ab440-111">Для заполнения **набора данных** с теми же пятью записями, но возвратить только пять записей, используется ВЕРХНЯЯ и предложениях WHERE в инструкции SQL, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ab440-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ab440-112">Обратите внимание, что при таком способе постраничного просмотра результатов запроса необходимо сохранять уникальный идентификатор, с помощью которого выполняется упорядочение строк. Этот уникальный идентификатор нужно будет передать команде, служащей для возврата следующей страницы записей, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ab440-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="ab440-113">Чтобы возвратить следующую страницу записей с помощью перегрузки **заполнения** метода, принимающего **startRecord** и **maxRecords** параметров, увеличить текущий индекс записи, размер страницы и заполнения таблицы.</span><span class="sxs-lookup"><span data-stu-id="ab440-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="ab440-114">Помните, что сервер базы данных возвращает все результаты запроса, несмотря на то, что добавляется только одна страница записей **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="ab440-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="ab440-115">В следующем примере кода строки таблицы очищаются, а затем заполняются следующей страницей данных.</span><span class="sxs-lookup"><span data-stu-id="ab440-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="ab440-116">Может быть необходимым сохранить определенное число возвращенных строк в локальном кэше, чтобы уменьшить число обращений к серверу базы данных.</span><span class="sxs-lookup"><span data-stu-id="ab440-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="ab440-117">Чтобы возвратить следующую страницу записей, не заставляя сервер баз данных возвращать сразу все результаты запроса, укажите ограничивающие критерии для инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="ab440-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="ab440-118">Так как код предыдущего примера сохранил последнюю возвращенную запись, ее можно использовать в предложении WHERE, чтобы указать для запроса начальную точку, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ab440-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab440-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ab440-119">See also</span></span>

- [<span data-ttu-id="ab440-120">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="ab440-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="ab440-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ab440-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
