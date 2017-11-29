---
title: "Сопоставления типов данных в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 65f9d8a6182c5882a173a3a3733c1c0c220efbf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="d4a48-102">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4a48-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="d4a48-103">Платформа .NET Framework основана на общей системе типов, в которой определяются способы объявления, использования типов и управления ими во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4a48-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="d4a48-104">Система типов состоит из типов-значений и типов-ссылок, производных от базового типа <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="d4a48-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="d4a48-105">При работе с источником данных не указанный явным образом тип данных выводится из поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="d4a48-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="d4a48-106">Например, объект <xref:System.Data.DataSet> не зависит ни от одного конкретного источника данных.</span><span class="sxs-lookup"><span data-stu-id="d4a48-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="d4a48-107">Получение данных в `DataSet` осуществляется из источника данных, а изменения передаются для сохранения в источнике данных с использованием `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d4a48-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="d4a48-108">Это означает, что при заполнении адаптером `DataAdapter` таблицы <xref:System.Data.DataTable> в наборе данных `DataSet` значениями из источника данных, результирующие типы данных столбцов в `DataTable` представляют собой типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], а не типы, относящиеся к поставщику данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], который использовался для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="d4a48-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types, instead of types specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="d4a48-109">Аналогичным образом, при возврате модулем `DataReader` любого значения из источника данных результирующее значение сохраняется в локальной переменной, которая имеет тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4a48-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type.</span></span> <span data-ttu-id="d4a48-110">Как для операций `Fill` объекта `DataAdapter`, так и для методов `Get` класса `DataReader`, тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] выводится из значения, возвращенного поставщиком данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4a48-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type is inferred from the value returned from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
 <span data-ttu-id="d4a48-111">Если известен тип возвращаемого значения, то вместо выводимого типа данных можно воспользоваться типизированными методами доступа объекта `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="d4a48-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="d4a48-112">Применение типизированных методов доступа позволяет достичь более высокой производительности, поскольку происходит возврат значения в качестве конкретного типа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], в связи с чем устраняется необходимость в дополнительном преобразовании типа.</span><span class="sxs-lookup"><span data-stu-id="d4a48-112">Typed accessor methods give you better performance by returning a value as a specific [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4a48-113">Значения NULL для типов данных поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] представлены с помощью `DBNull.Value`.</span><span class="sxs-lookup"><span data-stu-id="d4a48-113">Null values for [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4a48-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="d4a48-114">In This Section</span></span>  
 [<span data-ttu-id="d4a48-115">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4a48-115">SQL Server Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <span data-ttu-id="d4a48-116">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="d4a48-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="d4a48-117">Сопоставления типов данных OLE DB</span><span class="sxs-lookup"><span data-stu-id="d4a48-117">OLE DB Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <span data-ttu-id="d4a48-118">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="d4a48-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="d4a48-119">Сопоставления типов данных ODBC</span><span class="sxs-lookup"><span data-stu-id="d4a48-119">ODBC Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <span data-ttu-id="d4a48-120">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.Odbc>.</span><span class="sxs-lookup"><span data-stu-id="d4a48-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="d4a48-121">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="d4a48-121">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="d4a48-122">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="d4a48-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="d4a48-123">Числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d4a48-123">Floating-Point Numbers</span></span>](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 <span data-ttu-id="d4a48-124">Описывает проблемы, с которыми разработчики часто сталкиваются при работе с числами с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d4a48-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a48-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d4a48-125">See Also</span></span>  
 [<span data-ttu-id="d4a48-126">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4a48-126">SQL Server Data Types and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="d4a48-127">Настройка параметров и типов данных параметров</span><span class="sxs-lookup"><span data-stu-id="d4a48-127">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="d4a48-128">Получение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="d4a48-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="d4a48-129">Система общих типов CTS</span><span class="sxs-lookup"><span data-stu-id="d4a48-129">Common Type System</span></span>](../../../../docs/standard/base-types/common-type-system.md)  
 [<span data-ttu-id="d4a48-130">Преобразование типов</span><span class="sxs-lookup"><span data-stu-id="d4a48-130">Converting Types</span></span>](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [<span data-ttu-id="d4a48-131">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4a48-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
