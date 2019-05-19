---
title: Oracle и ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 012a5b55d052f5f06da5c152da79f4676b2bff4e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877951"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="893cb-102">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="893cb-103">Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="893cb-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="893cb-104">Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="893cb-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="893cb-105">Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="893cb-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="893cb-106">В этом разделе описывает возможности и варианты поведения, характерные для поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="893cb-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="893cb-107">Поставщик данных .NET Framework для Oracle обеспечивает доступ к базе данных Oracle, используя интерфейс вызова Oracle (OCI), предоставленный клиентского программного обеспечения Oracle.</span><span class="sxs-lookup"><span data-stu-id="893cb-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="893cb-108">Функциональные возможности поставщика данных должна быть аналогична поставщиков данных .NET Framework для SQL Server, OLE DB и ODBC.</span><span class="sxs-lookup"><span data-stu-id="893cb-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="893cb-109">Чтобы использовать поставщик данных .NET Framework для Oracle, приложение должно ссылаться <xref:System.Data.OracleClient> пространства имен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="893cb-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="893cb-110">Также при компиляции кода необходимо включить ссылку на библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="893cb-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="893cb-111">Например, при компиляции программы C# командная строка должна включать:</span><span class="sxs-lookup"><span data-stu-id="893cb-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="893cb-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="893cb-112">In This Section</span></span>  
 [<span data-ttu-id="893cb-113">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="893cb-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="893cb-114">Описывает требования для использования поставщика данных .NET Framework для Oracle и ряд вопросов, которые следует учитывать при его использовании.</span><span class="sxs-lookup"><span data-stu-id="893cb-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="893cb-115">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="893cb-116">Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.</span><span class="sxs-lookup"><span data-stu-id="893cb-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="893cb-117">Большие объекты (LOB) в Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="893cb-118">Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.</span><span class="sxs-lookup"><span data-stu-id="893cb-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="893cb-119">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="893cb-120">Описывает поддержку для типа данных Oracle REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="893cb-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="893cb-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="893cb-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="893cb-122">Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="893cb-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="893cb-123">Последовательности Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="893cb-124">Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.</span><span class="sxs-lookup"><span data-stu-id="893cb-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="893cb-125">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="893cb-126">Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="893cb-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="893cb-127">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="893cb-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="893cb-128">Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="893cb-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="893cb-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="893cb-129">Related Sections</span></span>  
 [<span data-ttu-id="893cb-130">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="893cb-131">Описывает приемы безопасного программирования при использовании ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="893cb-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="893cb-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="893cb-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="893cb-133">Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="893cb-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="893cb-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="893cb-135">Описывает работу с данными в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="893cb-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="893cb-136">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="893cb-137">Описывает процесс работы со специальными возможностями и функциями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="893cb-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="893cb-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="893cb-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="893cb-139">Описывает универсальные классы, позволяющие писать независимый от поставщика код в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="893cb-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893cb-140">См. также</span><span class="sxs-lookup"><span data-stu-id="893cb-140">See also</span></span>

- [<span data-ttu-id="893cb-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="893cb-142">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="893cb-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
