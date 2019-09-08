---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: d0250e573dc24bfcad97a2f2606cb2e6c8e520da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782757"
---
# <a name="schema-restrictions"></a><span data-ttu-id="44cb6-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="44cb6-102">Schema Restrictions</span></span>
<span data-ttu-id="44cb6-103">Второй необязательный параметр метода **GetSchema** — это ограничения, которые используются для ограничения объема возвращаемых сведений о схеме и передаются в метод **GetSchema** в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="44cb6-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="44cb6-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="44cb6-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="44cb6-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="44cb6-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="44cb6-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="44cb6-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="44cb6-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-107">Restriction Name</span></span>|<span data-ttu-id="44cb6-108">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-108">Parameter Name</span></span>|<span data-ttu-id="44cb6-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-109">Restriction Default</span></span>|<span data-ttu-id="44cb6-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-111">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-112">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-113">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-113">1</span></span>|  
|<span data-ttu-id="44cb6-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-114">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-116">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-116">2</span></span>|  
|<span data-ttu-id="44cb6-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-117">Table</span></span>|@Name|<span data-ttu-id="44cb6-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-118">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-119">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-119">3</span></span>|  
|<span data-ttu-id="44cb6-120">TableType</span><span class="sxs-lookup"><span data-stu-id="44cb6-120">TableType</span></span>|@TableType|<span data-ttu-id="44cb6-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44cb6-121">TABLE_TYPE</span></span>|<span data-ttu-id="44cb6-122">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="44cb6-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="44cb6-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="44cb6-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="44cb6-125">Например, чтобы ограничить таблицы, возвращаемые **методом GetSchema** , только таблицами в схеме Sales, задайте для второго элемента массива значение Sales, прежде чем передать его в метод **GetSchema** .</span><span class="sxs-lookup"><span data-stu-id="44cb6-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44cb6-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="44cb6-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="44cb6-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="44cb6-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="44cb6-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="44cb6-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44cb6-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="44cb6-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="44cb6-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="44cb6-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="44cb6-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="44cb6-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="44cb6-132">Можно запросить управляемый поставщик .NET Framework, чтобы определить список поддерживаемых ограничений, вызвав метод **GetSchema** с именем коллекции схем ограничений, которая является "ограничениями".</span><span class="sxs-lookup"><span data-stu-id="44cb6-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="44cb6-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="44cb6-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="44cb6-134">Пример</span><span class="sxs-lookup"><span data-stu-id="44cb6-134">Example</span></span>  
 <span data-ttu-id="44cb6-135">В следующих примерах показано, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для класса SQL Server <xref:System.Data.SqlClient.SqlConnection> , чтобы получить сведения о схеме всех таблиц, содержащихся в образце базы данных **AdventureWorks** . и для ограничения сведений, возвращаемых только таблицам в схеме Sales:</span><span class="sxs-lookup"><span data-stu-id="44cb6-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="44cb6-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="44cb6-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="44cb6-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="44cb6-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="44cb6-138">Users</span><span class="sxs-lookup"><span data-stu-id="44cb6-138">Users</span></span>  
  
|<span data-ttu-id="44cb6-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-139">Restriction Name</span></span>|<span data-ttu-id="44cb6-140">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-140">Parameter Name</span></span>|<span data-ttu-id="44cb6-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-141">Restriction Default</span></span>|<span data-ttu-id="44cb6-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="44cb6-143">User_Name</span></span>|@Name|<span data-ttu-id="44cb6-144">имя</span><span class="sxs-lookup"><span data-stu-id="44cb6-144">name</span></span>|<span data-ttu-id="44cb6-145">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="44cb6-146">Базы данных</span><span class="sxs-lookup"><span data-stu-id="44cb6-146">Databases</span></span>  
  
|<span data-ttu-id="44cb6-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-147">Restriction Name</span></span>|<span data-ttu-id="44cb6-148">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-148">Parameter Name</span></span>|<span data-ttu-id="44cb6-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-149">Restriction Default</span></span>|<span data-ttu-id="44cb6-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-151">name</span><span class="sxs-lookup"><span data-stu-id="44cb6-151">Name</span></span>|@Name|<span data-ttu-id="44cb6-152">name</span><span class="sxs-lookup"><span data-stu-id="44cb6-152">Name</span></span>|<span data-ttu-id="44cb6-153">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="44cb6-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="44cb6-154">Tables</span></span>  
  
|<span data-ttu-id="44cb6-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-155">Restriction Name</span></span>|<span data-ttu-id="44cb6-156">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-156">Parameter Name</span></span>|<span data-ttu-id="44cb6-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-157">Restriction Default</span></span>|<span data-ttu-id="44cb6-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-159">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-160">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-161">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-161">1</span></span>|  
|<span data-ttu-id="44cb6-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-162">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-164">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-164">2</span></span>|  
|<span data-ttu-id="44cb6-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-165">Table</span></span>|@Name|<span data-ttu-id="44cb6-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-166">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-167">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-167">3</span></span>|  
|<span data-ttu-id="44cb6-168">TableType</span><span class="sxs-lookup"><span data-stu-id="44cb6-168">TableType</span></span>|@TableType|<span data-ttu-id="44cb6-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44cb6-169">TABLE_TYPE</span></span>|<span data-ttu-id="44cb6-170">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="44cb6-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="44cb6-171">Columns</span></span>  
  
|<span data-ttu-id="44cb6-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-172">Restriction Name</span></span>|<span data-ttu-id="44cb6-173">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-173">Parameter Name</span></span>|<span data-ttu-id="44cb6-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-174">Restriction Default</span></span>|<span data-ttu-id="44cb6-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-176">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-177">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-178">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-178">1</span></span>|  
|<span data-ttu-id="44cb6-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-179">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-181">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-181">2</span></span>|  
|<span data-ttu-id="44cb6-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-182">Table</span></span>|@Table|<span data-ttu-id="44cb6-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-183">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-184">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-184">3</span></span>|  
|<span data-ttu-id="44cb6-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="44cb6-185">Column</span></span>|@Column|<span data-ttu-id="44cb6-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-186">COLUMN_NAME</span></span>|<span data-ttu-id="44cb6-187">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="44cb6-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="44cb6-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="44cb6-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-189">Restriction Name</span></span>|<span data-ttu-id="44cb6-190">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-190">Parameter Name</span></span>|<span data-ttu-id="44cb6-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-191">Restriction Default</span></span>|<span data-ttu-id="44cb6-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-193">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-194">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-195">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-195">1</span></span>|  
|<span data-ttu-id="44cb6-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-196">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-198">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-198">2</span></span>|  
|<span data-ttu-id="44cb6-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-199">Table</span></span>|@Table|<span data-ttu-id="44cb6-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-200">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-201">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-201">3</span></span>|  
|<span data-ttu-id="44cb6-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="44cb6-202">Column</span></span>|@Column|<span data-ttu-id="44cb6-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-203">COLUMN_NAME</span></span>|<span data-ttu-id="44cb6-204">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="44cb6-205">Представления</span><span class="sxs-lookup"><span data-stu-id="44cb6-205">Views</span></span>  
  
|<span data-ttu-id="44cb6-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-206">Restriction Name</span></span>|<span data-ttu-id="44cb6-207">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-207">Parameter Name</span></span>|<span data-ttu-id="44cb6-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-208">Restriction Default</span></span>|<span data-ttu-id="44cb6-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-210">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-211">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-212">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-212">1</span></span>|  
|<span data-ttu-id="44cb6-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-213">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-215">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-215">2</span></span>|  
|<span data-ttu-id="44cb6-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-216">Table</span></span>|@Table|<span data-ttu-id="44cb6-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-217">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-218">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="44cb6-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="44cb6-219">ViewColumns</span></span>  
  
|<span data-ttu-id="44cb6-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-220">Restriction Name</span></span>|<span data-ttu-id="44cb6-221">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-221">Parameter Name</span></span>|<span data-ttu-id="44cb6-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-222">Restriction Default</span></span>|<span data-ttu-id="44cb6-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-224">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-225">VIEW_CATALOG</span></span>|<span data-ttu-id="44cb6-226">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-226">1</span></span>|  
|<span data-ttu-id="44cb6-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-227">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="44cb6-229">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-229">2</span></span>|  
|<span data-ttu-id="44cb6-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-230">Table</span></span>|@Table|<span data-ttu-id="44cb6-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-231">VIEW_NAME</span></span>|<span data-ttu-id="44cb6-232">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-232">3</span></span>|  
|<span data-ttu-id="44cb6-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="44cb6-233">Column</span></span>|@Column|<span data-ttu-id="44cb6-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-234">COLUMN_NAME</span></span>|<span data-ttu-id="44cb6-235">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="44cb6-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="44cb6-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="44cb6-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-237">Restriction Name</span></span>|<span data-ttu-id="44cb6-238">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-238">Parameter Name</span></span>|<span data-ttu-id="44cb6-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-239">Restriction Default</span></span>|<span data-ttu-id="44cb6-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-241">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="44cb6-243">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-243">1</span></span>|  
|<span data-ttu-id="44cb6-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-244">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="44cb6-246">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-246">2</span></span>|  
|<span data-ttu-id="44cb6-247">name</span><span class="sxs-lookup"><span data-stu-id="44cb6-247">Name</span></span>|@Name|<span data-ttu-id="44cb6-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="44cb6-249">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-249">3</span></span>|  
|<span data-ttu-id="44cb6-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="44cb6-250">Parameter</span></span>|@Parameter|<span data-ttu-id="44cb6-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-251">PARAMETER_NAME</span></span>|<span data-ttu-id="44cb6-252">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="44cb6-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="44cb6-253">Procedures</span></span>  
  
|<span data-ttu-id="44cb6-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-254">Restriction Name</span></span>|<span data-ttu-id="44cb6-255">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-255">Parameter Name</span></span>|<span data-ttu-id="44cb6-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-256">Restriction Default</span></span>|<span data-ttu-id="44cb6-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-258">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="44cb6-260">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-260">1</span></span>|  
|<span data-ttu-id="44cb6-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-261">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="44cb6-263">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-263">2</span></span>|  
|<span data-ttu-id="44cb6-264">name</span><span class="sxs-lookup"><span data-stu-id="44cb6-264">Name</span></span>|@Name|<span data-ttu-id="44cb6-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="44cb6-266">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-266">3</span></span>|  
|<span data-ttu-id="44cb6-267">Тип</span><span class="sxs-lookup"><span data-stu-id="44cb6-267">Type</span></span>|@Type|<span data-ttu-id="44cb6-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44cb6-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="44cb6-269">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="44cb6-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="44cb6-270">IndexColumns</span></span>  
  
|<span data-ttu-id="44cb6-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-271">Restriction Name</span></span>|<span data-ttu-id="44cb6-272">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-272">Parameter Name</span></span>|<span data-ttu-id="44cb6-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-273">Restriction Default</span></span>|<span data-ttu-id="44cb6-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-275">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="44cb6-276">db_name()</span></span>|<span data-ttu-id="44cb6-277">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-277">1</span></span>|  
|<span data-ttu-id="44cb6-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-278">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="44cb6-279">user_name()</span></span>|<span data-ttu-id="44cb6-280">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-280">2</span></span>|  
|<span data-ttu-id="44cb6-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-281">Table</span></span>|@Table|<span data-ttu-id="44cb6-282">o.name</span><span class="sxs-lookup"><span data-stu-id="44cb6-282">o.name</span></span>|<span data-ttu-id="44cb6-283">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-283">3</span></span>|  
|<span data-ttu-id="44cb6-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="44cb6-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="44cb6-285">x.name</span><span class="sxs-lookup"><span data-stu-id="44cb6-285">x.name</span></span>|<span data-ttu-id="44cb6-286">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-286">4</span></span>|  
|<span data-ttu-id="44cb6-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="44cb6-287">Column</span></span>|@Column|<span data-ttu-id="44cb6-288">c.name</span><span class="sxs-lookup"><span data-stu-id="44cb6-288">c.name</span></span>|<span data-ttu-id="44cb6-289">5</span><span class="sxs-lookup"><span data-stu-id="44cb6-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="44cb6-290">Индексы</span><span class="sxs-lookup"><span data-stu-id="44cb6-290">Indexes</span></span>  
  
|<span data-ttu-id="44cb6-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-291">Restriction Name</span></span>|<span data-ttu-id="44cb6-292">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-292">Parameter Name</span></span>|<span data-ttu-id="44cb6-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-293">Restriction Default</span></span>|<span data-ttu-id="44cb6-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-295">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="44cb6-296">db_name()</span></span>|<span data-ttu-id="44cb6-297">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-297">1</span></span>|  
|<span data-ttu-id="44cb6-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-298">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="44cb6-299">user_name()</span></span>|<span data-ttu-id="44cb6-300">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-300">2</span></span>|  
|<span data-ttu-id="44cb6-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-301">Table</span></span>|@Table|<span data-ttu-id="44cb6-302">o.name</span><span class="sxs-lookup"><span data-stu-id="44cb6-302">o.name</span></span>|<span data-ttu-id="44cb6-303">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="44cb6-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="44cb6-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="44cb6-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-305">Restriction Name</span></span>|<span data-ttu-id="44cb6-306">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-306">Parameter Name</span></span>|<span data-ttu-id="44cb6-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-307">Restriction Default</span></span>|<span data-ttu-id="44cb6-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="44cb6-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="44cb6-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="44cb6-310">assemblies.name</span></span>|<span data-ttu-id="44cb6-311">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-311">1</span></span>|  
|<span data-ttu-id="44cb6-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="44cb6-312">udt_name</span></span>|@UDTName|<span data-ttu-id="44cb6-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="44cb6-313">types.assembly_class</span></span>|<span data-ttu-id="44cb6-314">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="44cb6-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="44cb6-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="44cb6-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-316">Restriction Name</span></span>|<span data-ttu-id="44cb6-317">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-317">Parameter Name</span></span>|<span data-ttu-id="44cb6-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-318">Restriction Default</span></span>|<span data-ttu-id="44cb6-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-320">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="44cb6-322">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-322">1</span></span>|  
|<span data-ttu-id="44cb6-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-323">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="44cb6-325">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-325">2</span></span>|  
|<span data-ttu-id="44cb6-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-326">Table</span></span>|@Table|<span data-ttu-id="44cb6-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-327">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-328">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-328">3</span></span>|  
|<span data-ttu-id="44cb6-329">name</span><span class="sxs-lookup"><span data-stu-id="44cb6-329">Name</span></span>|@Name|<span data-ttu-id="44cb6-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="44cb6-331">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="44cb6-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="44cb6-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="44cb6-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="44cb6-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="44cb6-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="44cb6-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="44cb6-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="44cb6-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="44cb6-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="44cb6-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="44cb6-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-337">Restriction Name</span></span>|<span data-ttu-id="44cb6-338">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-338">Parameter Name</span></span>|<span data-ttu-id="44cb6-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-339">Restriction Default</span></span>|<span data-ttu-id="44cb6-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-341">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-342">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-343">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-343">1</span></span>|  
|<span data-ttu-id="44cb6-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-344">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-346">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-346">2</span></span>|  
|<span data-ttu-id="44cb6-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-347">Table</span></span>|@Table|<span data-ttu-id="44cb6-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-348">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-349">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="44cb6-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="44cb6-350">AllColumns</span></span>  
  
|<span data-ttu-id="44cb6-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-351">Restriction Name</span></span>|<span data-ttu-id="44cb6-352">имени параметра</span><span class="sxs-lookup"><span data-stu-id="44cb6-352">Parameter Name</span></span>|<span data-ttu-id="44cb6-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44cb6-353">Restriction Default</span></span>|<span data-ttu-id="44cb6-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="44cb6-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="44cb6-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="44cb6-355">Catalog</span></span>|@Catalog|<span data-ttu-id="44cb6-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44cb6-356">TABLE_CATALOG</span></span>|<span data-ttu-id="44cb6-357">1</span><span class="sxs-lookup"><span data-stu-id="44cb6-357">1</span></span>|  
|<span data-ttu-id="44cb6-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="44cb6-358">Owner</span></span>|@Owner|<span data-ttu-id="44cb6-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44cb6-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="44cb6-360">2</span><span class="sxs-lookup"><span data-stu-id="44cb6-360">2</span></span>|  
|<span data-ttu-id="44cb6-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="44cb6-361">Table</span></span>|@Table|<span data-ttu-id="44cb6-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-362">TABLE_NAME</span></span>|<span data-ttu-id="44cb6-363">3</span><span class="sxs-lookup"><span data-stu-id="44cb6-363">3</span></span>|  
|<span data-ttu-id="44cb6-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="44cb6-364">Column</span></span>|@Column|<span data-ttu-id="44cb6-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44cb6-365">COLUMN_NAME</span></span>|<span data-ttu-id="44cb6-366">4</span><span class="sxs-lookup"><span data-stu-id="44cb6-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44cb6-367">См. также</span><span class="sxs-lookup"><span data-stu-id="44cb6-367">See also</span></span>

- [<span data-ttu-id="44cb6-368">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="44cb6-368">ADO.NET Overview</span></span>](ado-net-overview.md)
