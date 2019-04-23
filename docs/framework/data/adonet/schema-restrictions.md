---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: b5044d39d1dc5d2fa7d2ce691cdda7075fa0e32a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151207"
---
# <a name="schema-restrictions"></a><span data-ttu-id="62cc0-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="62cc0-102">Schema Restrictions</span></span>
<span data-ttu-id="62cc0-103">Вторым необязательным параметром метода **GetSchema** метод является возвращаемых ограничения, которые используются для ограничения объема данных схемы, и он передается **GetSchema** метод как массив строк .</span><span class="sxs-lookup"><span data-stu-id="62cc0-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="62cc0-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="62cc0-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="62cc0-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62cc0-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="62cc0-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="62cc0-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="62cc0-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-107">Restriction Name</span></span>|<span data-ttu-id="62cc0-108">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-108">Parameter Name</span></span>|<span data-ttu-id="62cc0-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-109">Restriction Default</span></span>|<span data-ttu-id="62cc0-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-111">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-112">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-113">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-113">1</span></span>|  
|<span data-ttu-id="62cc0-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-114">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-116">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-116">2</span></span>|  
|<span data-ttu-id="62cc0-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-117">Table</span></span>|@Name|<span data-ttu-id="62cc0-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-118">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-119">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-119">3</span></span>|  
|<span data-ttu-id="62cc0-120">TableType</span><span class="sxs-lookup"><span data-stu-id="62cc0-120">TableType</span></span>|@TableType|<span data-ttu-id="62cc0-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="62cc0-121">TABLE_TYPE</span></span>|<span data-ttu-id="62cc0-122">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="62cc0-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="62cc0-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="62cc0-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="62cc0-125">Например, чтобы ограничить таблицы, возвращаемые **GetSchema** метод только таблицами из схемы «Sales», присвойте второму элементу массива значение «Sales» перед передачей в **GetSchema** метод.</span><span class="sxs-lookup"><span data-stu-id="62cc0-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62cc0-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="62cc0-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="62cc0-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="62cc0-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="62cc0-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="62cc0-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62cc0-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="62cc0-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="62cc0-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="62cc0-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="62cc0-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="62cc0-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="62cc0-132">Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых ограничений, вызвав **GetSchema** метод с именем коллекции схем ограничений, который является «Ограничения».</span><span class="sxs-lookup"><span data-stu-id="62cc0-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="62cc0-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="62cc0-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="62cc0-134">Пример</span><span class="sxs-lookup"><span data-stu-id="62cc0-134">Example</span></span>  
 <span data-ttu-id="62cc0-135">Следующие примеры демонстрируют, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> класса для извлечения сведений схем обо всех таблицах, содержащихся в **AdventureWorks**образца базы данных, и для ограничения сведений, возвращается только таблицами из схемы «Sales»:</span><span class="sxs-lookup"><span data-stu-id="62cc0-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="62cc0-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="62cc0-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="62cc0-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62cc0-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="62cc0-138">Users</span><span class="sxs-lookup"><span data-stu-id="62cc0-138">Users</span></span>  
  
|<span data-ttu-id="62cc0-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-139">Restriction Name</span></span>|<span data-ttu-id="62cc0-140">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-140">Parameter Name</span></span>|<span data-ttu-id="62cc0-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-141">Restriction Default</span></span>|<span data-ttu-id="62cc0-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="62cc0-143">User_Name</span></span>|@Name|<span data-ttu-id="62cc0-144">имя</span><span class="sxs-lookup"><span data-stu-id="62cc0-144">name</span></span>|<span data-ttu-id="62cc0-145">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="62cc0-146">Базы данных</span><span class="sxs-lookup"><span data-stu-id="62cc0-146">Databases</span></span>  
  
|<span data-ttu-id="62cc0-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-147">Restriction Name</span></span>|<span data-ttu-id="62cc0-148">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-148">Parameter Name</span></span>|<span data-ttu-id="62cc0-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-149">Restriction Default</span></span>|<span data-ttu-id="62cc0-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-151">name</span><span class="sxs-lookup"><span data-stu-id="62cc0-151">Name</span></span>|@Name|<span data-ttu-id="62cc0-152">name</span><span class="sxs-lookup"><span data-stu-id="62cc0-152">Name</span></span>|<span data-ttu-id="62cc0-153">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="62cc0-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="62cc0-154">Tables</span></span>  
  
|<span data-ttu-id="62cc0-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-155">Restriction Name</span></span>|<span data-ttu-id="62cc0-156">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-156">Parameter Name</span></span>|<span data-ttu-id="62cc0-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-157">Restriction Default</span></span>|<span data-ttu-id="62cc0-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-159">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-160">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-161">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-161">1</span></span>|  
|<span data-ttu-id="62cc0-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-162">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-164">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-164">2</span></span>|  
|<span data-ttu-id="62cc0-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-165">Table</span></span>|@Name|<span data-ttu-id="62cc0-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-166">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-167">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-167">3</span></span>|  
|<span data-ttu-id="62cc0-168">TableType</span><span class="sxs-lookup"><span data-stu-id="62cc0-168">TableType</span></span>|@TableType|<span data-ttu-id="62cc0-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="62cc0-169">TABLE_TYPE</span></span>|<span data-ttu-id="62cc0-170">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="62cc0-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="62cc0-171">Columns</span></span>  
  
|<span data-ttu-id="62cc0-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-172">Restriction Name</span></span>|<span data-ttu-id="62cc0-173">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-173">Parameter Name</span></span>|<span data-ttu-id="62cc0-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-174">Restriction Default</span></span>|<span data-ttu-id="62cc0-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-176">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-177">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-178">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-178">1</span></span>|  
|<span data-ttu-id="62cc0-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-179">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-181">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-181">2</span></span>|  
|<span data-ttu-id="62cc0-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-182">Table</span></span>|@Table|<span data-ttu-id="62cc0-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-183">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-184">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-184">3</span></span>|  
|<span data-ttu-id="62cc0-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="62cc0-185">Column</span></span>|@Column|<span data-ttu-id="62cc0-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-186">COLUMN_NAME</span></span>|<span data-ttu-id="62cc0-187">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="62cc0-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="62cc0-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="62cc0-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-189">Restriction Name</span></span>|<span data-ttu-id="62cc0-190">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-190">Parameter Name</span></span>|<span data-ttu-id="62cc0-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-191">Restriction Default</span></span>|<span data-ttu-id="62cc0-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-193">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-194">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-195">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-195">1</span></span>|  
|<span data-ttu-id="62cc0-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-196">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-198">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-198">2</span></span>|  
|<span data-ttu-id="62cc0-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-199">Table</span></span>|@Table|<span data-ttu-id="62cc0-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-200">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-201">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-201">3</span></span>|  
|<span data-ttu-id="62cc0-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="62cc0-202">Column</span></span>|@Column|<span data-ttu-id="62cc0-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-203">COLUMN_NAME</span></span>|<span data-ttu-id="62cc0-204">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="62cc0-205">Представления</span><span class="sxs-lookup"><span data-stu-id="62cc0-205">Views</span></span>  
  
|<span data-ttu-id="62cc0-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-206">Restriction Name</span></span>|<span data-ttu-id="62cc0-207">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-207">Parameter Name</span></span>|<span data-ttu-id="62cc0-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-208">Restriction Default</span></span>|<span data-ttu-id="62cc0-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-210">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-211">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-212">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-212">1</span></span>|  
|<span data-ttu-id="62cc0-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-213">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-215">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-215">2</span></span>|  
|<span data-ttu-id="62cc0-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-216">Table</span></span>|@Table|<span data-ttu-id="62cc0-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-217">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-218">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="62cc0-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="62cc0-219">ViewColumns</span></span>  
  
|<span data-ttu-id="62cc0-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-220">Restriction Name</span></span>|<span data-ttu-id="62cc0-221">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-221">Parameter Name</span></span>|<span data-ttu-id="62cc0-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-222">Restriction Default</span></span>|<span data-ttu-id="62cc0-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-224">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-225">VIEW_CATALOG</span></span>|<span data-ttu-id="62cc0-226">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-226">1</span></span>|  
|<span data-ttu-id="62cc0-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-227">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="62cc0-229">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-229">2</span></span>|  
|<span data-ttu-id="62cc0-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-230">Table</span></span>|@Table|<span data-ttu-id="62cc0-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-231">VIEW_NAME</span></span>|<span data-ttu-id="62cc0-232">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-232">3</span></span>|  
|<span data-ttu-id="62cc0-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="62cc0-233">Column</span></span>|@Column|<span data-ttu-id="62cc0-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-234">COLUMN_NAME</span></span>|<span data-ttu-id="62cc0-235">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="62cc0-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="62cc0-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="62cc0-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-237">Restriction Name</span></span>|<span data-ttu-id="62cc0-238">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-238">Parameter Name</span></span>|<span data-ttu-id="62cc0-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-239">Restriction Default</span></span>|<span data-ttu-id="62cc0-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-241">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="62cc0-243">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-243">1</span></span>|  
|<span data-ttu-id="62cc0-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-244">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="62cc0-246">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-246">2</span></span>|  
|<span data-ttu-id="62cc0-247">name</span><span class="sxs-lookup"><span data-stu-id="62cc0-247">Name</span></span>|@Name|<span data-ttu-id="62cc0-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="62cc0-249">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-249">3</span></span>|  
|<span data-ttu-id="62cc0-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="62cc0-250">Parameter</span></span>|@Parameter|<span data-ttu-id="62cc0-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-251">PARAMETER_NAME</span></span>|<span data-ttu-id="62cc0-252">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="62cc0-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="62cc0-253">Procedures</span></span>  
  
|<span data-ttu-id="62cc0-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-254">Restriction Name</span></span>|<span data-ttu-id="62cc0-255">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-255">Parameter Name</span></span>|<span data-ttu-id="62cc0-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-256">Restriction Default</span></span>|<span data-ttu-id="62cc0-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-258">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="62cc0-260">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-260">1</span></span>|  
|<span data-ttu-id="62cc0-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-261">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="62cc0-263">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-263">2</span></span>|  
|<span data-ttu-id="62cc0-264">name</span><span class="sxs-lookup"><span data-stu-id="62cc0-264">Name</span></span>|@Name|<span data-ttu-id="62cc0-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="62cc0-266">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-266">3</span></span>|  
|<span data-ttu-id="62cc0-267">Тип</span><span class="sxs-lookup"><span data-stu-id="62cc0-267">Type</span></span>|@Type|<span data-ttu-id="62cc0-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="62cc0-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="62cc0-269">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="62cc0-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="62cc0-270">IndexColumns</span></span>  
  
|<span data-ttu-id="62cc0-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-271">Restriction Name</span></span>|<span data-ttu-id="62cc0-272">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-272">Parameter Name</span></span>|<span data-ttu-id="62cc0-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-273">Restriction Default</span></span>|<span data-ttu-id="62cc0-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-275">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="62cc0-276">db_name()</span></span>|<span data-ttu-id="62cc0-277">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-277">1</span></span>|  
|<span data-ttu-id="62cc0-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-278">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="62cc0-279">user_name()</span></span>|<span data-ttu-id="62cc0-280">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-280">2</span></span>|  
|<span data-ttu-id="62cc0-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-281">Table</span></span>|@Table|<span data-ttu-id="62cc0-282">o.name</span><span class="sxs-lookup"><span data-stu-id="62cc0-282">o.name</span></span>|<span data-ttu-id="62cc0-283">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-283">3</span></span>|  
|<span data-ttu-id="62cc0-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="62cc0-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="62cc0-285">x.name</span><span class="sxs-lookup"><span data-stu-id="62cc0-285">x.name</span></span>|<span data-ttu-id="62cc0-286">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-286">4</span></span>|  
|<span data-ttu-id="62cc0-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="62cc0-287">Column</span></span>|@Column|<span data-ttu-id="62cc0-288">c.name</span><span class="sxs-lookup"><span data-stu-id="62cc0-288">c.name</span></span>|<span data-ttu-id="62cc0-289">5</span><span class="sxs-lookup"><span data-stu-id="62cc0-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="62cc0-290">Индексы</span><span class="sxs-lookup"><span data-stu-id="62cc0-290">Indexes</span></span>  
  
|<span data-ttu-id="62cc0-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-291">Restriction Name</span></span>|<span data-ttu-id="62cc0-292">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-292">Parameter Name</span></span>|<span data-ttu-id="62cc0-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-293">Restriction Default</span></span>|<span data-ttu-id="62cc0-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-295">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="62cc0-296">db_name()</span></span>|<span data-ttu-id="62cc0-297">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-297">1</span></span>|  
|<span data-ttu-id="62cc0-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-298">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="62cc0-299">user_name()</span></span>|<span data-ttu-id="62cc0-300">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-300">2</span></span>|  
|<span data-ttu-id="62cc0-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-301">Table</span></span>|@Table|<span data-ttu-id="62cc0-302">o.name</span><span class="sxs-lookup"><span data-stu-id="62cc0-302">o.name</span></span>|<span data-ttu-id="62cc0-303">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="62cc0-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="62cc0-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="62cc0-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-305">Restriction Name</span></span>|<span data-ttu-id="62cc0-306">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-306">Parameter Name</span></span>|<span data-ttu-id="62cc0-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-307">Restriction Default</span></span>|<span data-ttu-id="62cc0-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="62cc0-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="62cc0-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="62cc0-310">assemblies.name</span></span>|<span data-ttu-id="62cc0-311">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-311">1</span></span>|  
|<span data-ttu-id="62cc0-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="62cc0-312">udt_name</span></span>|@UDTName|<span data-ttu-id="62cc0-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="62cc0-313">types.assembly_class</span></span>|<span data-ttu-id="62cc0-314">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="62cc0-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="62cc0-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="62cc0-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-316">Restriction Name</span></span>|<span data-ttu-id="62cc0-317">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-317">Parameter Name</span></span>|<span data-ttu-id="62cc0-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-318">Restriction Default</span></span>|<span data-ttu-id="62cc0-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-320">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="62cc0-322">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-322">1</span></span>|  
|<span data-ttu-id="62cc0-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-323">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="62cc0-325">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-325">2</span></span>|  
|<span data-ttu-id="62cc0-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-326">Table</span></span>|@Table|<span data-ttu-id="62cc0-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-327">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-328">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-328">3</span></span>|  
|<span data-ttu-id="62cc0-329">name</span><span class="sxs-lookup"><span data-stu-id="62cc0-329">Name</span></span>|@Name|<span data-ttu-id="62cc0-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="62cc0-331">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="62cc0-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="62cc0-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="62cc0-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="62cc0-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="62cc0-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="62cc0-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="62cc0-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62cc0-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="62cc0-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="62cc0-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="62cc0-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-337">Restriction Name</span></span>|<span data-ttu-id="62cc0-338">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-338">Parameter Name</span></span>|<span data-ttu-id="62cc0-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-339">Restriction Default</span></span>|<span data-ttu-id="62cc0-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-341">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-342">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-343">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-343">1</span></span>|  
|<span data-ttu-id="62cc0-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-344">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-346">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-346">2</span></span>|  
|<span data-ttu-id="62cc0-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-347">Table</span></span>|@Table|<span data-ttu-id="62cc0-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-348">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-349">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="62cc0-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="62cc0-350">AllColumns</span></span>  
  
|<span data-ttu-id="62cc0-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-351">Restriction Name</span></span>|<span data-ttu-id="62cc0-352">имени параметра</span><span class="sxs-lookup"><span data-stu-id="62cc0-352">Parameter Name</span></span>|<span data-ttu-id="62cc0-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="62cc0-353">Restriction Default</span></span>|<span data-ttu-id="62cc0-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="62cc0-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="62cc0-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="62cc0-355">Catalog</span></span>|@Catalog|<span data-ttu-id="62cc0-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="62cc0-356">TABLE_CATALOG</span></span>|<span data-ttu-id="62cc0-357">1</span><span class="sxs-lookup"><span data-stu-id="62cc0-357">1</span></span>|  
|<span data-ttu-id="62cc0-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="62cc0-358">Owner</span></span>|@Owner|<span data-ttu-id="62cc0-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="62cc0-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="62cc0-360">2</span><span class="sxs-lookup"><span data-stu-id="62cc0-360">2</span></span>|  
|<span data-ttu-id="62cc0-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="62cc0-361">Table</span></span>|@Table|<span data-ttu-id="62cc0-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-362">TABLE_NAME</span></span>|<span data-ttu-id="62cc0-363">3</span><span class="sxs-lookup"><span data-stu-id="62cc0-363">3</span></span>|  
|<span data-ttu-id="62cc0-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="62cc0-364">Column</span></span>|@Column|<span data-ttu-id="62cc0-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="62cc0-365">COLUMN_NAME</span></span>|<span data-ttu-id="62cc0-366">4</span><span class="sxs-lookup"><span data-stu-id="62cc0-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62cc0-367">См. также</span><span class="sxs-lookup"><span data-stu-id="62cc0-367">See also</span></span>

- [<span data-ttu-id="62cc0-368">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="62cc0-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
