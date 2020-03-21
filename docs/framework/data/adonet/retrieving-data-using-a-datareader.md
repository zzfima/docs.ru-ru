---
title: Извлечение данных с помощью объекта DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149028"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="3950c-102">Извлечение данных с помощью DataReader</span><span class="sxs-lookup"><span data-stu-id="3950c-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="3950c-103">Для получения данных с помощью **DataReader**создайте экземпляр объекта **командования,** а затем создайте **DataReader,** позвонив **в Command.ExecuteReader** для извлечения строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="3950c-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="3950c-104">**DataReader** обеспечивает небуферированный поток данных, что позволяет процедурной логике эффективно обрабатывать результаты из источника данных последовательно.</span><span class="sxs-lookup"><span data-stu-id="3950c-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="3950c-105">**DataReader** является хорошим выбором при извлечении больших объемов данных, поскольку данные не кэшируются в памяти.</span><span class="sxs-lookup"><span data-stu-id="3950c-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="3950c-106">Ниже приведен пример, иллюстрирующий использование **DataReader,** где `reader` он представляет собой действительный DataReader и `command` представляет собой допустимый объект Командного управления.</span><span class="sxs-lookup"><span data-stu-id="3950c-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="3950c-107">Используйте метод **DataReader.Read** для получения строки из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="3950c-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="3950c-108">Вы можете получить доступ к каждой колонке возвращенной строки, передавая имя или ординаторский номер столбца **DataReader.**</span><span class="sxs-lookup"><span data-stu-id="3950c-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="3950c-109">Однако, для лучшей производительности, **DataReader** предоставляет ряд методов, которые позволяют получить доступ к значениям столбцов в их родных типах данных **(GetDateTime,** **GetDouble**, **GetGuid**, **GetInt32**и так далее).</span><span class="sxs-lookup"><span data-stu-id="3950c-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="3950c-110">Для списка набранных методов доступа для данных поставщика <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.SqlClient.SqlDataReader>данных **конкретных DataReaders**, см.</span><span class="sxs-lookup"><span data-stu-id="3950c-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="3950c-111">Использование набранных методов доступа, когда вы знаете, что базовый тип данных уменьшает количество преобразования типа, необходимого при извлечении значения столбца.</span><span class="sxs-lookup"><span data-stu-id="3950c-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="3950c-112">Следующий пример итерирует объект **DataReader** и возвращает по две столбцы из каждой строки.</span><span class="sxs-lookup"><span data-stu-id="3950c-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="3950c-113">Закрытие DataReader</span><span class="sxs-lookup"><span data-stu-id="3950c-113">Closing the DataReader</span></span>  
 <span data-ttu-id="3950c-114">Всегда вызывайте метод **Close,** когда вы закончите использовать объект **DataReader.**</span><span class="sxs-lookup"><span data-stu-id="3950c-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="3950c-115">Если **команда** содержит параметры вывода или значения возврата, эти значения недоступны до закрытия **DataReader.**</span><span class="sxs-lookup"><span data-stu-id="3950c-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="3950c-116">В то время как **DataReader** открыт, **соединение** используется исключительно тем **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="3950c-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="3950c-117">Вы не можете выполнять какие-либо команды для **соединения,** включая создание другого **DataReader,** до тех пор, пока исходный **DataReader** не будет закрыт.</span><span class="sxs-lookup"><span data-stu-id="3950c-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3950c-118">Не вызывайте **Close** или **Dispose** на **соединение,** **DataReader**или любой другой управляемый объект в методе **завершения** вашего класса.</span><span class="sxs-lookup"><span data-stu-id="3950c-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="3950c-119">В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет.</span><span class="sxs-lookup"><span data-stu-id="3950c-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="3950c-120">Если ваш класс не владеет неуправляемыми ресурсами, не включайте метод **завершения** в определение класса.</span><span class="sxs-lookup"><span data-stu-id="3950c-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="3950c-121">Для получения дополнительной информации, см [Мусорная коллекция](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="3950c-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="3950c-122">Получение нескольких наборов результатов с помощью NextResult</span><span class="sxs-lookup"><span data-stu-id="3950c-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="3950c-123">Если **DataReader** возвращает несколько наборов результатов, вызовите метод **NextResult,** чтобы последовательно итерировать через наборы результатов.</span><span class="sxs-lookup"><span data-stu-id="3950c-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="3950c-124">В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="3950c-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="3950c-125">Получение информации о схемах от DataReader</span><span class="sxs-lookup"><span data-stu-id="3950c-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="3950c-126">Во время открытия **DataReader** можно получить информацию о результатах схемы с помощью метода **GetSchemaTable.**</span><span class="sxs-lookup"><span data-stu-id="3950c-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="3950c-127">**GetSchemaTable** возвращает <xref:System.Data.DataTable> объект, населенный строками и столбцов, содержащими информацию о схеме для текущего набора результатов.</span><span class="sxs-lookup"><span data-stu-id="3950c-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="3950c-128">**DataTable** содержит по одной строке для каждого столбца набора результатов.</span><span class="sxs-lookup"><span data-stu-id="3950c-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="3950c-129">Каждая колонка таблицы схемы отображает свойство столбцов, возвращенных в ряды набора результатов, где **ColumnName** является именем свойства, а значение столбца — значением свойства.</span><span class="sxs-lookup"><span data-stu-id="3950c-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="3950c-130">Следующий пример выписывает информацию о схеме для **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="3950c-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="3950c-131">Работа с главами OLE DB</span><span class="sxs-lookup"><span data-stu-id="3950c-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="3950c-132">Иерархические наборы строк или глав (тип OLE DB **DBTYPE_HCHAPTER,** ADO type <xref:System.Data.OleDb.OleDbDataReader> **adChapter),** можно получить с помощью .</span><span class="sxs-lookup"><span data-stu-id="3950c-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="3950c-133">Когда запрос, включающий главу, возвращается в качестве **DataReader,** глава возвращается в качестве столбца в этом **DataReader** и подвергается воздействию объекта **DataReader.**</span><span class="sxs-lookup"><span data-stu-id="3950c-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="3950c-134">ADO.NET **DataSet** также может использоваться для представления иерархических рядов с помощью отношений между родительскими и детскими отношениями между таблицами.</span><span class="sxs-lookup"><span data-stu-id="3950c-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="3950c-135">Для получения дополнительной [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="3950c-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="3950c-136">В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="3950c-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="3950c-137">Возвращение результатов с Oracle REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="3950c-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="3950c-138">Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса.</span><span class="sxs-lookup"><span data-stu-id="3950c-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="3950c-139">Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="3950c-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="3950c-140">Вы можете получить <xref:System.Data.OracleClient.OracleDataReader> объект, представляющий Oracle REF CURSOR, с помощью метода. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A></span><span class="sxs-lookup"><span data-stu-id="3950c-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="3950c-141">Вы также можете <xref:System.Data.OracleClient.OracleCommand> указать, что возвращает один или несколько Oracle <xref:System.Data.OracleClient.OracleDataAdapter> REF <xref:System.Data.DataSet>CURSORs в качестве **SelectCommand** для используемого для заполнения .</span><span class="sxs-lookup"><span data-stu-id="3950c-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="3950c-142">Чтобы получить доступ к REF CURSOR, возвращенным из источника данных Oracle, создайте <xref:System.Data.OracleClient.OracleCommand> для запроса <xref:System.Data.OracleClient.OracleCommand.Parameters> и добавьте параметр вывода, который ссылается на REF CURSOR в коллекцию вашего. <xref:System.Data.OracleClient.OracleCommand></span><span class="sxs-lookup"><span data-stu-id="3950c-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="3950c-143">Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе.</span><span class="sxs-lookup"><span data-stu-id="3950c-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="3950c-144">Установите тип параметра. <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3950c-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3950c-145">Метод <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> вашего <xref:System.Data.OracleClient.OracleCommand> возврата <xref:System.Data.OracleClient.OracleDataReader> для REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="3950c-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="3950c-146">Если <xref:System.Data.OracleClient.OracleCommand> возвращается несколько REF CURSORS, добавьте несколько параметров вывода.</span><span class="sxs-lookup"><span data-stu-id="3950c-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="3950c-147">Вы можете получить доступ к различным REF CURSORs, позвонив по методу. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3950c-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3950c-148">Призыв к <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возврату <xref:System.Data.OracleClient.OracleDataReader> ссылки на первый REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="3950c-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="3950c-149">Затем можно вызвать <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> метод для доступа к последующим REF CURSORs.</span><span class="sxs-lookup"><span data-stu-id="3950c-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="3950c-150">Хотя параметры в <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> вашей коллекции соответствуют параметрам вывода <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR по имени, доступ <xref:System.Data.OracleClient.OracleCommand.Parameters> к ним в порядке, в котором они были добавлены в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="3950c-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="3950c-151">Например, рассмотрим следующий пакет и текст пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="3950c-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="3950c-152">Следующий код <xref:System.Data.OracleClient.OracleCommand> создает, что возвращает REF CURSORs из предыдущего пакета <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> Oracle, добавив два параметра типа в коллекцию. <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3950c-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="3950c-153">Следующий код возвращает результаты предыдущей <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> команды с <xref:System.Data.OracleClient.OracleDataReader>использованием и методов .</span><span class="sxs-lookup"><span data-stu-id="3950c-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="3950c-154">Параметры REF CURSOR возвращаются по порядку.</span><span class="sxs-lookup"><span data-stu-id="3950c-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="3950c-155">В следующем примере предыдущая команда <xref:System.Data.DataSet> заполняет результаты пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="3950c-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="3950c-156">Чтобы избежать **OverflowException,** мы рекомендуем также обрабатывать любое преобразование из типа Oracle NUMBER в действительный тип рамочного соглашения .NET, прежде чем хранить значение в <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="3950c-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="3950c-157">Событие можно <xref:System.Data.Common.DataAdapter.FillError> использовать, чтобы определить, произошло ли **переполнение.**</span><span class="sxs-lookup"><span data-stu-id="3950c-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="3950c-158">Для получения дополнительной <xref:System.Data.Common.DataAdapter.FillError> информации о событии см. [Handling DataAdapter Events](handling-dataadapter-events.md)</span><span class="sxs-lookup"><span data-stu-id="3950c-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3950c-159">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3950c-159">See also</span></span>

- [<span data-ttu-id="3950c-160">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="3950c-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="3950c-161">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="3950c-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="3950c-162">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="3950c-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="3950c-163">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3950c-163">ADO.NET Overview</span></span>](ado-net-overview.md)
