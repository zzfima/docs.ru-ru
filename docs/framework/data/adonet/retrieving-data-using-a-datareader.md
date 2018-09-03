---
title: Извлечение данных с помощью объекта DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482168"
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="1f33f-102">Извлечение данных с помощью объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="1f33f-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="1f33f-103">Получение данных с помощью **DataReader** включает в себя создание экземпляра **команда** объекта, а затем создать **DataReader** путем вызова  **Command.ExecuteReader** для получения строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="1f33f-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="1f33f-104">В следующем примере демонстрируется использование **DataReader** где `reader` представляет допустимый DataReader и `command` представляет допустимый объект Command.</span><span class="sxs-lookup"><span data-stu-id="1f33f-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="1f33f-105">Использовании **чтения** метод **DataReader** объект для получения строки из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="1f33f-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="1f33f-106">Можно получить доступ к каждого столбца возвращенной строки, передав имя или порядковый номер столбца, **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="1f33f-107">Тем не менее, для наилучшей производительности **DataReader** предоставляет ряд методов, которые дают возможность обращаться к значениям столбцов в собственных типах данных (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, и так далее).</span><span class="sxs-lookup"><span data-stu-id="1f33f-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="1f33f-108">Список типизированных методов доступа для конкретных поставщиков данных **объекты DataReader**, см. в разделе <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="1f33f-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="1f33f-109">Использование типизированных методов доступа при условии, что известен базовый тип данных, сокращает объем преобразований типов, необходимых при извлечении значения столбца.</span><span class="sxs-lookup"><span data-stu-id="1f33f-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f33f-110">Выпуск Windows Server 2003, платформы .NET Framework включает в себя дополнительное свойство **DataReader**, **HasRows**, который позволяет определить, если **DataReader**возвратил никаких результатов, перед чтением из него.</span><span class="sxs-lookup"><span data-stu-id="1f33f-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="1f33f-111">В следующем примере кода выполняется итерация по **DataReader** объекта и возвращаются два столбца из каждой строки.</span><span class="sxs-lookup"><span data-stu-id="1f33f-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="1f33f-112">**DataReader** предоставляет небуферизованный поток данных, позволяющий процедурам последовательно обрабатывать результаты из источника данных.</span><span class="sxs-lookup"><span data-stu-id="1f33f-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="1f33f-113">**DataReader** хорошо подходит при получении больших объемов данных, поскольку данные не кэшируются в памяти.</span><span class="sxs-lookup"><span data-stu-id="1f33f-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="1f33f-114">Закрытие DataReader</span><span class="sxs-lookup"><span data-stu-id="1f33f-114">Closing the DataReader</span></span>  
 <span data-ttu-id="1f33f-115">Следует всегда вызывать **закрыть** метод после завершения с помощью **DataReader** объекта.</span><span class="sxs-lookup"><span data-stu-id="1f33f-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="1f33f-116">Если ваш **команда** содержит выходные данные параметры или возвращаемые значения, они не будут доступны до **DataReader** закрыт.</span><span class="sxs-lookup"><span data-stu-id="1f33f-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="1f33f-117">Обратите внимание, что, хотя **DataReader** открыт, **подключения** используется исключительно этим объектом **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="1f33f-118">Невозможно выполнить команды для **подключения**, включая создание еще одного **DataReader**, пока исходный **DataReader** закрыт.</span><span class="sxs-lookup"><span data-stu-id="1f33f-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f33f-119">Не вызывайте **закрыть** или **Dispose** на **подключения**, **DataReader**, или любого другого управляемого объекта в **Finalize**  метод класса.</span><span class="sxs-lookup"><span data-stu-id="1f33f-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="1f33f-120">В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет.</span><span class="sxs-lookup"><span data-stu-id="1f33f-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="1f33f-121">Если ваш класс не владеет неуправляемые ресурсы, не включайте **Finalize** метод в определении класса.</span><span class="sxs-lookup"><span data-stu-id="1f33f-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="1f33f-122">Дополнительные сведения см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f33f-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="1f33f-123">Извлечение нескольких результирующих наборов при помощи NextResult</span><span class="sxs-lookup"><span data-stu-id="1f33f-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="1f33f-124">Если несколько результирующих наборов при возвращении **DataReader** предоставляет **NextResult** задает метод для выполнения итерации по результат в порядке.</span><span class="sxs-lookup"><span data-stu-id="1f33f-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="1f33f-125">В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f33f-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="1f33f-126">Получение данных схемы от DataReader</span><span class="sxs-lookup"><span data-stu-id="1f33f-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="1f33f-127">Хотя **DataReader** является открытым, можно получить данные схемы о текущем результирующем наборе с помощью **GetSchemaTable** метод.</span><span class="sxs-lookup"><span data-stu-id="1f33f-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="1f33f-128">**GetSchemaTable** возвращает <xref:System.Data.DataTable> заполненный строк и столбцов, содержащих сведения о схеме для текущего результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="1f33f-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="1f33f-129">**DataTable** содержит по одной строке для каждого столбца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="1f33f-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="1f33f-130">Каждый столбец строки таблицы схемы соответствует свойству столбца, возвращенного в результирующем наборе, где **ColumnName** — это имя свойства и значением столбца является значением свойства.</span><span class="sxs-lookup"><span data-stu-id="1f33f-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="1f33f-131">В следующем примере кода записывает сведения о схеме для **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="1f33f-132">Работа с разделами OLE DB</span><span class="sxs-lookup"><span data-stu-id="1f33f-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="1f33f-133">Иерархические наборы строк, или разделы (тип OLE DB **DBTYPE_HCHAPTER**, тип ADO **adChapter**) можно получить с помощью <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="1f33f-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="1f33f-134">Когда запрос, содержащий раздел возвращается в виде **DataReader**, раздел возвращается в виде столбца в этом **DataReader** и указывается в виде **DataReader** объекта.</span><span class="sxs-lookup"><span data-stu-id="1f33f-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="1f33f-135">ADO.NET **набора данных** также может использоваться для представления иерархических наборов строк с помощью родительско дочерних отношений между таблицами.</span><span class="sxs-lookup"><span data-stu-id="1f33f-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="1f33f-136">Дополнительные сведения см. в разделе [наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f33f-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="1f33f-137">В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="1f33f-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="1f33f-138">Возвращение результатов при помощи Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="1f33f-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="1f33f-139">Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса.</span><span class="sxs-lookup"><span data-stu-id="1f33f-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="1f33f-140">Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="1f33f-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="1f33f-141">Вы можете получить **OracleDataReader** объекта, который представляет Oracle REF CURSOR с помощью <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> метод и можно также указать <xref:System.Data.OracleClient.OracleCommand> , возвращающий один или несколько REF CURSOR Oracle в виде  **SelectCommand** для <xref:System.Data.OracleClient.OracleDataAdapter> используются для заполнения <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="1f33f-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="1f33f-142">Чтобы получить доступ к REF CURSOR, возвращенному из источника данных Oracle, создайте **OracleCommand** запроса и добавьте выходной параметр, который ссылается на REF CURSOR **параметры** коллекцию вашей  **OracleCommand**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="1f33f-143">Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе.</span><span class="sxs-lookup"><span data-stu-id="1f33f-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="1f33f-144">Задайте тип параметра для **OracleType.Cursor**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="1f33f-145">**ExecuteReader** метод вашей **OracleCommand** вернет **OracleDataReader** для параметра REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="1f33f-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="1f33f-146">Если ваш **OracleCommand** возвращает несколько параметров REF CURSOR, добавьте несколько выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="1f33f-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="1f33f-147">Доступны различные параметры REF CURSOR, вызвав **OracleCommand.ExecuteReader** метод.</span><span class="sxs-lookup"><span data-stu-id="1f33f-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="1f33f-148">Вызов **ExecuteReader** возвращает **OracleDataReader** ссылки на первый параметр REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="1f33f-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="1f33f-149">Затем можно вызвать **OracleDataReader.NextResult** метод для доступа к последующих параметров REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="1f33f-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="1f33f-150">Хотя параметры в вашей **OracleCommand.Parameters** соответствуют REF CURSOR выходных параметров по имени, **OracleDataReader** получает доступ к ним в порядке, в котором они были добавлены  **Параметры** коллекции.</span><span class="sxs-lookup"><span data-stu-id="1f33f-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="1f33f-151">Например, рассмотрим следующий пакет и текст пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="1f33f-151">For example, consider the following Oracle package and package body.</span></span>  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="1f33f-152">Следующий код создает **OracleCommand** , возвращает параметры REF CURSOR из предыдущего пакета Oracle путем добавления двух параметров типа **OracleType.Cursor** для **параметры** коллекции.</span><span class="sxs-lookup"><span data-stu-id="1f33f-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="1f33f-153">Следующий код возвращает результаты предыдущей команды при помощи **чтения** и **NextResult** методы **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="1f33f-154">Параметры REF CURSOR возвращаются по порядку.</span><span class="sxs-lookup"><span data-stu-id="1f33f-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="1f33f-155">В следующем примере предыдущая команда используется для заполнения **набора данных** с результатами пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="1f33f-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f33f-156">Чтобы избежать **OverflowException**, рекомендуется также производить преобразования из типа Oracle NUMBER в допустимый тип .NET Framework перед сохранением значения в **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="1f33f-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="1f33f-157">Можно использовать **FillError** событий на предмет **OverflowException** произошла.</span><span class="sxs-lookup"><span data-stu-id="1f33f-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="1f33f-158">Дополнительные сведения о **FillError** событий, см. в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="1f33f-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f33f-159">См. также</span><span class="sxs-lookup"><span data-stu-id="1f33f-159">See Also</span></span>  
 [<span data-ttu-id="1f33f-160">Работа с объекты DataReader</span><span class="sxs-lookup"><span data-stu-id="1f33f-160">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="1f33f-161">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="1f33f-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="1f33f-162">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="1f33f-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="1f33f-163">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="1f33f-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="1f33f-164">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1f33f-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
