---
title: Oracle и ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: ccfe40f218e3f09de53d6cb596a31b2520d9ff9b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783476"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="95f61-102">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-102">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="95f61-103">Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="95f61-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="95f61-104">Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="95f61-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="95f61-105">Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="95f61-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="95f61-106">В этом разделе описываются функции и поведения, характерные для поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="95f61-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="95f61-107">Поставщик данных .NET Framework для Oracle предоставляет доступ к базе данных Oracle с помощью интерфейса Oracle Call Interface (OCI), предоставляемого клиентским программным обеспечением Oracle.</span><span class="sxs-lookup"><span data-stu-id="95f61-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="95f61-108">Функциональные возможности поставщика данных аналогичны функциям .NET Framework поставщиков данных для SQL Server, OLE DB и ODBC.</span><span class="sxs-lookup"><span data-stu-id="95f61-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="95f61-109">Чтобы использовать поставщик данных .NET Framework для Oracle, приложение должно ссылаться на <xref:System.Data.OracleClient> пространство имен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="95f61-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="95f61-110">Также при компиляции кода необходимо включить ссылку на библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="95f61-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="95f61-111">Например, при компиляции программы C# командная строка должна включать:</span><span class="sxs-lookup"><span data-stu-id="95f61-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="95f61-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="95f61-112">In This Section</span></span>  
 [<span data-ttu-id="95f61-113">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="95f61-113">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="95f61-114">Описывает требования к использованию поставщика данных .NET Framework для Oracle и описывает ряд проблем, которые необходимо учитывать при их использовании.</span><span class="sxs-lookup"><span data-stu-id="95f61-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="95f61-115">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-115">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="95f61-116">Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.</span><span class="sxs-lookup"><span data-stu-id="95f61-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="95f61-117">Большие объекты (LOB) в Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-117">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="95f61-118">Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.</span><span class="sxs-lookup"><span data-stu-id="95f61-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="95f61-119">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-119">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="95f61-120">Описывает поддержку для типа данных Oracle REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="95f61-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="95f61-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="95f61-121">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="95f61-122">Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="95f61-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="95f61-123">Последовательности Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-123">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="95f61-124">Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.</span><span class="sxs-lookup"><span data-stu-id="95f61-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="95f61-125">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-125">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="95f61-126">Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="95f61-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="95f61-127">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="95f61-127">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="95f61-128">Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="95f61-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="95f61-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="95f61-129">Related Sections</span></span>  
 [<span data-ttu-id="95f61-130">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-130">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="95f61-131">Описывает приемы безопасного программирования при использовании ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="95f61-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="95f61-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="95f61-132">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="95f61-133">Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="95f61-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="95f61-134">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="95f61-135">Описывает работу с данными в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="95f61-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="95f61-136">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-136">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="95f61-137">Описывает процесс работы со специальными возможностями и функциями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95f61-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="95f61-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="95f61-138">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="95f61-139">Описывает универсальные классы, позволяющие писать независимый от поставщика код в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="95f61-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f61-140">См. также</span><span class="sxs-lookup"><span data-stu-id="95f61-140">See also</span></span>

- [<span data-ttu-id="95f61-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="95f61-142">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f61-142">ADO.NET Overview</span></span>](ado-net-overview.md)
