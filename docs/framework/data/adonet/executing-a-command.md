---
title: "Выполнение команды"
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
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 035d619574707ec7944c80b95d5b7a6ea0de1899
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="executing-a-command"></a><span data-ttu-id="85ea5-102">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="85ea5-102">Executing a Command</span></span>
<span data-ttu-id="85ea5-103">Каждый поставщик данных .NET Framework, включенный в состав .NET Framework, имеет собственный объект команды, наследуемый от <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-103">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="85ea5-104">Поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbCommand>, поставщик данных .NET Framework для SQL Server - объект <xref:System.Data.SqlClient.SqlCommand>, поставщик данных .NET Framework для ODBC - объект <xref:System.Data.Odbc.OdbcCommand>, а поставщик данных .NET Framework для Oracle - объект <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-104">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="85ea5-105">Каждый из этих объектов предоставляет методы выполнения команд с учетом типа команды и требуемого возвращаемого значения, как описано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="85ea5-105">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="85ea5-106">Команда</span><span class="sxs-lookup"><span data-stu-id="85ea5-106">Command</span></span>|<span data-ttu-id="85ea5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85ea5-107">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="85ea5-108">Возвращает объект `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="85ea5-108">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="85ea5-109">Возвращает одно скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="85ea5-109">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="85ea5-110">Выполняет команду, которая не возвращает строк.</span><span class="sxs-lookup"><span data-stu-id="85ea5-110">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="85ea5-111">Возвращает значение типа <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="85ea5-111">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="85ea5-112">Этот метод предусмотрен только для объекта `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="85ea5-112">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="85ea5-113">Каждый строго типизированный объект команды поддерживает также перечисление <xref:System.Data.CommandType>, которое указывает способ интерпретации строки команды, как описано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="85ea5-113">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="85ea5-114">CommandType</span><span class="sxs-lookup"><span data-stu-id="85ea5-114">CommandType</span></span>|<span data-ttu-id="85ea5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="85ea5-115">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="85ea5-116">Команда SQL, определяющая инструкции, которые выполняются применительно к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="85ea5-116">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="85ea5-117">Имя хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="85ea5-117">The name of the stored procedure.</span></span> <span data-ttu-id="85ea5-118">Свойство команды `Parameters` может использоваться для доступа к входным и выходным параметрам и возвращаемым значениям независимо от вызываемого метода `Execute`.</span><span class="sxs-lookup"><span data-stu-id="85ea5-118">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="85ea5-119">При использовании `ExecuteReader` возвращаемые значения и выходные параметры будут недоступными, пока не будет закрыт `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="85ea5-119">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="85ea5-120">Имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="85ea5-120">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="85ea5-121">Пример</span><span class="sxs-lookup"><span data-stu-id="85ea5-121">Example</span></span>  
 <span data-ttu-id="85ea5-122">Следующий пример кода демонстрирует способ создания объекта <xref:System.Data.SqlClient.SqlCommand> для выполнения хранимой процедуры путем установки его свойств.</span><span class="sxs-lookup"><span data-stu-id="85ea5-122">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="85ea5-123">Объект <xref:System.Data.SqlClient.SqlParameter> используется для задания входных параметров хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="85ea5-123">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="85ea5-124">Команда выполняется с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>, и выходное значение из <xref:System.Data.SqlClient.SqlDataReader> отображается в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="85ea5-124">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="85ea5-125">Команды устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="85ea5-125">Troubleshooting Commands</span></span>  
 <span data-ttu-id="85ea5-126">Поставщик данных .NET Framework для SQL Server добавляет счетчики производительности, позволяя обнаруживать периодически возникающие проблемы, связанные со сбоями команд.</span><span class="sxs-lookup"><span data-stu-id="85ea5-126">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="85ea5-127">Дополнительные сведения см. [счетчики производительности](../../../../docs/framework/data/adonet/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="85ea5-127">For more information see [Performance Counters](../../../../docs/framework/data/adonet/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ea5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="85ea5-128">See Also</span></span>  
 [<span data-ttu-id="85ea5-129">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="85ea5-129">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="85ea5-130">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="85ea5-130">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="85ea5-131">Работа с объекты DataReader</span><span class="sxs-lookup"><span data-stu-id="85ea5-131">Working with DataReaders</span></span>](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="85ea5-132">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="85ea5-132">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
