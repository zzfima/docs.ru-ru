---
title: Извлечение данных с помощью объекта DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: ff1869ab17761645321d803f0f7db4bb39c992bc
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093285"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="9f95a-102">Извлечение данных с помощью объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="9f95a-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="9f95a-103">Для получения данных с помощью **DataReader** создайте экземпляр объекта **Command**, а затем создайте **DataReader** путем вызова **Command.ExecuteReader** для получения строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9f95a-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="9f95a-104">**DataReader** предоставляет небуферизованный поток данных, позволяющий эффективно реализовать процедурную логику последовательной обработки результатов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9f95a-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="9f95a-105">**DataReader** хорошо подходит для извлечения больших объемов данных, поскольку данные не кэшируются в памяти.</span><span class="sxs-lookup"><span data-stu-id="9f95a-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="9f95a-106">В следующем примере демонстрируется использование **DataReader**, где `reader` представляет допустимый DataReader и `command` представляет допустимый объект Command.</span><span class="sxs-lookup"><span data-stu-id="9f95a-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="9f95a-107">Используйте метод **DataReader.Read** для получения строки из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="9f95a-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="9f95a-108">Можно получить доступ к каждому столбцу возвращенной строки, передав **DataReader** имя или порядковый номер столбца.</span><span class="sxs-lookup"><span data-stu-id="9f95a-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="9f95a-109">Тем не менее, для наилучшей производительности **DataReader** предоставляет ряд методов, которые дают возможность обращаться к значениям столбцов в собственных типах данных (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, и так далее).</span><span class="sxs-lookup"><span data-stu-id="9f95a-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="9f95a-110">Список типизированных методов доступа для объектов **DataReader** конкретных поставщиков данных см. в разделах <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="9f95a-111">Использование типизированных методов доступа при известном базовом типе данных сокращает объем преобразований типов, необходимых при извлечении значения столбца.</span><span class="sxs-lookup"><span data-stu-id="9f95a-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="9f95a-112">В следующем примере осуществляется проход по **DataReader** и возврат двух столбцов из каждой строки.</span><span class="sxs-lookup"><span data-stu-id="9f95a-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="9f95a-113">Закрытие DataReader</span><span class="sxs-lookup"><span data-stu-id="9f95a-113">Closing the DataReader</span></span>  
 <span data-ttu-id="9f95a-114">Всегда вызывайте метод **Close** после завершения использования объекта **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="9f95a-115">Если ваш объект **Command** содержит выходные параметры или возвращаемые значения, они будут доступны только после закрытия **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="9f95a-116">Когда **DataReader** открыт, объект **Connection** монопольно используется этим объектом **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="9f95a-117">До тех пор, пока исходный объект **DataReader** не закрыт, для объекта **Connection** невозможно выполнение команд, в том числе создание еще одного **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f95a-118">Не вызывайте **Close** или **Dispose** для объектов **Connection**, **DataReader** или любого другого управляемого объекта в методе **Finalize**  класса.</span><span class="sxs-lookup"><span data-stu-id="9f95a-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="9f95a-119">В методе завершения следует освобождать только неуправляемые ресурсы, которыми ваш класс непосредственно владеет.</span><span class="sxs-lookup"><span data-stu-id="9f95a-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="9f95a-120">Если ваш класс не владеет неуправляемыми ресурсами, не включайте в определение класс метод **Finalize**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="9f95a-121">Дополнительные сведения см. в разделе [Сборка мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f95a-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="9f95a-122">Извлечение нескольких результирующих наборов с помощью NextResult</span><span class="sxs-lookup"><span data-stu-id="9f95a-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="9f95a-123">Если **DataReader** возвращает несколько результирующих наборов, используйте метод **NextResult** для последовательного прохода по ним.</span><span class="sxs-lookup"><span data-stu-id="9f95a-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="9f95a-124">В следующем примере показана обработка результатов двух инструкций SELECT в <xref:System.Data.SqlClient.SqlDataReader> с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="9f95a-125">Получение сведений о схеме из DataReader</span><span class="sxs-lookup"><span data-stu-id="9f95a-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="9f95a-126">Пока **DataReader** открыт, можно получить сведения о схеме для текущего результирующего набора с помощью метода **GetSchemaTable**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="9f95a-127">**GetSchemaTable** возвращает объект <xref:System.Data.DataTable>, заполненный строками и столбцами, содержащими сведения о схеме для текущего результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="9f95a-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="9f95a-128">**DataTable** содержит по одной строке для каждого столбца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="9f95a-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="9f95a-129">Каждый столбец в таблице схемы соответствует свойству столбца, возвращаемого в строках результирующего набора, где **ColumnName** — это имя свойства, а значением столбца является значение свойства.</span><span class="sxs-lookup"><span data-stu-id="9f95a-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="9f95a-130">Следующий пример выводит сведения о схеме для **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="9f95a-131">Работа с разделами OLE DB</span><span class="sxs-lookup"><span data-stu-id="9f95a-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="9f95a-132">Иерархические наборы строк, или разделы (тип OLE DB **DBTYPE_HCHAPTER**, тип ADO **adChapter**), можно получить с помощью <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="9f95a-133">Когда для возврата результатов запроса, содержащего раздел, используется **DataReader**, раздел возвращается в виде столбца в этом **DataReader** и представляется в виде объекта **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9f95a-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="9f95a-134">**DataSet** из ADO.NET также может использоваться для представления иерархических наборов строк с использованием отношений "родитель — потомок" между таблицами.</span><span class="sxs-lookup"><span data-stu-id="9f95a-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="9f95a-135">Дополнительные сведения см. в разделе [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f95a-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="9f95a-136">В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="9f95a-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="9f95a-137">Возврат результатов с использованием параметров REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="9f95a-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="9f95a-138">Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возврата результата запроса.</span><span class="sxs-lookup"><span data-stu-id="9f95a-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="9f95a-139">Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="9f95a-140">Вы можете получить объект <xref:System.Data.OracleClient.OracleDataReader>, представляющий Oracle REF CURSOR, используя метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="9f95a-141">Можно также указать <xref:System.Data.OracleClient.OracleCommand>, возвращающий один или несколько REF CURSOR Oracle, в качестве **SelectCommand** для <xref:System.Data.OracleClient.OracleDataAdapter>, используемого для заполнения <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="9f95a-142">Чтобы получить доступ к REF CURSOR, возвращенному из источника данных Oracle, создайте запрос <xref:System.Data.OracleClient.OracleCommand> и добавьте выходной параметр, который ссылается на REF CURSOR, в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters> вашего объекта <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="9f95a-143">Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе.</span><span class="sxs-lookup"><span data-stu-id="9f95a-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="9f95a-144">В качестве типа параметра установите <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9f95a-145">Метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> вашего объекта <xref:System.Data.OracleClient.OracleCommand> возвращает <xref:System.Data.OracleClient.OracleDataReader> для параметра REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="9f95a-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="9f95a-146">Если ваш объект <xref:System.Data.OracleClient.OracleCommand> возвращает несколько параметров REF CURSOR, добавьте несколько выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="9f95a-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="9f95a-147">Можно получить доступ к разным параметрам REF CURSOR, вызвав метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9f95a-148">Вызов <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возвращает <xref:System.Data.OracleClient.OracleDataReader>, ссылающийся на первый REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="9f95a-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="9f95a-149">Затем можно вызвать метод <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> для доступа к следующим параметрам REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="9f95a-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="9f95a-150">Хотя параметры в вашей коллекции <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> соответствуют выходным параметрам REF CURSOR по имени, <xref:System.Data.OracleClient.OracleDataReader> осуществляет доступ к ним в том порядке, в котором они были добавлены в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="9f95a-151">Например, рассмотрим следующий пакет и текст пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="9f95a-151">For example, consider the following Oracle package and package body.</span></span>  
  
```sql
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
  
 <span data-ttu-id="9f95a-152">Следующий код создает команду <xref:System.Data.OracleClient.OracleCommand>, которая возвращает параметры REF CURSOR из приведенного выше пакета Oracle путем добавления двух параметров типа <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> в коллекцию <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="9f95a-153">Следующий код возвращает результаты приведенной выше команды, используя методы <xref:System.Data.OracleClient.OracleDataReader.Read> и <xref:System.Data.OracleClient.OracleDataReader.NextResult> объекта <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="9f95a-154">Параметры REF CURSOR возвращаются по порядку.</span><span class="sxs-lookup"><span data-stu-id="9f95a-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="9f95a-155">В следующем примере приведенная выше команда используется для заполнения <xref:System.Data.DataSet> результатами пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="9f95a-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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

> [!NOTE]
>  <span data-ttu-id="9f95a-156">Чтобы избежать **OverflowException**, рекомендуется также производить преобразование из типа Oracle NUMBER в допустимый тип .NET Framework перед сохранением значения в <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="9f95a-157">Чтобы отследить возникновение **OverflowException**, можно использовать событие <xref:System.Data.Common.DataAdapter.FillError>.</span><span class="sxs-lookup"><span data-stu-id="9f95a-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="9f95a-158">Дополнительные сведения о событии <xref:System.Data.Common.DataAdapter.FillError> см. в разделе [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="9f95a-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f95a-159">См. также</span><span class="sxs-lookup"><span data-stu-id="9f95a-159">See also</span></span>
- [<span data-ttu-id="9f95a-160">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="9f95a-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="9f95a-161">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="9f95a-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="9f95a-162">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="9f95a-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="9f95a-163">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9f95a-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
