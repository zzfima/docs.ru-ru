---
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791683"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="38a48-102">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="38a48-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="38a48-103">В SQL Server появился описатель `max`, расширяющий возможности хранения типов данных `varchar`, `nvarchar` и `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="38a48-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="38a48-104">`varchar(max)`, `nvarchar(max)` и`varbinary(max)` совместно называются *типами данных больших значений*.</span><span class="sxs-lookup"><span data-stu-id="38a48-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="38a48-105">Типы данных большого размера можно использовать для хранения данных размером до 2^31-1 байт.</span><span class="sxs-lookup"><span data-stu-id="38a48-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="38a48-106">В SQL Server 2008 появился атрибут FILESTREAM, который является не типом данных, а определяемым для столбца атрибутом, позволяющим хранить данные большого размера не в базе данных, а в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="38a48-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38a48-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="38a48-107">In This Section</span></span>  
 [<span data-ttu-id="38a48-108">Изменение данных больших объемов (max) в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38a48-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="38a48-109">Содержит описание работы с большими типами данных.</span><span class="sxs-lookup"><span data-stu-id="38a48-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="38a48-110">Данные FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="38a48-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="38a48-111">Описывается работа с данными большого размера, хранящимися в SQL Server 2008 с указанием атрибута FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="38a48-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a48-112">См. также</span><span class="sxs-lookup"><span data-stu-id="38a48-112">See also</span></span>

- [<span data-ttu-id="38a48-113">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38a48-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="38a48-114">Операции данных SQL Server Data в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38a48-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="38a48-115">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38a48-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="38a48-116">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="38a48-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
