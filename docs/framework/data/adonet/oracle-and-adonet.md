---
title: Oracle и ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 9a60499674f0192bb7589f227bffb6f907f682d9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084602"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="f4116-102">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="f4116-103">Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="f4116-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="f4116-104">Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="f4116-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="f4116-105">Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="f4116-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="f4116-106">В этом разделе описаны функции и правила работы, характерные для поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle.</span><span class="sxs-lookup"><span data-stu-id="f4116-106">This section describes features and behaviors that are specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="f4116-107">Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle обеспечивает доступ к базе данных Oracle, используя интерфейс Oracle Call (OCI), поставляемый в пакете клиентского программного обеспечения Oracle.</span><span class="sxs-lookup"><span data-stu-id="f4116-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="f4116-108">Функциональные возможности поставщика данных должен быть аналогичен [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщики данных для SQL Server, OLE DB и ODBC.</span><span class="sxs-lookup"><span data-stu-id="f4116-108">The functionality of the data provider is designed to be similar to that of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="f4116-109">Чтобы использовать поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle, приложение должно содержать ссылку на пространство имен <xref:System.Data.OracleClient> следующим образом: </span><span class="sxs-lookup"><span data-stu-id="f4116-109">To use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="f4116-110">Также при компиляции кода необходимо включить ссылку на библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="f4116-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="f4116-111">Например, при компиляции программы C# командная строка должна включать:</span><span class="sxs-lookup"><span data-stu-id="f4116-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="f4116-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f4116-112">In This Section</span></span>  
 [<span data-ttu-id="f4116-113">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="f4116-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="f4116-114">Содержит требования к использованию поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle и описывает многие проблемы, которые необходимо учитывать при его использовании.</span><span class="sxs-lookup"><span data-stu-id="f4116-114">Describes requirements for using the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="f4116-115">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="f4116-116">Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.</span><span class="sxs-lookup"><span data-stu-id="f4116-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="f4116-117">Большие объекты (LOB) в Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="f4116-118">Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.</span><span class="sxs-lookup"><span data-stu-id="f4116-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="f4116-119">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="f4116-120">Описывает поддержку для типа данных Oracle REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="f4116-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="f4116-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="f4116-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="f4116-122">Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="f4116-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="f4116-123">Последовательности Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="f4116-124">Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.</span><span class="sxs-lookup"><span data-stu-id="f4116-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="f4116-125">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="f4116-126">Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="f4116-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="f4116-127">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="f4116-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="f4116-128">Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="f4116-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f4116-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f4116-129">Related Sections</span></span>  
 [<span data-ttu-id="f4116-130">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="f4116-131">Описывает приемы безопасного программирования при использовании [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4116-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="f4116-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="f4116-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="f4116-133">Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="f4116-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="f4116-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="f4116-135">Описывает работу с данными в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f4116-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="f4116-136">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="f4116-137">Описывает процесс работы со специальными возможностями и возможностями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4116-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="f4116-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="f4116-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="f4116-139">Описывает универсальные классы, позволяющие создавать независимый от поставщика код в [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4116-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4116-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f4116-140">See Also</span></span>  
 [<span data-ttu-id="f4116-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="f4116-142">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4116-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
