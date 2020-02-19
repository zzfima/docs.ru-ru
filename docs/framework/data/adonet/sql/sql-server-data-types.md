---
title: Типы данных SQL Server и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: f727c69b1dd5c23c6a89911005256de70255fd4c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452335"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="eeadd-102">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eeadd-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="eeadd-103">В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных.</span><span class="sxs-lookup"><span data-stu-id="eeadd-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="eeadd-104">Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eeadd-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="eeadd-105">Для указания типов данных <xref:System.Data.SqlDbType> можно использовать перечисления классов <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="eeadd-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="eeadd-106">Дополнительные сведения и таблица с описанием сопоставлений типов данных между типами данных SQL Server и .NET Framework см. в разделе [SQL Server сопоставления типов данных](../sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="eeadd-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="eeadd-107">В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей по работе с датами и временем, структурированными, частично структурированными и неструктурированными данными.</span><span class="sxs-lookup"><span data-stu-id="eeadd-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="eeadd-108">Они описаны в электронной документации на SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="eeadd-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="eeadd-109">Типы данных SQL Server, которые можно использовать в приложениях, зависят от используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eeadd-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="eeadd-110">Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="eeadd-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="eeadd-111">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="eeadd-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="eeadd-112">Типы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eeadd-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="eeadd-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="eeadd-113">In This Section</span></span>  
 [<span data-ttu-id="eeadd-114">Типы SqlType и набор данных</span><span class="sxs-lookup"><span data-stu-id="eeadd-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="eeadd-115">Описывает тип поддержки пространства имен `SqlTypes` в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="eeadd-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="eeadd-116">Обработка значений NULL</span><span class="sxs-lookup"><span data-stu-id="eeadd-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="eeadd-117">Демонстрируется работа со значениями NULL и тройственной логикой.</span><span class="sxs-lookup"><span data-stu-id="eeadd-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="eeadd-118">Сравнение значений идентификатора GUID и uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="eeadd-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="eeadd-119">Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eeadd-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="eeadd-120">Данные даты и времени</span><span class="sxs-lookup"><span data-stu-id="eeadd-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="eeadd-121">Описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="eeadd-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="eeadd-122">Большие UDT</span><span class="sxs-lookup"><span data-stu-id="eeadd-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="eeadd-123">Демонстрируется извлечение данных из определяемых пользователем типов данных большого размера, появившихся в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="eeadd-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="eeadd-124">Данные XML в SQL Server</span><span class="sxs-lookup"><span data-stu-id="eeadd-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="eeadd-125">Описание работы с данными XML, извлеченными из SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eeadd-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eeadd-126">Справочник</span><span class="sxs-lookup"><span data-stu-id="eeadd-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="eeadd-127">Описывает класс `DataSet` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="eeadd-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="eeadd-128">Описывает пространство имен `SqlTypes` и все его элементы.</span><span class="sxs-lookup"><span data-stu-id="eeadd-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="eeadd-129">Описывает перечисление `SqlDbType` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="eeadd-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="eeadd-130">Описывает перечисление `DbType` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="eeadd-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeadd-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eeadd-131">See also</span></span>

- [<span data-ttu-id="eeadd-132">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="eeadd-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="eeadd-133">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="eeadd-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="eeadd-134">Возвращающие табличные значения параметры</span><span class="sxs-lookup"><span data-stu-id="eeadd-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="eeadd-135">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="eeadd-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="eeadd-136">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eeadd-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
