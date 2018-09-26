---
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078179"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="f02bb-102">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="f02bb-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="f02bb-103">В SQL Server появился описатель `max`, расширяющий возможности хранения типов данных `varchar`, `nvarchar` и `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="f02bb-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="f02bb-104">`varchar(max)`, `nvarchar(max)`, и `varbinary(max)` называются *типы данных больших значений*.</span><span class="sxs-lookup"><span data-stu-id="f02bb-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="f02bb-105">Типы данных большого размера можно использовать для хранения данных размером до 2^31-1 байт.</span><span class="sxs-lookup"><span data-stu-id="f02bb-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="f02bb-106">В SQL Server 2008 появился атрибут FILESTREAM, который является не типом данных, а определяемым для столбца атрибутом, позволяющим хранить данные большого размера не в базе данных, а в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="f02bb-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f02bb-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f02bb-107">In This Section</span></span>  
 [<span data-ttu-id="f02bb-108">Изменение данных больших объемов (max) в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f02bb-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="f02bb-109">Содержит описание работы с большими типами данных.</span><span class="sxs-lookup"><span data-stu-id="f02bb-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="f02bb-110">Данные FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="f02bb-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="f02bb-111">Описывается работа с данными большого размера, хранящимися в SQL Server 2008 с указанием атрибута FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f02bb-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02bb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f02bb-112">See Also</span></span>  
 [<span data-ttu-id="f02bb-113">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f02bb-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="f02bb-114">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f02bb-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="f02bb-115">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f02bb-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="f02bb-116">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f02bb-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
