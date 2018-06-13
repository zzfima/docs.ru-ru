---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c62f934561fa4a6c352ff84b8c1201461c42de39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357261"
---
# <a name="schema-restrictions"></a><span data-ttu-id="13b37-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="13b37-102">Schema Restrictions</span></span>
<span data-ttu-id="13b37-103">Вторым необязательным параметром метода **GetSchema** в противном случае возвращается ограничений, которые используются для ограничения объема сведений о схеме, и оно передается **GetSchema** метод как массив строк .</span><span class="sxs-lookup"><span data-stu-id="13b37-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="13b37-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="13b37-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="13b37-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13b37-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="13b37-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="13b37-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="13b37-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-107">Restriction Name</span></span>|<span data-ttu-id="13b37-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-108">Parameter Name</span></span>|<span data-ttu-id="13b37-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-109">Restriction Default</span></span>|<span data-ttu-id="13b37-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-111">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-112">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-113">1</span><span class="sxs-lookup"><span data-stu-id="13b37-113">1</span></span>|  
|<span data-ttu-id="13b37-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-114">Owner</span></span>|@Owner|<span data-ttu-id="13b37-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-116">2</span><span class="sxs-lookup"><span data-stu-id="13b37-116">2</span></span>|  
|<span data-ttu-id="13b37-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-117">Table</span></span>|@Name|<span data-ttu-id="13b37-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-118">TABLE_NAME</span></span>|<span data-ttu-id="13b37-119">3</span><span class="sxs-lookup"><span data-stu-id="13b37-119">3</span></span>|  
|<span data-ttu-id="13b37-120">TableType</span><span class="sxs-lookup"><span data-stu-id="13b37-120">TableType</span></span>|@TableType|<span data-ttu-id="13b37-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="13b37-121">TABLE_TYPE</span></span>|<span data-ttu-id="13b37-122">4</span><span class="sxs-lookup"><span data-stu-id="13b37-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="13b37-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="13b37-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="13b37-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="13b37-125">Например, чтобы ограничить таблицы, возвращаемые **GetSchema** только таблицами из схемы «Sales», присвойте второй элемент массива значение «Sales» перед передачей **GetSchema** метод.</span><span class="sxs-lookup"><span data-stu-id="13b37-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13b37-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="13b37-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="13b37-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="13b37-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="13b37-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="13b37-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13b37-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="13b37-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="13b37-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="13b37-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="13b37-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="13b37-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="13b37-132">Можно запросить управляемый поставщик .NET Framework для определения списка поддерживаемых ограничений, вызвав **GetSchema** метод с именем коллекции схем ограничений — «Ограничения».</span><span class="sxs-lookup"><span data-stu-id="13b37-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="13b37-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="13b37-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="13b37-134">Пример</span><span class="sxs-lookup"><span data-stu-id="13b37-134">Example</span></span>  
 <span data-ttu-id="13b37-135">Следующие примеры демонстрируют, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для SQL Server <xref:System.Data.SqlClient.SqlConnection> класса для извлечения сведений о всех таблиц, содержащихся в схеме **AdventureWorks**образца базы данных, а также для ограничения сведений возвращаются только таблицами из схемы «Sales»:</span><span class="sxs-lookup"><span data-stu-id="13b37-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="13b37-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="13b37-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="13b37-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13b37-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="13b37-138">Users</span><span class="sxs-lookup"><span data-stu-id="13b37-138">Users</span></span>  
  
|<span data-ttu-id="13b37-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-139">Restriction Name</span></span>|<span data-ttu-id="13b37-140">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-140">Parameter Name</span></span>|<span data-ttu-id="13b37-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-141">Restriction Default</span></span>|<span data-ttu-id="13b37-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="13b37-143">User_Name</span></span>|@Name|<span data-ttu-id="13b37-144">имя</span><span class="sxs-lookup"><span data-stu-id="13b37-144">name</span></span>|<span data-ttu-id="13b37-145">1</span><span class="sxs-lookup"><span data-stu-id="13b37-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="13b37-146">Databases</span><span class="sxs-lookup"><span data-stu-id="13b37-146">Databases</span></span>  
  
|<span data-ttu-id="13b37-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-147">Restriction Name</span></span>|<span data-ttu-id="13b37-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-148">Parameter Name</span></span>|<span data-ttu-id="13b37-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-149">Restriction Default</span></span>|<span data-ttu-id="13b37-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-151">name</span><span class="sxs-lookup"><span data-stu-id="13b37-151">Name</span></span>|@Name|<span data-ttu-id="13b37-152">name</span><span class="sxs-lookup"><span data-stu-id="13b37-152">Name</span></span>|<span data-ttu-id="13b37-153">1</span><span class="sxs-lookup"><span data-stu-id="13b37-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="13b37-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="13b37-154">Tables</span></span>  
  
|<span data-ttu-id="13b37-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-155">Restriction Name</span></span>|<span data-ttu-id="13b37-156">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-156">Parameter Name</span></span>|<span data-ttu-id="13b37-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-157">Restriction Default</span></span>|<span data-ttu-id="13b37-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-159">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-160">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-161">1</span><span class="sxs-lookup"><span data-stu-id="13b37-161">1</span></span>|  
|<span data-ttu-id="13b37-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-162">Owner</span></span>|@Owner|<span data-ttu-id="13b37-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-164">2</span><span class="sxs-lookup"><span data-stu-id="13b37-164">2</span></span>|  
|<span data-ttu-id="13b37-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-165">Table</span></span>|@Name|<span data-ttu-id="13b37-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-166">TABLE_NAME</span></span>|<span data-ttu-id="13b37-167">3</span><span class="sxs-lookup"><span data-stu-id="13b37-167">3</span></span>|  
|<span data-ttu-id="13b37-168">TableType</span><span class="sxs-lookup"><span data-stu-id="13b37-168">TableType</span></span>|@TableType|<span data-ttu-id="13b37-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="13b37-169">TABLE_TYPE</span></span>|<span data-ttu-id="13b37-170">4</span><span class="sxs-lookup"><span data-stu-id="13b37-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="13b37-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="13b37-171">Columns</span></span>  
  
|<span data-ttu-id="13b37-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-172">Restriction Name</span></span>|<span data-ttu-id="13b37-173">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-173">Parameter Name</span></span>|<span data-ttu-id="13b37-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-174">Restriction Default</span></span>|<span data-ttu-id="13b37-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-176">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-177">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-178">1</span><span class="sxs-lookup"><span data-stu-id="13b37-178">1</span></span>|  
|<span data-ttu-id="13b37-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-179">Owner</span></span>|@Owner|<span data-ttu-id="13b37-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-181">2</span><span class="sxs-lookup"><span data-stu-id="13b37-181">2</span></span>|  
|<span data-ttu-id="13b37-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-182">Table</span></span>|@Table|<span data-ttu-id="13b37-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-183">TABLE_NAME</span></span>|<span data-ttu-id="13b37-184">3</span><span class="sxs-lookup"><span data-stu-id="13b37-184">3</span></span>|  
|<span data-ttu-id="13b37-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="13b37-185">Column</span></span>|@Column|<span data-ttu-id="13b37-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-186">COLUMN_NAME</span></span>|<span data-ttu-id="13b37-187">4</span><span class="sxs-lookup"><span data-stu-id="13b37-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="13b37-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="13b37-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="13b37-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-189">Restriction Name</span></span>|<span data-ttu-id="13b37-190">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-190">Parameter Name</span></span>|<span data-ttu-id="13b37-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-191">Restriction Default</span></span>|<span data-ttu-id="13b37-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-193">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-194">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-195">1</span><span class="sxs-lookup"><span data-stu-id="13b37-195">1</span></span>|  
|<span data-ttu-id="13b37-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-196">Owner</span></span>|@Owner|<span data-ttu-id="13b37-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-198">2</span><span class="sxs-lookup"><span data-stu-id="13b37-198">2</span></span>|  
|<span data-ttu-id="13b37-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-199">Table</span></span>|@Table|<span data-ttu-id="13b37-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-200">TABLE_NAME</span></span>|<span data-ttu-id="13b37-201">3</span><span class="sxs-lookup"><span data-stu-id="13b37-201">3</span></span>|  
|<span data-ttu-id="13b37-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="13b37-202">Column</span></span>|@Column|<span data-ttu-id="13b37-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-203">COLUMN_NAME</span></span>|<span data-ttu-id="13b37-204">4</span><span class="sxs-lookup"><span data-stu-id="13b37-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="13b37-205">Представления</span><span class="sxs-lookup"><span data-stu-id="13b37-205">Views</span></span>  
  
|<span data-ttu-id="13b37-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-206">Restriction Name</span></span>|<span data-ttu-id="13b37-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-207">Parameter Name</span></span>|<span data-ttu-id="13b37-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-208">Restriction Default</span></span>|<span data-ttu-id="13b37-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-210">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-211">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-212">1</span><span class="sxs-lookup"><span data-stu-id="13b37-212">1</span></span>|  
|<span data-ttu-id="13b37-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-213">Owner</span></span>|@Owner|<span data-ttu-id="13b37-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-215">2</span><span class="sxs-lookup"><span data-stu-id="13b37-215">2</span></span>|  
|<span data-ttu-id="13b37-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-216">Table</span></span>|@Table|<span data-ttu-id="13b37-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-217">TABLE_NAME</span></span>|<span data-ttu-id="13b37-218">3</span><span class="sxs-lookup"><span data-stu-id="13b37-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="13b37-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="13b37-219">ViewColumns</span></span>  
  
|<span data-ttu-id="13b37-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-220">Restriction Name</span></span>|<span data-ttu-id="13b37-221">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-221">Parameter Name</span></span>|<span data-ttu-id="13b37-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-222">Restriction Default</span></span>|<span data-ttu-id="13b37-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-224">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-225">VIEW_CATALOG</span></span>|<span data-ttu-id="13b37-226">1</span><span class="sxs-lookup"><span data-stu-id="13b37-226">1</span></span>|  
|<span data-ttu-id="13b37-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-227">Owner</span></span>|@Owner|<span data-ttu-id="13b37-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="13b37-229">2</span><span class="sxs-lookup"><span data-stu-id="13b37-229">2</span></span>|  
|<span data-ttu-id="13b37-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-230">Table</span></span>|@Table|<span data-ttu-id="13b37-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-231">VIEW_NAME</span></span>|<span data-ttu-id="13b37-232">3</span><span class="sxs-lookup"><span data-stu-id="13b37-232">3</span></span>|  
|<span data-ttu-id="13b37-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="13b37-233">Column</span></span>|@Column|<span data-ttu-id="13b37-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-234">COLUMN_NAME</span></span>|<span data-ttu-id="13b37-235">4</span><span class="sxs-lookup"><span data-stu-id="13b37-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="13b37-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="13b37-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="13b37-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-237">Restriction Name</span></span>|<span data-ttu-id="13b37-238">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-238">Parameter Name</span></span>|<span data-ttu-id="13b37-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-239">Restriction Default</span></span>|<span data-ttu-id="13b37-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-241">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="13b37-243">1</span><span class="sxs-lookup"><span data-stu-id="13b37-243">1</span></span>|  
|<span data-ttu-id="13b37-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-244">Owner</span></span>|@Owner|<span data-ttu-id="13b37-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="13b37-246">2</span><span class="sxs-lookup"><span data-stu-id="13b37-246">2</span></span>|  
|<span data-ttu-id="13b37-247">name</span><span class="sxs-lookup"><span data-stu-id="13b37-247">Name</span></span>|@Name|<span data-ttu-id="13b37-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="13b37-249">3</span><span class="sxs-lookup"><span data-stu-id="13b37-249">3</span></span>|  
|<span data-ttu-id="13b37-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="13b37-250">Parameter</span></span>|@Parameter|<span data-ttu-id="13b37-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-251">PARAMETER_NAME</span></span>|<span data-ttu-id="13b37-252">4</span><span class="sxs-lookup"><span data-stu-id="13b37-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="13b37-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="13b37-253">Procedures</span></span>  
  
|<span data-ttu-id="13b37-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-254">Restriction Name</span></span>|<span data-ttu-id="13b37-255">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-255">Parameter Name</span></span>|<span data-ttu-id="13b37-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-256">Restriction Default</span></span>|<span data-ttu-id="13b37-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-258">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="13b37-260">1</span><span class="sxs-lookup"><span data-stu-id="13b37-260">1</span></span>|  
|<span data-ttu-id="13b37-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-261">Owner</span></span>|@Owner|<span data-ttu-id="13b37-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="13b37-263">2</span><span class="sxs-lookup"><span data-stu-id="13b37-263">2</span></span>|  
|<span data-ttu-id="13b37-264">name</span><span class="sxs-lookup"><span data-stu-id="13b37-264">Name</span></span>|@Name|<span data-ttu-id="13b37-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="13b37-266">3</span><span class="sxs-lookup"><span data-stu-id="13b37-266">3</span></span>|  
|<span data-ttu-id="13b37-267">Тип</span><span class="sxs-lookup"><span data-stu-id="13b37-267">Type</span></span>|@Type|<span data-ttu-id="13b37-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="13b37-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="13b37-269">4</span><span class="sxs-lookup"><span data-stu-id="13b37-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="13b37-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="13b37-270">IndexColumns</span></span>  
  
|<span data-ttu-id="13b37-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-271">Restriction Name</span></span>|<span data-ttu-id="13b37-272">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-272">Parameter Name</span></span>|<span data-ttu-id="13b37-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-273">Restriction Default</span></span>|<span data-ttu-id="13b37-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-275">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="13b37-276">db_name()</span></span>|<span data-ttu-id="13b37-277">1</span><span class="sxs-lookup"><span data-stu-id="13b37-277">1</span></span>|  
|<span data-ttu-id="13b37-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-278">Owner</span></span>|@Owner|<span data-ttu-id="13b37-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="13b37-279">user_name()</span></span>|<span data-ttu-id="13b37-280">2</span><span class="sxs-lookup"><span data-stu-id="13b37-280">2</span></span>|  
|<span data-ttu-id="13b37-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-281">Table</span></span>|@Table|<span data-ttu-id="13b37-282">o.name</span><span class="sxs-lookup"><span data-stu-id="13b37-282">o.name</span></span>|<span data-ttu-id="13b37-283">3</span><span class="sxs-lookup"><span data-stu-id="13b37-283">3</span></span>|  
|<span data-ttu-id="13b37-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="13b37-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="13b37-285">x.name</span><span class="sxs-lookup"><span data-stu-id="13b37-285">x.name</span></span>|<span data-ttu-id="13b37-286">4</span><span class="sxs-lookup"><span data-stu-id="13b37-286">4</span></span>|  
|<span data-ttu-id="13b37-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="13b37-287">Column</span></span>|@Column|<span data-ttu-id="13b37-288">c.name</span><span class="sxs-lookup"><span data-stu-id="13b37-288">c.name</span></span>|<span data-ttu-id="13b37-289">5</span><span class="sxs-lookup"><span data-stu-id="13b37-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="13b37-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="13b37-290">Indexes</span></span>  
  
|<span data-ttu-id="13b37-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-291">Restriction Name</span></span>|<span data-ttu-id="13b37-292">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-292">Parameter Name</span></span>|<span data-ttu-id="13b37-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-293">Restriction Default</span></span>|<span data-ttu-id="13b37-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-295">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="13b37-296">db_name()</span></span>|<span data-ttu-id="13b37-297">1</span><span class="sxs-lookup"><span data-stu-id="13b37-297">1</span></span>|  
|<span data-ttu-id="13b37-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-298">Owner</span></span>|@Owner|<span data-ttu-id="13b37-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="13b37-299">user_name()</span></span>|<span data-ttu-id="13b37-300">2</span><span class="sxs-lookup"><span data-stu-id="13b37-300">2</span></span>|  
|<span data-ttu-id="13b37-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-301">Table</span></span>|@Table|<span data-ttu-id="13b37-302">o.name</span><span class="sxs-lookup"><span data-stu-id="13b37-302">o.name</span></span>|<span data-ttu-id="13b37-303">3</span><span class="sxs-lookup"><span data-stu-id="13b37-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="13b37-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="13b37-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="13b37-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-305">Restriction Name</span></span>|<span data-ttu-id="13b37-306">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-306">Parameter Name</span></span>|<span data-ttu-id="13b37-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-307">Restriction Default</span></span>|<span data-ttu-id="13b37-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="13b37-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="13b37-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="13b37-310">assemblies.name</span></span>|<span data-ttu-id="13b37-311">1</span><span class="sxs-lookup"><span data-stu-id="13b37-311">1</span></span>|  
|<span data-ttu-id="13b37-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="13b37-312">udt_name</span></span>|@UDTName|<span data-ttu-id="13b37-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="13b37-313">types.assembly_class</span></span>|<span data-ttu-id="13b37-314">2</span><span class="sxs-lookup"><span data-stu-id="13b37-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="13b37-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="13b37-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="13b37-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-316">Restriction Name</span></span>|<span data-ttu-id="13b37-317">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-317">Parameter Name</span></span>|<span data-ttu-id="13b37-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-318">Restriction Default</span></span>|<span data-ttu-id="13b37-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-320">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="13b37-322">1</span><span class="sxs-lookup"><span data-stu-id="13b37-322">1</span></span>|  
|<span data-ttu-id="13b37-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-323">Owner</span></span>|@Owner|<span data-ttu-id="13b37-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="13b37-325">2</span><span class="sxs-lookup"><span data-stu-id="13b37-325">2</span></span>|  
|<span data-ttu-id="13b37-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-326">Table</span></span>|@Table|<span data-ttu-id="13b37-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-327">TABLE_NAME</span></span>|<span data-ttu-id="13b37-328">3</span><span class="sxs-lookup"><span data-stu-id="13b37-328">3</span></span>|  
|<span data-ttu-id="13b37-329">name</span><span class="sxs-lookup"><span data-stu-id="13b37-329">Name</span></span>|@Name|<span data-ttu-id="13b37-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="13b37-331">4</span><span class="sxs-lookup"><span data-stu-id="13b37-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="13b37-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="13b37-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="13b37-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="13b37-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="13b37-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="13b37-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="13b37-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13b37-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="13b37-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="13b37-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="13b37-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-337">Restriction Name</span></span>|<span data-ttu-id="13b37-338">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-338">Parameter Name</span></span>|<span data-ttu-id="13b37-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-339">Restriction Default</span></span>|<span data-ttu-id="13b37-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-341">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-342">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-343">1</span><span class="sxs-lookup"><span data-stu-id="13b37-343">1</span></span>|  
|<span data-ttu-id="13b37-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-344">Owner</span></span>|@Owner|<span data-ttu-id="13b37-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-346">2</span><span class="sxs-lookup"><span data-stu-id="13b37-346">2</span></span>|  
|<span data-ttu-id="13b37-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-347">Table</span></span>|@Table|<span data-ttu-id="13b37-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-348">TABLE_NAME</span></span>|<span data-ttu-id="13b37-349">3</span><span class="sxs-lookup"><span data-stu-id="13b37-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="13b37-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="13b37-350">AllColumns</span></span>  
  
|<span data-ttu-id="13b37-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-351">Restriction Name</span></span>|<span data-ttu-id="13b37-352">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="13b37-352">Parameter Name</span></span>|<span data-ttu-id="13b37-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="13b37-353">Restriction Default</span></span>|<span data-ttu-id="13b37-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="13b37-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="13b37-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="13b37-355">Catalog</span></span>|@Catalog|<span data-ttu-id="13b37-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="13b37-356">TABLE_CATALOG</span></span>|<span data-ttu-id="13b37-357">1</span><span class="sxs-lookup"><span data-stu-id="13b37-357">1</span></span>|  
|<span data-ttu-id="13b37-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="13b37-358">Owner</span></span>|@Owner|<span data-ttu-id="13b37-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="13b37-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="13b37-360">2</span><span class="sxs-lookup"><span data-stu-id="13b37-360">2</span></span>|  
|<span data-ttu-id="13b37-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="13b37-361">Table</span></span>|@Table|<span data-ttu-id="13b37-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-362">TABLE_NAME</span></span>|<span data-ttu-id="13b37-363">3</span><span class="sxs-lookup"><span data-stu-id="13b37-363">3</span></span>|  
|<span data-ttu-id="13b37-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="13b37-364">Column</span></span>|@Column|<span data-ttu-id="13b37-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="13b37-365">COLUMN_NAME</span></span>|<span data-ttu-id="13b37-366">4</span><span class="sxs-lookup"><span data-stu-id="13b37-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13b37-367">См. также</span><span class="sxs-lookup"><span data-stu-id="13b37-367">See Also</span></span>  
 [<span data-ttu-id="13b37-368">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="13b37-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
