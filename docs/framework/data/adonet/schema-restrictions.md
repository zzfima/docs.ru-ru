---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079712"
---
# <a name="schema-restrictions"></a><span data-ttu-id="810c8-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="810c8-102">Schema Restrictions</span></span>
<span data-ttu-id="810c8-103">Вторым необязательным параметром метода **GetSchema** метод является возвращаемых ограничения, которые используются для ограничения объема данных схемы, и он передается **GetSchema** метод как массив строк .</span><span class="sxs-lookup"><span data-stu-id="810c8-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="810c8-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="810c8-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="810c8-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="810c8-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="810c8-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="810c8-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="810c8-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-107">Restriction Name</span></span>|<span data-ttu-id="810c8-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-108">Parameter Name</span></span>|<span data-ttu-id="810c8-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-109">Restriction Default</span></span>|<span data-ttu-id="810c8-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-111">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-112">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-113">1</span><span class="sxs-lookup"><span data-stu-id="810c8-113">1</span></span>|  
|<span data-ttu-id="810c8-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-114">Owner</span></span>|@Owner|<span data-ttu-id="810c8-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-116">2</span><span class="sxs-lookup"><span data-stu-id="810c8-116">2</span></span>|  
|<span data-ttu-id="810c8-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-117">Table</span></span>|@Name|<span data-ttu-id="810c8-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-118">TABLE_NAME</span></span>|<span data-ttu-id="810c8-119">3</span><span class="sxs-lookup"><span data-stu-id="810c8-119">3</span></span>|  
|<span data-ttu-id="810c8-120">TableType</span><span class="sxs-lookup"><span data-stu-id="810c8-120">TableType</span></span>|@TableType|<span data-ttu-id="810c8-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="810c8-121">TABLE_TYPE</span></span>|<span data-ttu-id="810c8-122">4</span><span class="sxs-lookup"><span data-stu-id="810c8-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="810c8-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="810c8-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="810c8-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="810c8-125">Например, чтобы ограничить таблицы, возвращаемые **GetSchema** метод только таблицами из схемы «Sales», присвойте второму элементу массива значение «Sales» перед передачей в **GetSchema** метод.</span><span class="sxs-lookup"><span data-stu-id="810c8-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="810c8-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="810c8-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="810c8-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="810c8-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="810c8-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="810c8-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="810c8-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="810c8-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="810c8-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="810c8-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="810c8-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="810c8-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="810c8-132">Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых ограничений, вызвав **GetSchema** метод с именем коллекции схем ограничений, который является «Ограничения».</span><span class="sxs-lookup"><span data-stu-id="810c8-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="810c8-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="810c8-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="810c8-134">Пример</span><span class="sxs-lookup"><span data-stu-id="810c8-134">Example</span></span>  
 <span data-ttu-id="810c8-135">Следующие примеры демонстрируют, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> класса для извлечения сведений схем обо всех таблицах, содержащихся в **AdventureWorks**образца базы данных, и для ограничения сведений, возвращается только таблицами из схемы «Sales»:</span><span class="sxs-lookup"><span data-stu-id="810c8-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="810c8-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="810c8-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="810c8-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="810c8-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="810c8-138">Users</span><span class="sxs-lookup"><span data-stu-id="810c8-138">Users</span></span>  
  
|<span data-ttu-id="810c8-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-139">Restriction Name</span></span>|<span data-ttu-id="810c8-140">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-140">Parameter Name</span></span>|<span data-ttu-id="810c8-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-141">Restriction Default</span></span>|<span data-ttu-id="810c8-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="810c8-143">User_Name</span></span>|@Name|<span data-ttu-id="810c8-144">имя</span><span class="sxs-lookup"><span data-stu-id="810c8-144">name</span></span>|<span data-ttu-id="810c8-145">1</span><span class="sxs-lookup"><span data-stu-id="810c8-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="810c8-146">Databases</span><span class="sxs-lookup"><span data-stu-id="810c8-146">Databases</span></span>  
  
|<span data-ttu-id="810c8-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-147">Restriction Name</span></span>|<span data-ttu-id="810c8-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-148">Parameter Name</span></span>|<span data-ttu-id="810c8-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-149">Restriction Default</span></span>|<span data-ttu-id="810c8-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-151">name</span><span class="sxs-lookup"><span data-stu-id="810c8-151">Name</span></span>|@Name|<span data-ttu-id="810c8-152">name</span><span class="sxs-lookup"><span data-stu-id="810c8-152">Name</span></span>|<span data-ttu-id="810c8-153">1</span><span class="sxs-lookup"><span data-stu-id="810c8-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="810c8-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="810c8-154">Tables</span></span>  
  
|<span data-ttu-id="810c8-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-155">Restriction Name</span></span>|<span data-ttu-id="810c8-156">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-156">Parameter Name</span></span>|<span data-ttu-id="810c8-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-157">Restriction Default</span></span>|<span data-ttu-id="810c8-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-159">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-160">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-161">1</span><span class="sxs-lookup"><span data-stu-id="810c8-161">1</span></span>|  
|<span data-ttu-id="810c8-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-162">Owner</span></span>|@Owner|<span data-ttu-id="810c8-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-164">2</span><span class="sxs-lookup"><span data-stu-id="810c8-164">2</span></span>|  
|<span data-ttu-id="810c8-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-165">Table</span></span>|@Name|<span data-ttu-id="810c8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-166">TABLE_NAME</span></span>|<span data-ttu-id="810c8-167">3</span><span class="sxs-lookup"><span data-stu-id="810c8-167">3</span></span>|  
|<span data-ttu-id="810c8-168">TableType</span><span class="sxs-lookup"><span data-stu-id="810c8-168">TableType</span></span>|@TableType|<span data-ttu-id="810c8-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="810c8-169">TABLE_TYPE</span></span>|<span data-ttu-id="810c8-170">4</span><span class="sxs-lookup"><span data-stu-id="810c8-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="810c8-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="810c8-171">Columns</span></span>  
  
|<span data-ttu-id="810c8-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-172">Restriction Name</span></span>|<span data-ttu-id="810c8-173">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-173">Parameter Name</span></span>|<span data-ttu-id="810c8-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-174">Restriction Default</span></span>|<span data-ttu-id="810c8-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-176">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-177">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-178">1</span><span class="sxs-lookup"><span data-stu-id="810c8-178">1</span></span>|  
|<span data-ttu-id="810c8-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-179">Owner</span></span>|@Owner|<span data-ttu-id="810c8-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-181">2</span><span class="sxs-lookup"><span data-stu-id="810c8-181">2</span></span>|  
|<span data-ttu-id="810c8-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-182">Table</span></span>|@Table|<span data-ttu-id="810c8-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-183">TABLE_NAME</span></span>|<span data-ttu-id="810c8-184">3</span><span class="sxs-lookup"><span data-stu-id="810c8-184">3</span></span>|  
|<span data-ttu-id="810c8-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="810c8-185">Column</span></span>|@Column|<span data-ttu-id="810c8-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-186">COLUMN_NAME</span></span>|<span data-ttu-id="810c8-187">4</span><span class="sxs-lookup"><span data-stu-id="810c8-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="810c8-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="810c8-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="810c8-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-189">Restriction Name</span></span>|<span data-ttu-id="810c8-190">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-190">Parameter Name</span></span>|<span data-ttu-id="810c8-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-191">Restriction Default</span></span>|<span data-ttu-id="810c8-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-193">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-194">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-195">1</span><span class="sxs-lookup"><span data-stu-id="810c8-195">1</span></span>|  
|<span data-ttu-id="810c8-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-196">Owner</span></span>|@Owner|<span data-ttu-id="810c8-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-198">2</span><span class="sxs-lookup"><span data-stu-id="810c8-198">2</span></span>|  
|<span data-ttu-id="810c8-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-199">Table</span></span>|@Table|<span data-ttu-id="810c8-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-200">TABLE_NAME</span></span>|<span data-ttu-id="810c8-201">3</span><span class="sxs-lookup"><span data-stu-id="810c8-201">3</span></span>|  
|<span data-ttu-id="810c8-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="810c8-202">Column</span></span>|@Column|<span data-ttu-id="810c8-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-203">COLUMN_NAME</span></span>|<span data-ttu-id="810c8-204">4</span><span class="sxs-lookup"><span data-stu-id="810c8-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="810c8-205">Представления</span><span class="sxs-lookup"><span data-stu-id="810c8-205">Views</span></span>  
  
|<span data-ttu-id="810c8-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-206">Restriction Name</span></span>|<span data-ttu-id="810c8-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-207">Parameter Name</span></span>|<span data-ttu-id="810c8-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-208">Restriction Default</span></span>|<span data-ttu-id="810c8-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-210">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-211">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-212">1</span><span class="sxs-lookup"><span data-stu-id="810c8-212">1</span></span>|  
|<span data-ttu-id="810c8-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-213">Owner</span></span>|@Owner|<span data-ttu-id="810c8-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-215">2</span><span class="sxs-lookup"><span data-stu-id="810c8-215">2</span></span>|  
|<span data-ttu-id="810c8-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-216">Table</span></span>|@Table|<span data-ttu-id="810c8-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-217">TABLE_NAME</span></span>|<span data-ttu-id="810c8-218">3</span><span class="sxs-lookup"><span data-stu-id="810c8-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="810c8-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="810c8-219">ViewColumns</span></span>  
  
|<span data-ttu-id="810c8-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-220">Restriction Name</span></span>|<span data-ttu-id="810c8-221">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-221">Parameter Name</span></span>|<span data-ttu-id="810c8-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-222">Restriction Default</span></span>|<span data-ttu-id="810c8-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-224">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-225">VIEW_CATALOG</span></span>|<span data-ttu-id="810c8-226">1</span><span class="sxs-lookup"><span data-stu-id="810c8-226">1</span></span>|  
|<span data-ttu-id="810c8-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-227">Owner</span></span>|@Owner|<span data-ttu-id="810c8-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="810c8-229">2</span><span class="sxs-lookup"><span data-stu-id="810c8-229">2</span></span>|  
|<span data-ttu-id="810c8-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-230">Table</span></span>|@Table|<span data-ttu-id="810c8-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-231">VIEW_NAME</span></span>|<span data-ttu-id="810c8-232">3</span><span class="sxs-lookup"><span data-stu-id="810c8-232">3</span></span>|  
|<span data-ttu-id="810c8-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="810c8-233">Column</span></span>|@Column|<span data-ttu-id="810c8-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-234">COLUMN_NAME</span></span>|<span data-ttu-id="810c8-235">4</span><span class="sxs-lookup"><span data-stu-id="810c8-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="810c8-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="810c8-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="810c8-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-237">Restriction Name</span></span>|<span data-ttu-id="810c8-238">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-238">Parameter Name</span></span>|<span data-ttu-id="810c8-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-239">Restriction Default</span></span>|<span data-ttu-id="810c8-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-241">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="810c8-243">1</span><span class="sxs-lookup"><span data-stu-id="810c8-243">1</span></span>|  
|<span data-ttu-id="810c8-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-244">Owner</span></span>|@Owner|<span data-ttu-id="810c8-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="810c8-246">2</span><span class="sxs-lookup"><span data-stu-id="810c8-246">2</span></span>|  
|<span data-ttu-id="810c8-247">name</span><span class="sxs-lookup"><span data-stu-id="810c8-247">Name</span></span>|@Name|<span data-ttu-id="810c8-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="810c8-249">3</span><span class="sxs-lookup"><span data-stu-id="810c8-249">3</span></span>|  
|<span data-ttu-id="810c8-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="810c8-250">Parameter</span></span>|@Parameter|<span data-ttu-id="810c8-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-251">PARAMETER_NAME</span></span>|<span data-ttu-id="810c8-252">4</span><span class="sxs-lookup"><span data-stu-id="810c8-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="810c8-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="810c8-253">Procedures</span></span>  
  
|<span data-ttu-id="810c8-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-254">Restriction Name</span></span>|<span data-ttu-id="810c8-255">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-255">Parameter Name</span></span>|<span data-ttu-id="810c8-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-256">Restriction Default</span></span>|<span data-ttu-id="810c8-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-258">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="810c8-260">1</span><span class="sxs-lookup"><span data-stu-id="810c8-260">1</span></span>|  
|<span data-ttu-id="810c8-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-261">Owner</span></span>|@Owner|<span data-ttu-id="810c8-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="810c8-263">2</span><span class="sxs-lookup"><span data-stu-id="810c8-263">2</span></span>|  
|<span data-ttu-id="810c8-264">name</span><span class="sxs-lookup"><span data-stu-id="810c8-264">Name</span></span>|@Name|<span data-ttu-id="810c8-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="810c8-266">3</span><span class="sxs-lookup"><span data-stu-id="810c8-266">3</span></span>|  
|<span data-ttu-id="810c8-267">Тип</span><span class="sxs-lookup"><span data-stu-id="810c8-267">Type</span></span>|@Type|<span data-ttu-id="810c8-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="810c8-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="810c8-269">4</span><span class="sxs-lookup"><span data-stu-id="810c8-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="810c8-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="810c8-270">IndexColumns</span></span>  
  
|<span data-ttu-id="810c8-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-271">Restriction Name</span></span>|<span data-ttu-id="810c8-272">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-272">Parameter Name</span></span>|<span data-ttu-id="810c8-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-273">Restriction Default</span></span>|<span data-ttu-id="810c8-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-275">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="810c8-276">db_name()</span></span>|<span data-ttu-id="810c8-277">1</span><span class="sxs-lookup"><span data-stu-id="810c8-277">1</span></span>|  
|<span data-ttu-id="810c8-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-278">Owner</span></span>|@Owner|<span data-ttu-id="810c8-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="810c8-279">user_name()</span></span>|<span data-ttu-id="810c8-280">2</span><span class="sxs-lookup"><span data-stu-id="810c8-280">2</span></span>|  
|<span data-ttu-id="810c8-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-281">Table</span></span>|@Table|<span data-ttu-id="810c8-282">o.name</span><span class="sxs-lookup"><span data-stu-id="810c8-282">o.name</span></span>|<span data-ttu-id="810c8-283">3</span><span class="sxs-lookup"><span data-stu-id="810c8-283">3</span></span>|  
|<span data-ttu-id="810c8-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="810c8-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="810c8-285">x.name</span><span class="sxs-lookup"><span data-stu-id="810c8-285">x.name</span></span>|<span data-ttu-id="810c8-286">4</span><span class="sxs-lookup"><span data-stu-id="810c8-286">4</span></span>|  
|<span data-ttu-id="810c8-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="810c8-287">Column</span></span>|@Column|<span data-ttu-id="810c8-288">c.name</span><span class="sxs-lookup"><span data-stu-id="810c8-288">c.name</span></span>|<span data-ttu-id="810c8-289">5</span><span class="sxs-lookup"><span data-stu-id="810c8-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="810c8-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="810c8-290">Indexes</span></span>  
  
|<span data-ttu-id="810c8-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-291">Restriction Name</span></span>|<span data-ttu-id="810c8-292">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-292">Parameter Name</span></span>|<span data-ttu-id="810c8-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-293">Restriction Default</span></span>|<span data-ttu-id="810c8-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-295">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="810c8-296">db_name()</span></span>|<span data-ttu-id="810c8-297">1</span><span class="sxs-lookup"><span data-stu-id="810c8-297">1</span></span>|  
|<span data-ttu-id="810c8-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-298">Owner</span></span>|@Owner|<span data-ttu-id="810c8-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="810c8-299">user_name()</span></span>|<span data-ttu-id="810c8-300">2</span><span class="sxs-lookup"><span data-stu-id="810c8-300">2</span></span>|  
|<span data-ttu-id="810c8-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-301">Table</span></span>|@Table|<span data-ttu-id="810c8-302">o.name</span><span class="sxs-lookup"><span data-stu-id="810c8-302">o.name</span></span>|<span data-ttu-id="810c8-303">3</span><span class="sxs-lookup"><span data-stu-id="810c8-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="810c8-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="810c8-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="810c8-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-305">Restriction Name</span></span>|<span data-ttu-id="810c8-306">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-306">Parameter Name</span></span>|<span data-ttu-id="810c8-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-307">Restriction Default</span></span>|<span data-ttu-id="810c8-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="810c8-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="810c8-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="810c8-310">assemblies.name</span></span>|<span data-ttu-id="810c8-311">1</span><span class="sxs-lookup"><span data-stu-id="810c8-311">1</span></span>|  
|<span data-ttu-id="810c8-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="810c8-312">udt_name</span></span>|@UDTName|<span data-ttu-id="810c8-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="810c8-313">types.assembly_class</span></span>|<span data-ttu-id="810c8-314">2</span><span class="sxs-lookup"><span data-stu-id="810c8-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="810c8-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="810c8-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="810c8-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-316">Restriction Name</span></span>|<span data-ttu-id="810c8-317">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-317">Parameter Name</span></span>|<span data-ttu-id="810c8-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-318">Restriction Default</span></span>|<span data-ttu-id="810c8-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-320">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="810c8-322">1</span><span class="sxs-lookup"><span data-stu-id="810c8-322">1</span></span>|  
|<span data-ttu-id="810c8-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-323">Owner</span></span>|@Owner|<span data-ttu-id="810c8-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="810c8-325">2</span><span class="sxs-lookup"><span data-stu-id="810c8-325">2</span></span>|  
|<span data-ttu-id="810c8-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-326">Table</span></span>|@Table|<span data-ttu-id="810c8-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-327">TABLE_NAME</span></span>|<span data-ttu-id="810c8-328">3</span><span class="sxs-lookup"><span data-stu-id="810c8-328">3</span></span>|  
|<span data-ttu-id="810c8-329">name</span><span class="sxs-lookup"><span data-stu-id="810c8-329">Name</span></span>|@Name|<span data-ttu-id="810c8-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="810c8-331">4</span><span class="sxs-lookup"><span data-stu-id="810c8-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="810c8-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="810c8-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="810c8-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="810c8-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="810c8-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="810c8-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="810c8-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="810c8-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="810c8-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="810c8-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="810c8-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-337">Restriction Name</span></span>|<span data-ttu-id="810c8-338">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-338">Parameter Name</span></span>|<span data-ttu-id="810c8-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-339">Restriction Default</span></span>|<span data-ttu-id="810c8-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-341">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-342">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-343">1</span><span class="sxs-lookup"><span data-stu-id="810c8-343">1</span></span>|  
|<span data-ttu-id="810c8-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-344">Owner</span></span>|@Owner|<span data-ttu-id="810c8-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-346">2</span><span class="sxs-lookup"><span data-stu-id="810c8-346">2</span></span>|  
|<span data-ttu-id="810c8-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-347">Table</span></span>|@Table|<span data-ttu-id="810c8-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-348">TABLE_NAME</span></span>|<span data-ttu-id="810c8-349">3</span><span class="sxs-lookup"><span data-stu-id="810c8-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="810c8-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="810c8-350">AllColumns</span></span>  
  
|<span data-ttu-id="810c8-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-351">Restriction Name</span></span>|<span data-ttu-id="810c8-352">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="810c8-352">Parameter Name</span></span>|<span data-ttu-id="810c8-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c8-353">Restriction Default</span></span>|<span data-ttu-id="810c8-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="810c8-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="810c8-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="810c8-355">Catalog</span></span>|@Catalog|<span data-ttu-id="810c8-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="810c8-356">TABLE_CATALOG</span></span>|<span data-ttu-id="810c8-357">1</span><span class="sxs-lookup"><span data-stu-id="810c8-357">1</span></span>|  
|<span data-ttu-id="810c8-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="810c8-358">Owner</span></span>|@Owner|<span data-ttu-id="810c8-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="810c8-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="810c8-360">2</span><span class="sxs-lookup"><span data-stu-id="810c8-360">2</span></span>|  
|<span data-ttu-id="810c8-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="810c8-361">Table</span></span>|@Table|<span data-ttu-id="810c8-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-362">TABLE_NAME</span></span>|<span data-ttu-id="810c8-363">3</span><span class="sxs-lookup"><span data-stu-id="810c8-363">3</span></span>|  
|<span data-ttu-id="810c8-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="810c8-364">Column</span></span>|@Column|<span data-ttu-id="810c8-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="810c8-365">COLUMN_NAME</span></span>|<span data-ttu-id="810c8-366">4</span><span class="sxs-lookup"><span data-stu-id="810c8-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="810c8-367">См. также</span><span class="sxs-lookup"><span data-stu-id="810c8-367">See Also</span></span>  
 [<span data-ttu-id="810c8-368">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="810c8-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
