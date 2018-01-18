---
title: "Разбивка на страницы результатов запроса"
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
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 83e8241fed71ec4dd0ea32f97b02373f3a1d56bb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="fb4e8-102">Разбивка на страницы результатов запроса</span><span class="sxs-lookup"><span data-stu-id="fb4e8-102">Paging Through a Query Result</span></span>
<span data-ttu-id="fb4e8-103">Постраничный просмотр результатов запроса - это процесс возврата результатов запроса небольшими подмножествами данных (страницами).</span><span class="sxs-lookup"><span data-stu-id="fb4e8-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="fb4e8-104">Этот метод часто используется для вывода результатов пользователю в виде небольших фрагментов, с которыми легко работать.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="fb4e8-105">**DataAdapter** предоставляет возможность возвращать только одну страницу данных путем перегрузки **заполнения** метод.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="fb4e8-106">Однако это не может быть наилучшим решением для постраничного просмотра результатов запроса имеет большой размер, поскольку несмотря на то что **DataAdapter** заполняет целевые <xref:System.Data.DataTable> или <xref:System.Data.DataSet> с только запрошенными записями, а ресурсы, возвращая весь запрос все еще используются.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="fb4e8-107">Для возврата страницы данных из источника данных без использования лишних ресурсов задайте для запроса дополнительные критерии, которые ограничат число возвращаемых строки только необходимыми.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="fb4e8-108">Для использования **заполнения** указать метод для возврата страницы данных, **startRecord** параметр первую запись на странице данных и **maxRecords** параметр количества записей на странице данных.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="fb4e8-109">В следующем примере кода показано, как использовать **заполнения** метод для возврата первой страницы результатов запроса, где размер страницы-пять записей.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="fb4e8-110">В предыдущем примере **набора данных** заполняется только пятью записями, и вся **заказов** возвращается вся таблица.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="fb4e8-111">Для заполнения **набора данных** с теми же пятью записями, но возвратить только пять записей, используйте TOP и WHERE в инструкции SQL, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="fb4e8-112">Обратите внимание, что при таком способе постраничного просмотра результатов запроса необходимо сохранять уникальный идентификатор, с помощью которого выполняется упорядочение строк. Этот уникальный идентификатор нужно будет передать команде, служащей для возврата следующей страницы записей, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="fb4e8-113">Чтобы возвратить следующую страницу записей, используя перегруженный **заполнения** метода, принимающего **startRecord** и **maxRecords** параметров, увеличения значения текущему индексу записи по размер страницы и заполнения таблицы.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="fb4e8-114">Помните, что сервер базы данных возвращает все результаты запроса, несмотря на то, что только одна страница записей добавляется **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="fb4e8-115">В следующем примере кода строки таблицы очищаются, а затем заполняются следующей страницей данных.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="fb4e8-116">Может быть необходимым сохранить определенное число возвращенных строк в локальном кэше, чтобы уменьшить число обращений к серверу базы данных.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="fb4e8-117">Чтобы возвратить следующую страницу записей, не заставляя сервер баз данных возвращать сразу все результаты запроса, укажите ограничивающие критерии для инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="fb4e8-118">Так как код предыдущего примера сохранил последнюю возвращенную запись, ее можно использовать в предложении WHERE, чтобы указать для запроса начальную точку, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="fb4e8-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb4e8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fb4e8-119">See Also</span></span>  
 [<span data-ttu-id="fb4e8-120">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="fb4e8-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="fb4e8-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fb4e8-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
