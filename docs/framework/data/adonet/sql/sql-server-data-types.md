---
title: "Типы данных SQL Server и ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="1ef80-102">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ef80-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="1ef80-103">В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных.</span><span class="sxs-lookup"><span data-stu-id="1ef80-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="1ef80-104">Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ef80-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="1ef80-105">Для указания типов данных <xref:System.Data.SqlDbType> можно использовать перечисления классов <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="1ef80-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="1ef80-106">Дополнительные сведения и таблицу с описанием данных введите сопоставления между типами данных .NET Framework и SQL Server см. в разделе [сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="1ef80-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="1ef80-107">В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей по работе с датами и временем, структурированными, частично структурированными и неструктурированными данными.</span><span class="sxs-lookup"><span data-stu-id="1ef80-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="1ef80-108">Новые типы данных описаны в электронной документации по SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1ef80-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="1ef80-109">Типы данных SQL Server, которые можно использовать в приложениях, зависят от используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ef80-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="1ef80-110">Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="1ef80-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="1ef80-111">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1ef80-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="1ef80-112">Типы данных (ядро СУБД)</span><span class="sxs-lookup"><span data-stu-id="1ef80-112">Data Types (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="1ef80-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="1ef80-113">In This Section</span></span>  
 [<span data-ttu-id="1ef80-114">Типы SQLType и набор данных</span><span class="sxs-lookup"><span data-stu-id="1ef80-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="1ef80-115">Описывается поддержка типов для объекта `SqlTypes` в объекте `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="1ef80-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="1ef80-116">Обработка значений Null</span><span class="sxs-lookup"><span data-stu-id="1ef80-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="1ef80-117">Демонстрируется работа со значениями NULL и тройственной логикой.</span><span class="sxs-lookup"><span data-stu-id="1ef80-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="1ef80-118">Сравнение GUID и uniqueidentifier значения</span><span class="sxs-lookup"><span data-stu-id="1ef80-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="1ef80-119">Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ef80-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="1ef80-120">Данных даты и времени</span><span class="sxs-lookup"><span data-stu-id="1ef80-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="1ef80-121">Описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1ef80-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="1ef80-122">Больших определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="1ef80-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="1ef80-123">Демонстрируется извлечение данных из определяемых пользователем типов данных большого размера, появившихся в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1ef80-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="1ef80-124">XML-данных в SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ef80-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="1ef80-125">Описание работы с данными XML, извлеченными из SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ef80-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1ef80-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="1ef80-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="1ef80-127">Описывает класс `DataSet` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="1ef80-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="1ef80-128">Описывает пространство имен `SqlTypes` и все его элементы.</span><span class="sxs-lookup"><span data-stu-id="1ef80-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="1ef80-129">Описывает перечисление `SqlDbType` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="1ef80-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="1ef80-130">Описывает перечисление `DbType` и все его члены.</span><span class="sxs-lookup"><span data-stu-id="1ef80-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef80-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1ef80-131">See Also</span></span>  
 [<span data-ttu-id="1ef80-132">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ef80-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="1ef80-133">Настройка параметров и типов данных параметров</span><span class="sxs-lookup"><span data-stu-id="1ef80-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="1ef80-134">Возвращающие табличные значения параметров</span><span class="sxs-lookup"><span data-stu-id="1ef80-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="1ef80-135">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ef80-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="1ef80-136">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ef80-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
