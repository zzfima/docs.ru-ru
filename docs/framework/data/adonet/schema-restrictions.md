---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149015"
---
# <a name="schema-restrictions"></a><span data-ttu-id="4e28b-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="4e28b-102">Schema Restrictions</span></span>
<span data-ttu-id="4e28b-103">Вторым дополнительным параметром **метода GetSchema** являются ограничения, которые используются для ограничения количества возвращенной информации о схеме, и она передается методу **GetSchema** в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="4e28b-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="4e28b-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="4e28b-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="4e28b-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e28b-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="4e28b-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="4e28b-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="4e28b-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-107">Restriction Name</span></span>|<span data-ttu-id="4e28b-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-108">Parameter Name</span></span>|<span data-ttu-id="4e28b-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-109">Restriction Default</span></span>|<span data-ttu-id="4e28b-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-111">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-111">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-112">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-113">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-113">1</span></span>|  
|<span data-ttu-id="4e28b-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-114">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-116">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-116">2</span></span>|  
|<span data-ttu-id="4e28b-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-117">Table</span></span>|@Name|<span data-ttu-id="4e28b-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-118">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-119">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-119">3</span></span>|  
|<span data-ttu-id="4e28b-120">TableType</span><span class="sxs-lookup"><span data-stu-id="4e28b-120">TableType</span></span>|@TableType|<span data-ttu-id="4e28b-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4e28b-121">TABLE_TYPE</span></span>|<span data-ttu-id="4e28b-122">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="4e28b-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="4e28b-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="4e28b-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="4e28b-125">Например, чтобы ограничить таблицы, возвращенные методом **GetSchema,** только теми таблицами в схеме "Продажи", установите второй элемент массива в "Продажи", прежде чем передать его методу **GetSchema.**</span><span class="sxs-lookup"><span data-stu-id="4e28b-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e28b-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="4e28b-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="4e28b-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="4e28b-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="4e28b-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="4e28b-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e28b-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="4e28b-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="4e28b-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="4e28b-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="4e28b-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="4e28b-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="4e28b-132">Вы можете задать запрос управляемому провайдеру .NET Framework для определения списка поддерживаемых ограничений, позвонив в метод **GetSchema** с названием коллекции схем ый схемы ограничений, которая является "Ограничения".</span><span class="sxs-lookup"><span data-stu-id="4e28b-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="4e28b-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="4e28b-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4e28b-134">Пример</span><span class="sxs-lookup"><span data-stu-id="4e28b-134">Example</span></span>  
 <span data-ttu-id="4e28b-135">Следующие примеры демонстрируют, <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> как использовать метод поставщика рамочных <xref:System.Data.SqlClient.SqlConnection> данных .NET для класса S'L Server для получения информации о схемах обо всех таблицах, содержащихся в базе данных **образцов AdventureWorks,** и ограничить доступ информации только в те таблицы в схеме "Продажи":</span><span class="sxs-lookup"><span data-stu-id="4e28b-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="4e28b-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e28b-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="4e28b-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e28b-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="4e28b-138">Пользователи</span><span class="sxs-lookup"><span data-stu-id="4e28b-138">Users</span></span>  
  
|<span data-ttu-id="4e28b-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-139">Restriction Name</span></span>|<span data-ttu-id="4e28b-140">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-140">Parameter Name</span></span>|<span data-ttu-id="4e28b-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-141">Restriction Default</span></span>|<span data-ttu-id="4e28b-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="4e28b-143">User_Name</span></span>|@Name|<span data-ttu-id="4e28b-144">name</span><span class="sxs-lookup"><span data-stu-id="4e28b-144">name</span></span>|<span data-ttu-id="4e28b-145">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="4e28b-146">Базы данных</span><span class="sxs-lookup"><span data-stu-id="4e28b-146">Databases</span></span>  
  
|<span data-ttu-id="4e28b-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-147">Restriction Name</span></span>|<span data-ttu-id="4e28b-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-148">Parameter Name</span></span>|<span data-ttu-id="4e28b-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-149">Restriction Default</span></span>|<span data-ttu-id="4e28b-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-151">Имя</span><span class="sxs-lookup"><span data-stu-id="4e28b-151">Name</span></span>|@Name|<span data-ttu-id="4e28b-152">Имя</span><span class="sxs-lookup"><span data-stu-id="4e28b-152">Name</span></span>|<span data-ttu-id="4e28b-153">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="4e28b-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="4e28b-154">Tables</span></span>  
  
|<span data-ttu-id="4e28b-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-155">Restriction Name</span></span>|<span data-ttu-id="4e28b-156">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-156">Parameter Name</span></span>|<span data-ttu-id="4e28b-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-157">Restriction Default</span></span>|<span data-ttu-id="4e28b-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-159">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-159">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-160">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-161">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-161">1</span></span>|  
|<span data-ttu-id="4e28b-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-162">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-164">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-164">2</span></span>|  
|<span data-ttu-id="4e28b-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-165">Table</span></span>|@Name|<span data-ttu-id="4e28b-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-166">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-167">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-167">3</span></span>|  
|<span data-ttu-id="4e28b-168">TableType</span><span class="sxs-lookup"><span data-stu-id="4e28b-168">TableType</span></span>|@TableType|<span data-ttu-id="4e28b-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4e28b-169">TABLE_TYPE</span></span>|<span data-ttu-id="4e28b-170">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4e28b-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="4e28b-171">Columns</span></span>  
  
|<span data-ttu-id="4e28b-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-172">Restriction Name</span></span>|<span data-ttu-id="4e28b-173">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-173">Parameter Name</span></span>|<span data-ttu-id="4e28b-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-174">Restriction Default</span></span>|<span data-ttu-id="4e28b-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-176">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-176">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-177">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-178">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-178">1</span></span>|  
|<span data-ttu-id="4e28b-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-179">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-181">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-181">2</span></span>|  
|<span data-ttu-id="4e28b-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-182">Table</span></span>|@Table|<span data-ttu-id="4e28b-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-183">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-184">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-184">3</span></span>|  
|<span data-ttu-id="4e28b-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="4e28b-185">Column</span></span>|@Column|<span data-ttu-id="4e28b-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-186">COLUMN_NAME</span></span>|<span data-ttu-id="4e28b-187">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="4e28b-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="4e28b-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="4e28b-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-189">Restriction Name</span></span>|<span data-ttu-id="4e28b-190">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-190">Parameter Name</span></span>|<span data-ttu-id="4e28b-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-191">Restriction Default</span></span>|<span data-ttu-id="4e28b-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-193">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-193">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-194">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-195">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-195">1</span></span>|  
|<span data-ttu-id="4e28b-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-196">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-198">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-198">2</span></span>|  
|<span data-ttu-id="4e28b-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-199">Table</span></span>|@Table|<span data-ttu-id="4e28b-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-200">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-201">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-201">3</span></span>|  
|<span data-ttu-id="4e28b-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="4e28b-202">Column</span></span>|@Column|<span data-ttu-id="4e28b-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-203">COLUMN_NAME</span></span>|<span data-ttu-id="4e28b-204">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="4e28b-205">Представления</span><span class="sxs-lookup"><span data-stu-id="4e28b-205">Views</span></span>  
  
|<span data-ttu-id="4e28b-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-206">Restriction Name</span></span>|<span data-ttu-id="4e28b-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-207">Parameter Name</span></span>|<span data-ttu-id="4e28b-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-208">Restriction Default</span></span>|<span data-ttu-id="4e28b-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-210">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-210">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-211">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-212">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-212">1</span></span>|  
|<span data-ttu-id="4e28b-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-213">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-215">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-215">2</span></span>|  
|<span data-ttu-id="4e28b-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-216">Table</span></span>|@Table|<span data-ttu-id="4e28b-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-217">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-218">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="4e28b-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="4e28b-219">ViewColumns</span></span>  
  
|<span data-ttu-id="4e28b-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-220">Restriction Name</span></span>|<span data-ttu-id="4e28b-221">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-221">Parameter Name</span></span>|<span data-ttu-id="4e28b-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-222">Restriction Default</span></span>|<span data-ttu-id="4e28b-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-224">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-224">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-225">VIEW_CATALOG</span></span>|<span data-ttu-id="4e28b-226">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-226">1</span></span>|  
|<span data-ttu-id="4e28b-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-227">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="4e28b-229">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-229">2</span></span>|  
|<span data-ttu-id="4e28b-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-230">Table</span></span>|@Table|<span data-ttu-id="4e28b-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-231">VIEW_NAME</span></span>|<span data-ttu-id="4e28b-232">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-232">3</span></span>|  
|<span data-ttu-id="4e28b-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="4e28b-233">Column</span></span>|@Column|<span data-ttu-id="4e28b-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-234">COLUMN_NAME</span></span>|<span data-ttu-id="4e28b-235">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="4e28b-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4e28b-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="4e28b-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-237">Restriction Name</span></span>|<span data-ttu-id="4e28b-238">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-238">Parameter Name</span></span>|<span data-ttu-id="4e28b-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-239">Restriction Default</span></span>|<span data-ttu-id="4e28b-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-241">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-241">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="4e28b-243">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-243">1</span></span>|  
|<span data-ttu-id="4e28b-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-244">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="4e28b-246">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-246">2</span></span>|  
|<span data-ttu-id="4e28b-247">Имя</span><span class="sxs-lookup"><span data-stu-id="4e28b-247">Name</span></span>|@Name|<span data-ttu-id="4e28b-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="4e28b-249">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-249">3</span></span>|  
|<span data-ttu-id="4e28b-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="4e28b-250">Parameter</span></span>|@Parameter|<span data-ttu-id="4e28b-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-251">PARAMETER_NAME</span></span>|<span data-ttu-id="4e28b-252">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4e28b-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4e28b-253">Procedures</span></span>  
  
|<span data-ttu-id="4e28b-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-254">Restriction Name</span></span>|<span data-ttu-id="4e28b-255">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-255">Parameter Name</span></span>|<span data-ttu-id="4e28b-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-256">Restriction Default</span></span>|<span data-ttu-id="4e28b-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-258">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-258">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="4e28b-260">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-260">1</span></span>|  
|<span data-ttu-id="4e28b-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-261">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="4e28b-263">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-263">2</span></span>|  
|<span data-ttu-id="4e28b-264">Имя</span><span class="sxs-lookup"><span data-stu-id="4e28b-264">Name</span></span>|@Name|<span data-ttu-id="4e28b-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="4e28b-266">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-266">3</span></span>|  
|<span data-ttu-id="4e28b-267">Тип</span><span class="sxs-lookup"><span data-stu-id="4e28b-267">Type</span></span>|@Type|<span data-ttu-id="4e28b-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4e28b-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="4e28b-269">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="4e28b-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="4e28b-270">IndexColumns</span></span>  
  
|<span data-ttu-id="4e28b-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-271">Restriction Name</span></span>|<span data-ttu-id="4e28b-272">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-272">Parameter Name</span></span>|<span data-ttu-id="4e28b-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-273">Restriction Default</span></span>|<span data-ttu-id="4e28b-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-275">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-275">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="4e28b-276">db_name()</span></span>|<span data-ttu-id="4e28b-277">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-277">1</span></span>|  
|<span data-ttu-id="4e28b-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-278">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="4e28b-279">user_name()</span></span>|<span data-ttu-id="4e28b-280">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-280">2</span></span>|  
|<span data-ttu-id="4e28b-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-281">Table</span></span>|@Table|<span data-ttu-id="4e28b-282">o.name</span><span class="sxs-lookup"><span data-stu-id="4e28b-282">o.name</span></span>|<span data-ttu-id="4e28b-283">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-283">3</span></span>|  
|<span data-ttu-id="4e28b-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="4e28b-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="4e28b-285">x.name</span><span class="sxs-lookup"><span data-stu-id="4e28b-285">x.name</span></span>|<span data-ttu-id="4e28b-286">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-286">4</span></span>|  
|<span data-ttu-id="4e28b-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="4e28b-287">Column</span></span>|@Column|<span data-ttu-id="4e28b-288">c.name</span><span class="sxs-lookup"><span data-stu-id="4e28b-288">c.name</span></span>|<span data-ttu-id="4e28b-289">5</span><span class="sxs-lookup"><span data-stu-id="4e28b-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4e28b-290">Индексы</span><span class="sxs-lookup"><span data-stu-id="4e28b-290">Indexes</span></span>  
  
|<span data-ttu-id="4e28b-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-291">Restriction Name</span></span>|<span data-ttu-id="4e28b-292">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-292">Parameter Name</span></span>|<span data-ttu-id="4e28b-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-293">Restriction Default</span></span>|<span data-ttu-id="4e28b-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-295">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-295">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="4e28b-296">db_name()</span></span>|<span data-ttu-id="4e28b-297">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-297">1</span></span>|  
|<span data-ttu-id="4e28b-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-298">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="4e28b-299">user_name()</span></span>|<span data-ttu-id="4e28b-300">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-300">2</span></span>|  
|<span data-ttu-id="4e28b-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-301">Table</span></span>|@Table|<span data-ttu-id="4e28b-302">o.name</span><span class="sxs-lookup"><span data-stu-id="4e28b-302">o.name</span></span>|<span data-ttu-id="4e28b-303">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="4e28b-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="4e28b-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="4e28b-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-305">Restriction Name</span></span>|<span data-ttu-id="4e28b-306">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-306">Parameter Name</span></span>|<span data-ttu-id="4e28b-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-307">Restriction Default</span></span>|<span data-ttu-id="4e28b-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="4e28b-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="4e28b-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="4e28b-310">assemblies.name</span></span>|<span data-ttu-id="4e28b-311">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-311">1</span></span>|  
|<span data-ttu-id="4e28b-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="4e28b-312">udt_name</span></span>|@UDTName|<span data-ttu-id="4e28b-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="4e28b-313">types.assembly_class</span></span>|<span data-ttu-id="4e28b-314">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="4e28b-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="4e28b-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="4e28b-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-316">Restriction Name</span></span>|<span data-ttu-id="4e28b-317">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-317">Parameter Name</span></span>|<span data-ttu-id="4e28b-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-318">Restriction Default</span></span>|<span data-ttu-id="4e28b-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-320">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-320">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="4e28b-322">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-322">1</span></span>|  
|<span data-ttu-id="4e28b-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-323">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="4e28b-325">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-325">2</span></span>|  
|<span data-ttu-id="4e28b-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-326">Table</span></span>|@Table|<span data-ttu-id="4e28b-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-327">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-328">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-328">3</span></span>|  
|<span data-ttu-id="4e28b-329">Имя</span><span class="sxs-lookup"><span data-stu-id="4e28b-329">Name</span></span>|@Name|<span data-ttu-id="4e28b-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="4e28b-331">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="4e28b-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="4e28b-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="4e28b-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4e28b-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="4e28b-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4e28b-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="4e28b-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e28b-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="4e28b-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="4e28b-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="4e28b-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-337">Restriction Name</span></span>|<span data-ttu-id="4e28b-338">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-338">Parameter Name</span></span>|<span data-ttu-id="4e28b-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-339">Restriction Default</span></span>|<span data-ttu-id="4e28b-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-341">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-341">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-342">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-343">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-343">1</span></span>|  
|<span data-ttu-id="4e28b-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-344">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-346">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-346">2</span></span>|  
|<span data-ttu-id="4e28b-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-347">Table</span></span>|@Table|<span data-ttu-id="4e28b-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-348">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-349">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="4e28b-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="4e28b-350">AllColumns</span></span>  
  
|<span data-ttu-id="4e28b-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-351">Restriction Name</span></span>|<span data-ttu-id="4e28b-352">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="4e28b-352">Parameter Name</span></span>|<span data-ttu-id="4e28b-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4e28b-353">Restriction Default</span></span>|<span data-ttu-id="4e28b-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="4e28b-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4e28b-355">Каталог</span><span class="sxs-lookup"><span data-stu-id="4e28b-355">Catalog</span></span>|@Catalog|<span data-ttu-id="4e28b-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4e28b-356">TABLE_CATALOG</span></span>|<span data-ttu-id="4e28b-357">1</span><span class="sxs-lookup"><span data-stu-id="4e28b-357">1</span></span>|  
|<span data-ttu-id="4e28b-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="4e28b-358">Owner</span></span>|@Owner|<span data-ttu-id="4e28b-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4e28b-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="4e28b-360">2</span><span class="sxs-lookup"><span data-stu-id="4e28b-360">2</span></span>|  
|<span data-ttu-id="4e28b-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="4e28b-361">Table</span></span>|@Table|<span data-ttu-id="4e28b-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-362">TABLE_NAME</span></span>|<span data-ttu-id="4e28b-363">3</span><span class="sxs-lookup"><span data-stu-id="4e28b-363">3</span></span>|  
|<span data-ttu-id="4e28b-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="4e28b-364">Column</span></span>|@Column|<span data-ttu-id="4e28b-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4e28b-365">COLUMN_NAME</span></span>|<span data-ttu-id="4e28b-366">4</span><span class="sxs-lookup"><span data-stu-id="4e28b-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e28b-367">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e28b-367">See also</span></span>

- [<span data-ttu-id="4e28b-368">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4e28b-368">ADO.NET Overview</span></span>](ado-net-overview.md)
