---
title: "Типы SqlType и набор данных"
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
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3235581ca3328307396796f01ff728ab798d3ad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="c5d70-102">Типы SqlType и набор данных</span><span class="sxs-lookup"><span data-stu-id="c5d70-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="c5d70-103">В ADO.NET 2.0 улучшена поддержка типов для объекта `DataSet` через пространство имен <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="c5d70-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="c5d70-104">Типы <xref:System.Data.SqlTypes> разработаны для предоставления типов данных с одинаковой семантикой и точностью в качестве типов данных в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5d70-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="c5d70-105">Каждому типу данных в пространстве имен <xref:System.Data.SqlTypes> соответствует эквивалентный тип данных в SQL Server с аналогичным базовым представлением данных.</span><span class="sxs-lookup"><span data-stu-id="c5d70-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="c5d70-106">Использование <xref:System.Data.SqlTypes> непосредственно в <xref:System.Data.DataSet> дает несколько преимуществ при работе с типами данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5d70-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="c5d70-107"><xref:System.Data.SqlTypes> поддерживает ту же семантику, что и собственные типы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5d70-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="c5d70-108">Указание одного из типов <xref:System.Data.SqlTypes> в определении <xref:System.Data.DataColumn> позволяет избежать потери точности, которая может возникнуть при преобразовании десятичных или численных типов данных к одному из типов данных среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c5d70-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5d70-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c5d70-109">Example</span></span>  
 <span data-ttu-id="c5d70-110">В приведенном ниже примере создается объект <xref:System.Data.DataTable>, явным образом определяющий типы данных <xref:System.Data.DataColumn> через типы <xref:System.Data.SqlTypes>, а не типы среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c5d70-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="c5d70-111">В этом коде таблица <xref:System.Data.DataTable> заполняется данными из таблицы Sales.SalesOrderDetail базы данных AdventureWorks на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5d70-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="c5d70-112">В результатах, отображаемых в консольном окне, показывается тип данных каждого столбца, а также значения, полученные из SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5d70-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c5d70-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c5d70-113">See Also</span></span>  
 [<span data-ttu-id="c5d70-114">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5d70-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="c5d70-115">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="c5d70-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="c5d70-116">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5d70-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
